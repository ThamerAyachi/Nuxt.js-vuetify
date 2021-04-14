<template>
  <div class="Jokes">
    <h1 class="grey--text mb-3">
      <v-icon right class="grey--text">mdi-emoticon-lol</v-icon>
      <span>Jokes</span>
    </h1>
    <div>
      <SearchJokes class="mb-10" v-on:search-text="searchText"/>
    </div>
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
  </div>
</template>

<script>
  import axios from 'axios'
  import Joke from '@/components/Joke'
  import SearchJokes from '@/components/SearchJokes'

  export default {
    data() {
      return {
        jokes: []
      }
    },
    components :{
      Joke,
      SearchJokes
    },
    async fetch(){
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }
      try {
        const res = await axios.get('https://icanhazdadjoke.com/search', config);
        this.jokes = res.data.results;
      } catch(err) {
        console.log(err)
      }
    },
    methods: {
      async searchText(text) {
        const config = {
          headers: {
            'Accept': 'application/json'
          }
        }
        try {
          const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
          this.jokes = res.data.results;
        } catch(err) {
          console.log(err)
        }
      }
    },
    head(){
      return {
        title: 'All Jokes',
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

