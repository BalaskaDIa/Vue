<template>
  <tr>
      <td>{{nev}}</td>
      <td>{{ev}}</td>
      <td>{{kiado}}</td>
      <td>{{free}}</td>
    <td><button @click="Delete">Törlés</button></td>

  </tr>
</template>

<script>
export default {
    props: ['Tabla'],
    data() {
        return {
            nev: this.Tabla.nev,
            ev: this.Tabla.ev,
            kiado: this.Tabla.kiado,
            free: this.Tabla.free,
        }
    },
methods: {
        Delete(){
            this.$emit('Tabla-torles',{original: this.Tabla})
        }
    }
}
</script>