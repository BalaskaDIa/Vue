<template>
  <table>
      <tr>
          <th><h1>Név</h1></th>
          <th><h1>Kiadási év</h1></th>
          <th><h1>Kiadó</h1></th>
          <th><h1>Ingyenes?</h1></th>
      </tr>
        <Tablazat
        v-for="Tabla in Tablazat"
        :key="Tabla.nev"
        :Tabla="Tabla"
        @Tabla-torles="Deleted"
        />
        <tr>
            <td><input type="text" v-model="nev"></td>
            <td><input type="date" v-model="ev"></td>
            <td><input type="text" v-model="kiado"></td>
            <td><input type="text" v-model="free"></td>
            <td><button @click="New">Felvétel</button></td>
        </tr>
  </table>
</template>

<script>
import Tablazat from './Tablazat.vue'
export default {
    props: ['Tablazat'],
    data() {
        return {
            nev: null,
            ev: null,
            kiado: null,
            free: null,
        }
    },
    components: {Tablazat},
    methods: {
        New(){
            this.$emit('Tabla-hozzaadas', {nev:this.nev, ev:this.ev, kiado:this.kiado, free:this.free} )
            this.nev = null 
            this.ev = null 
            this.kiado = null 
            this.free = null 
        },
        Deleted(e){
            this.$emit('Tabla-torles', e)
        }
    }
}
</script>
