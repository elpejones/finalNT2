<template>
  <div>
   <span>Color: </span>
   <input @input="actualizarColor($event)" /> 
      <span>Fondo: </span>
         <input @input="actualizarFondo($event)" /> 
               <span>Size: </span>
         <input @input="actualizarTamaño($event)" /> 
  </div>
  <hr>
  <div>
       <span>Texto: </span>
   <input :value="texto"  @input="actualizarTexto($event), contarPalabras($event)" :style="{ 'color': color, 'fontSize': tamaño, 'backgroundColor': fondo }" /> 
         <h3>Cantidad de palabras: {{ cantPalabras }}</h3>
  </div>
  <hr>
<div>
    <table>
  <tr>
    <th>Numero de pregunta</th>
    <th>Respuesta</th>
  </tr>
  <tr>
    <td>1</td>
    <td>b,c</td>
  </tr>
  <tr>
    <td>2</td>
    <td>c</td>
  </tr>
    <tr>
    <td>3</td>
    <td>b</td>
  </tr>
    <tr>
    <td>4</td>
    <td>d</td>
  </tr>
    <tr>
    <td>5</td>
    <td>d</td>
  </tr>
</table>
  </div>
</template>

<script>
export default {
  name: 'Texto',
  props: {
    msg: String
  },
  data() {
    return {
      texto: '',
      cantPalabras: 0,
      tamaño: '10px',
      fondo: 'white',
      color: 'black'
    };
  },
  methods: {
    contarPalabras() {
      this.cantPalabras = this.texto.split(' ').filter((item) => item != '').length;
    },
    actualizarTexto(e) {
      this.texto = e.target.value
    },
    actualizarColor(e) {
      this.color = e.target.value
    },
    actualizarFondo(e) {
      this.fondo = e.target.value
    },
    actualizarTamaño(e) {
      this.tamaño = e.target.value
    }          
  },
  computed: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
