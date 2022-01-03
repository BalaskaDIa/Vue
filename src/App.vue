<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Kedvenc videó-játékok listája</h1>
    <jatekok :Tablazat="Tablazat" @Tabla-hozzaadas="Created" @Tabla-torles="Deleted"/>
  </div>
</template>


<script>
import jatekok from './components/Jatekok.vue'

export default {
  name: 'App',
  components: {
    jatekok
  },
  data() {
    return {
      Tablazat: [
        {
          nev: 'Red Dead Redemption 2',
          ev: '2018-10-26',
          kiado: 'Rockstar Games',
          free: 'Nem'
        },
        {
          nev: 'Warframe',
          ev: '2013-03-25',
          kiado: 'Digital Extremes',
          free: 'Igen'
        },
        {
          nev: 'Detroit: Become Human',
          ev: '2018-05-25',
          kiado: 'Quantic Dream',
          free: 'Nem'
        },
      ]
    }
  },
  methods: {
    Created(e){
        this.Tablazat.push({nev: e.nev, ev: e.ev, kiado: e.kiado, free: e.free})
    },
    Deleted(e){
      this.Tablazat.splice(this.Tablazat.indexOf(e.original), 1);
      }
    }
  }
</script>

<style>
#app {
  margin-top: 60px;
}
img {
  width: 200px;
}
body {
  background: #1A5276;
  margin-left: 200px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: gainsboro;
}
</style>
