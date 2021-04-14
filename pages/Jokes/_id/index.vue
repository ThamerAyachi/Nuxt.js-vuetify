<template>
  <div class="sjoke">
    <h1 class="grey--text mb-5">Singel Joke</h1>
    <v-btn color="grey" class="white--text" text router to="/jokes">
      <v-icon left>mdi-arrow-left</v-icon>
      <span>go back</span>
    </v-btn>
    <v-card flat>
      <v-card-text>
        <span >{{joke}}</span>
        <br>
        <br>
        <small class="grey white--text pt-1 pb-1 pl-1 pr-1">
          Joke ID: {{$route.params.id}}
        </small>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    data() {
      return {
        joke: {}
      }
    },
    async fetch(){
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }
      try {
        const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
        this.joke = res.data.joke;
      } catch(err) {
        console.log(err)
      }
    },

    head(){
      return {
        title: this.joke,
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

<style lang="scss" scoped>
  .grey.white--text{
    border-radius: 2px;
  }

</style>
