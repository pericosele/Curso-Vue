<template>
 <div class="">
   <h1><center>{{mensaje}} ! </center></h1>
   <h2 :class="clasepruebas" v-text="texto"></h2>
   <p v-html="textohtml"></p>
   <input type="text" v-model="imputText">
   <br>
   <center><img :src="img" alt=""></center>
   <br>
   <br>
   <button @click="incrementarcontador()">
     Boton {{contador}}
   </button>
   <input type="text" @keyup="pressbutton()" v-model="inputEvent ">
   <select @change="cambiarcolor()" v-model="colorContenedor">
     <option value="contenedor rojo">rojo</option>
     <option value="contenedor verde">verde</option>
     <option value="contenedor purpura">purple</option>
     <option value="contenedor gris">gray</option>
   </select>
   <br>
   <div :class="contenedor"></div>
   <br>
   <form @submit="enviarFormulario">
     <input type="text" v-model="inputform">
     <!-- <textarea cols="30" rows="10" v-model= "inputform"></textarea> -->
     <input type="submit" value="Send">
   </form>
   <!-- <input type="text" @input= "cambiarParrafo" v-model= "inputform">-->
   <br>
   <p>{{parrafo}}</p>
 </div>
</template>
<script>
export default {
  name: 'App',
  data () {
    return {
      mensaje: 'Hola Vue ',
      texto: 'Hola mundo',
      textohtml: ' <a href="https://wax-metal-014.notion.site/Curso-VUE-JS-21c6d515f5b04698b04d5018b9524d2b"> Hola mundo pero en html </a> ',
      imputText: 'Escribe un texto',
      img: 'https://picsum.photos/200/300?grayscale',
      clasepruebas: 'texto-azul',
      contador: 0,
      inputEvent: '',
      contenedor: 'contenedor',
      colorContenedor: 'contenedor-verde',
      inputform: '',
      parrafo: ''
    }
  },
  methods: {
    incrementarcontador () {
      this.contador++
    },
    pressbutton () {
      alert(this.inputEvent)
    },
    cambiarcolor () {
      this.contenedor = this.colorContenedor
    },
    enviarFormulario () {
      this.parrafo = this.inputform
    },
    cambiarParrafo () {
      this.parrafo = this.inputform
    }
  }
}
</script>
<style>
.texto-azul{
  color: blue;
  background-color: orange;
}
.texto-rojo{
  color: red;
  background-color: pink;
}
.contenedor{
  width: 100px;
  height: 100px;
  background-color: white;
}
.verde
{
  background-color: green;
}
.rojo{
  background-color: red;
}
.purpura{
  background-color: purple;
}
.gris{
  background-color: gray;
}

</style>
