<template>
  <div class="about">
    <h1 class="grey--text mb-10">
      <v-icon left class="grey--text">mdi-account-group</v-icon>
      <span>About</span>
    </h1>
    <p>This is an app that displays corny Ragnarok Jokes</p>
  </div>
</template>

<script>
  export default {
    name: 'about',
    head(){
      return {
        title: 'About',
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: 'Best place for corny Ragnarok Jokes'
          }
        ]
      }
    }
  }
</script>

