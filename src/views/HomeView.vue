<script setup>
//props - onMounted, reactive, ref
import { onMounted, reactive, ref } from 'vue';
import ListPokemon from '../components/ListPokemon.vue'

let pokemons = reactive(ref())

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon?limit=20&offset=0")
  .then(response => response.json())
  .then(response => {
    pokemons.value = response.results
    console.log(pokemons)
  })
})

</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-12 col-md-6">
          <div class="row">
            <div class="card" style="width: 18rem;">
              <img src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/025.png" alt=".." class="card-img-top">
              <div class="card-body">
                <h5 class="card-title">
                  Pikachu
                </h5>
                <p class="card-text">
                  
                </p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-sm-12 col-md-6">
          <div class="card">
            <div class="card-body row">
              <ListPokemon 
              v-for="pokemon in pokemons"
              :key="pokemon.name"
              :name="pokemon.name"
              :url="pokemon.url"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
    
  </main>
</template>
