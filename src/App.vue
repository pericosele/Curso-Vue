<template>
 <div class="">
   <h1>{{imputText}} ! </h1>
   <h2 :class="clasepruebas" v-text="texto"></h2>
   <p v-html="textohtml"></p>
   <input type="text" v-model="imputText">
   <img :src="img" alt="">
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
      clasepruebas: 'texto-azul'
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
</style>
