<template lang="pug">
  #app
    section.section
      nav.nav.has-shadow
        div.container
          input.input.is-large(
            type="text", 
            placeholder="Buscar canciones", 
            v-model="searchQuery")
          a.button.is-info.is-large(v-on:click="search") Buscar
          a.button.is-danger.is-large &times;

      div.container
        .columns
          .column(v-for="t in tracks") {{ t.name }} {{ t.artist }}
        .p 
          small {{ searchMessage }}
</template>

<script>
const tracks = [
  { name: "lala 1", artist: "lele1" },
  { name: "lala 2", artist: "lele1"},
  { name: "lala 3", artist: "lele1"},
]

export default {
  name: 'app',
  data () {
    return {
      searchQuery:'',
      tracks : []
    }
  },

  computed:{
    searchMessage() {
      return "Encotnrados: " + this.tracks.length 
    }
  },

  methods:{
    search (){
      this.tracks = tracks
    }
  }
}
</script>

<style lang="scss">
@import './scss/main.scss';
</style>
