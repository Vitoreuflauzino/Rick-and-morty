<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListPersonagens from '../components/ListPersonagens.vue';

let personagens = reactive(ref([]));

onMounted (()=>{
  fetch("https://rickandmortyapi.com/api/character/")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results
  });
})
</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">
        </div>
        <div class="card">
    </div>
        <ListPersonagens
        v-for="personagem in personagens"
          :image="personagem.image"
          :key="personagem.name"
          :name="personagem.name"
          :url="personagem.url"
          :status="personagem.status"
          :species="personagem.species"
          :gender="personagem.gender"
          :location="personagem.location.name"
        />
      </div>
    </div>
  </main>
</template>
