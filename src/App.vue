
<template>
  <div class="container">
    <h1>PERSONAJES</h1>
    <h1>Rick and Morty</h1>

    <div class="grid">
      <CharacterCard
        v-for="character in characters"
        :key="character.id"
        :character="character"
      />
    </div>
  </div>
</template>

<script>
import CharacterCard from './assets/components/CharacterCard.vue'

export default {
  components: { CharacterCard },
  data() {
    return {
      characters: []
    }
  },
  mounted() {
    fetch('https://rickandmortyapi.com/api/character')
      .then(res => res.json())
      .then(data => {
        this.characters = data.results
      })
      .catch(error => {
        console.error('Error al consumir la API:', error)
      })
  }
}
</script>

