<template>
  <nuxt-link :to="'jokes/' + id">
    <v-card color="white" flat class="joke">
      <v-card-text class="grey--text">
        <span>
          {{joke}}
        </span>
      </v-card-text>
    </v-card>
  </nuxt-link>
</template>

<script>
  export default {
    name : 'Joke',
    props: ['joke', 'id']
  }
</script>

<style lang="scss">
  a{
    text-decoration: none !important;
    .v-card {
      .v-card__text {
        color: #616161 !important;
      }
      margin:  10px 0 !important;
    }
  }

</style>

