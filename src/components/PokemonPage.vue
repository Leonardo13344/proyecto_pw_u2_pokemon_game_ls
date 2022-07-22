<template>
  <!--TODO Page-->
  <PokemonPicture :pokemonId="478" :mostrarPokemon="true"/>
  <PokemonOptions />
</template>

<script>

import PokemonOptions from './PokemonOptions'
import PokemonPicture from './PokemonPicture'
export default {
components:{
    PokemonPicture,
    PokemonOptions
}
}
</script>

<style>

</style>