<template>
  <div class="home">
    <h1 class="grey--text mb-10">
      <v-icon class="grey--text" left>mdi-home</v-icon>
      <span>Home</span>
    </h1>
    <div class="card">
      <div class="card-text">
        <div class="title"><h2>Welcom in Ragnarok Jokes</h2></div>
        <span class="content">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Officia iusto ad saepe eligendi esse tenetur velit! Modi, facilis, ipsum atque distinctio officiis, molestias animi quae vero in reprehenderit ullam aperiam!
        </span>
        <v-btn color="white" class="mt-10 red--text" router to="/jokes" >Go TO Jokes</v-btn>
      </div>
    </div>

    <v-layout row class="mt-10">
      <v-flex md3 sm4 xs6 v-for="(photo, i) in photos" :key="i">
        <v-card flat class="ma-3">
          <!-- image -->
          <v-responsive class="pt-4">
            <v-avatar size="100" class="grey lighten-2" width="150" height="150">
              <img :src="require(`@/assets/images/${photo.name}`)">
            </v-avatar>
          </v-responsive>

          <!-- text -->
          <v-card-text>
            <div class="subheading">
              <span>{{photo.text}}</span>
            </div>
          </v-card-text>
          <!-- card action -->
          <v-card-actions>
            <v-btn right color="red" text @click="Onlike(i)">
              <v-icon class="red--text" left>{{photo.like}}</v-icon>
              <span>Like</span>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
  export default {
    name: 'Home',
    data() {
      return {
        photos: [
          {name: 'img1.jpeg', alt: 'photo1', text: 'Colonel', like: 'mdi-thumb-up-outline'},
          {name: 'img2.jpeg', alt: 'photo2', text: 'Crumbles', like: 'mdi-thumb-up-outline'},
          {name: 'img3.jpeg', alt: 'photo3', text: 'Diesel', like: 'mdi-thumb-up-outline'},
          {name: 'img4.jpeg', alt: 'photo4', text: 'Speedy', like: 'mdi-thumb-up-outline'},
          {name: 'img5.jpeg', alt: 'photo5', text: 'Freak', like: 'mdi-thumb-up-outline'},
          {name: 'img6.jpeg', alt: 'photo6', text: 'Dot', like: 'mdi-thumb-up-outline'},
          {name: 'img7.jpeg', alt: 'photo7', text: 'Figgy', like: 'mdi-thumb-up-outline'},
          {name: 'img8.jpeg', alt: 'photo8', text: 'Red Hot', like: 'mdi-thumb-up-outline'},
        ],
        dislike: 'mdi-thumb-up-outline',
        like: 'mdi-thumb-up',
      }
    },
    methods: {
      Onlike(i) {
        if (this.photos[i].like == this.dislike) {
          this.photos[i].like = this.like
        }else{
          this.photos[i].like = this.dislike
        }
      }
    },
    head(){
      return {
        title: 'Home',
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

