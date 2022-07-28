<template>
  <!--TODO Page-->
  <PokemonPicture :pokemonId="478" :mostrarPokemon="true"/>
  <PokemonOptions :pokemons="pokemonArr"/>
</template>

<script>

import PokemonOptions from './PokemonOptions'
import PokemonPicture from './PokemonPicture'
import getPokemonOptions from '@/helpers/obtenerOpcionesPokemon'

//getPokemonOptions()

export default {
components:{
    PokemonPicture,
    PokemonOptions
},
data(){
  return{
    pokemonArr:[]
  }
},
methods:{
  async obtenerPokemonsArreglo(){
    this.pokemonArr = await getPokemonOptions()
    console.log('Impresion desde el page')
    console.log(this.pokemonArr )
  }
},
mounted(){
  this.obtenerPokemonsArreglo()
}
}
</script>

<style>

</style>