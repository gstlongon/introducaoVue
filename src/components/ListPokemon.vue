<script setup>
    const pokemon = defineProps(["name", "url"])
    const idPokemon = pokemon.url.split('/')[6]
    const imgUrl = `https://assets.pokemon.com/assets/cms2/img/pokedex/full/${idPokemon}.png`
    console.log(idPokemon)
    
</script>
    
<template>
    <div class="col-md-4">
        <div class="card mb-3">
            <p class="text-center"> {{ pokemon.name }}</p>
            <img  src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/024.png" alt=".." class="card-img-top">
            
        </div>
    </div>
</template>