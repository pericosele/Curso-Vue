<template>
 <div class="">
   <!--<h1><center>{{mensaje}} ! </center></h1>
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
     <textarea cols="30" rows="10" v-model= "inputform"></textarea>
     <input type="submit" value="Send">
   </form>
   <input type="text" @input= "cambiarParrafo" v-model= "inputform">
   <br>
   <p>{{parrafo}}</p>-->
  <!--<div class="contendor">
  <p>{{primertexto}} {{segundotexto}}</p>
  <p>{{textocompleto}}</p>

  <time>{{now}}</time>
  <br>
  <time>{{hoy}}</time>
  <br>
  <input type='text' name='' id='' v-model='tercertexto'>
  <button @click='cambiar()'>Cambiar</button>

  <select name='' id='' v-model='selection'>
  <option value="1">1</option>
  <option value="2">2</option>
  <option value="3">3</option>
  <option value="4">4</option>
  </select>
  <br>
  <br>
  <button @click='openDoor = !openDoor'></button>
  {{openDoor? 'cerrar': 'abrir'}}
  <br>
  <br>
  <img v-if='openDoor' src='https://picsum.photos/200/300' alt=''>
  <img v-else src='https://picsum.photos/200/300?grayscale' alt=''>

  <p v-for='(persona,index) in listaPersonas' :key="index">
    {{persona}}
 </div>-->
  <nuevo-componente v-for="(imagen, index)in imagenes" :key="index"
  :titulo="`imagen ${index +1}`"
  :descripcion="`Esta es la imagen ${index +1} `"
  :imagen="imagen"
  @mostrarAlerta="Alertar"
  />
 </div>

</template>
<script>
import NuevoComponente from '.components/NuevoComponente.Vue'
export default {
  components: { NuevoComponente },
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
      parrafo: '',
      primertexto: 'BIENVENIDO',
      segundotexto: 'al curso de vue',
      tercertexto: '',
      now: new Date(),
      selection: '',
      Contenedor: 'cerrado',
      openDoor: false,

      listaPersonas: ['juan', 'peter', 'bartolomeo', 'evaristo', 'jim'],

      imagenes: [
        'https://picsum.photos/id/870/200/300?grayscale&blur=2',
        'https://picsum.photos/id/870/200/300',
        'https://picsum.photos/id/860/200/300',
        'https://picsum.photos/id/560/200/300'
      ]
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
    },
    cambiar () {
      this.segundotexto = this.tercertexto
    },
    Alertar (data) {
      alert(data)
    }
  },
  computed: {
    textocompleto () {
      return this.primertexto + ' ' + this.segundotexto
    },
    hoy () {
      return this.now.toLocaleDateString()
    }
  },
  watch: {
    selection (value, old) {
      console.console.log('Se hizo un cambio', value, '-', old)
    },
    openDoor (value) {
      alert('Watcher activado ')
      value ? (this.contenedor = 'abierto') : (this.contendor = 'cerrado')
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
.verde{
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
.cerrado{
  background-color: red;
  padding: 10px;
  border: 5px solid black;
}
.abierto{
  background-color: green;
  padding: 10px;
  border: 5px dotted black;
}
</style>
