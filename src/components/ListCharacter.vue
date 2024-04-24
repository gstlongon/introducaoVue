<script setup>
import axios from 'axios';
import { ref, onMounted } from 'vue';

const characters = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get('https://rickandmortyapi.com/api/character?page=4');
    characters.value = response.data.results;
  } catch (error) {
    console.error('Erro ao buscar personagens:', error);
  }
});
</script>

<template>
  <div>
    <div class="row">
        <div class="col-sm-12 col-md-6" v-for="character in characters" :key="character.id">
          <div class="card col-12 mb-3 shadow">
            <div class="row align-items-center">
                <div class="col-md-6 col-sm-12">
                    <img :src="character.image" :alt="character.name" class="card-img-top w-full object-fit-cover">
                </div>
                <div class="col-md-6 col-sm-12 p-4">
                    <p class=""><strong>Nome: </strong>{{ character.name }}</p>
                    <p class=""><strong>Status: </strong>{{ character.status }}</p>
                    <p class=""><strong>Espécie: </strong>{{ character.species }}</p>
                    <p class=""><strong>Gênero: </strong>{{ character.gender === 'Male' ? 'Masculino' : 'Feminino' }}</p>
                    <p class=""><strong>Localização: </strong>{{ character.location.name }}</p>
                    <p class=""><strong>Epsódios atuados: </strong>{{ character.episode.length }}</p>

                </div>
            </div>
          </div>
        </div>
    </div>
  </div>
</template>
