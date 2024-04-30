<script setup>
    const personagem = defineProps(["name", "url","status","species","gender","location", "image"]);
    const personagens = personagem.url.split('/')[6];
    const imageUrl = "https://rickandmortyapi.com/documentation/#get-all-characters" + personagem + ".svg"
</script>



<template>
    <div class="col-md-4">
        <div class="card mb-3 p-2">
            <img :src="image" height="220" alt="...">
            <div class="card-body">
                <p class="card-title text-center">{{ personagem.name }}</p>
                <p class="card-text">Status: {{ status }}</p>
                <p class="card-text">Espécie: {{ species }}</p>
                <p class="card-text">Gênero: {{ gender }}</p>
                <p class="card-text">Localização: {{ location }}</p>
            </div>
        </div>
    </div>
</template>

<style>

</style>