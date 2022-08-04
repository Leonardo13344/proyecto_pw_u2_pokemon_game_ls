<template>
  <!--TODO Page-->
  <h1 v-if="!pokemonCorrecto">Espere por favor ...</h1>
  <div v-else>
    <!--<div v-if="pokemonCorrecto"></div>-->
    <h1>¿Quién es este pokemon?</h1>
    <PokemonPicture :pokemonId="pokemonCorrecto.id" :mostrarPokemon="mostrarPokemon" />
    <PokemonOptions :pokemons="pokemonArr" @eventoHijo="validarRespuesta($event)" />

    <div v-if="mostrarMensaje">
      <h1>{{ mensajeResultado }}</h1>
      <button v-on:click="resetearJuego">Nuevo Juego</button>
    </div>
  </div>
</template>

<script>

import PokemonOptions from './PokemonOptions'
import PokemonPicture from './PokemonPicture'
import getPokemonOptions from '@/helpers/obtenerOpcionesPokemon'

//getPokemonOptions()

export default {
  components: {
    PokemonPicture,
    PokemonOptions
  },
  data() {
    return {
      pokemonArr: [],
      pokemonCorrecto: null,
      mostrarPokemon: false,
      mensajeResultado: "",
      mostrarMensaje: false
    }
  },
  methods: {
    async cargaPokemonInicial() {
      this.pokemonArr = await getPokemonOptions()
      const numAleatorio = Math.floor(Math.random() * 4)
      console.log(numAleatorio)
      this.pokemonCorrecto = this.pokemonArr[numAleatorio]
      console.log('Impresion desde el page')
      console.log(this.pokemonArr)
    },
    validarRespuesta(pokemonSelected) {
      this.mostrarPokemon = true
      console.log("evento emitido")
      console.log(pokemonSelected)
      if (this.pokemonCorrecto.id === pokemonSelected) {
        console.log('correcto')
        this.mensajeResultado = `Correcto, ${this.pokemonCorrecto.nombre}`
      } else {
        console.log('incorrecto')
        this.mensajeResultado = `Error el Pokemon Correcto es: ${this.pokemonCorrecto.nombre}`

      }
      this.mostrarMensaje = true

    },
    resetearJuego() {
      this.pokemonArr = []
      this.pokemonCorrecto = null
      this.mostrarPokemon = false
      this.mensajeResultado = ""
      this.mostrarMensaje = false
      this.cargaPokemonInicial()
    }
  },

  mounted() {
    this.cargaPokemonInicial()
  }
}
</script>

<style>
</style>