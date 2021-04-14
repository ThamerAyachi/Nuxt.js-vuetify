<template>
  <div class="text-center">
    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="grey"
          text
          v-bind="attrs"
          v-on="on"
        >
          <span>Menu</span>
          <v-icon right>mdi-dots-vertical</v-icon>
        </v-btn>
      </template>
      <!-- list -->
      <v-list>
        <v-list-item-group>
          <!-- for in list item -->
          <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
              <!-- icon list -->
              <v-list-item-icon>
                <v-icon class="grey--text">{{link.icon}}</v-icon>
              </v-list-item-icon>
              <!-- text list -->
              <span class="grey--text">{{link.text}}</span>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-menu>
  </div>
</template>

<script>
  export default {
    name: 'BtnMenu',
    data: () => ({
      links: [
        {icon: 'mdi-home', text: 'Home', route: '/'},
        {icon: 'mdi-emoticon-lol', text: 'Jokes', route: '/jokes'},
        {icon: 'mdi-account-group', text: 'About', route: '/about'}
      ],
    }),
  }
</script>
