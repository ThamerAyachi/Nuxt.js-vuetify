<template>
  <nav>
    <!-- toolbar -->
    <v-app-bar color="white" flat >
      <!-- icon bar -->
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="grey--text"></v-app-bar-nav-icon>
      <!-- title bar -->
      <v-toolbar-title>
        <span class="font-weight-light grey--text">Jokes</span>
        <span class="grey--text">Ragnarok</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <!-- btn Menu -->
      <BtnMenu/>
    </v-app-bar>
    <!-- /toolbar -->

    <v-navigation-drawer v-model="drawer" temporary app color="red">
      <!-- list -->
      <v-list class="mt-10">
        <v-list-item-group >
          <!-- for in list item -->
          <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
            <!-- icon list -->
            <v-list-item-icon>
              <v-icon left class="white--text">{{link.icon}}</v-icon>
            </v-list-item-icon>
            <!-- text list -->
            <span class="white--text">{{link.text}}</span>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

  </nav>
</template>

<script>
import BtnMenu from '@/components/BtnMenu'

export default {
  name:'navbar',
  components: {
    BtnMenu
  },
  data() {
    return {
      drawer: false,
      links: [
        {icon: 'mdi-home', text: 'Home', route: '/'},
        {icon: 'mdi-emoticon-lol', text: 'Jokes', route: '/jokes'},
        {icon: 'mdi-account-group', text: 'About', route: '/about'}

      ],
    }
  },
}
</script>
