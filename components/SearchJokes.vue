<template>
  <v-form @submit.prevent="OnSubmit" row>
    <v-layout row wrap>
      <v-flex md11 sm12 xs12>
        <v-text-field label="Search" v-model="text" ></v-text-field>
      </v-flex>
      <v-flex md1 sm12 xs12>
        <v-btn color="grey" block class="mt-3 ml-1" type="submit">
          <v-icon class="white--text">mdi-magnify</v-icon>
        </v-btn>
      </v-flex>
    </v-layout>
  </v-form>
</template>

<script>
  export default {
    name: 'SearchJokes',
    data() {
      return {
        text: ''
      }
    },
    methods: {
      OnSubmit() {
        this.$emit('search-text', this.text);
        this.text = "";
      }
    },
  }
</script>

<style lang="scss" scoped>

</style>
