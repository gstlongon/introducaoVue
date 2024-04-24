<script setup>
import {ref} from 'vue'

</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
    <router-link class="navbar-brand" to="/"> <img src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Rick_and_Morty.svg" width="300" height="80" alt=""></router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item active">
          <router-link class="nav-link active" to="/" aria-current="page">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link active" to="/about" aria-current="page">Sobre nós</router-link>
        </li>
      </ul>
    </div>
   </div>
  </nav>

  <div class="main">
    <RouterView/>
  </div>
  <footer class="bg-dark text-light">
    <div class="">
      Unimar | ADS | {{ new Date().getFullYear() }}
    </div>
  </footer>
</template>
<style>

footer {
  width: 100%;
  height: 40px;
  margin-top: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
}

</style>