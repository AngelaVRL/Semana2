<template>
  <div class="card">
    <img :src="character.image" :alt="character.name" />
    <h3>{{ character.name }}</h3>
    <p>Especie: {{ character.species }}</p>
    <p>Estado: {{ character.status }}</p>

    <button @click="mostrarInfo">Ver información completa</button>
  </div>
</template>

<script>
export default {
  props: {
    character: Object
  },
  methods: {
    mostrarInfo() {
      alert(JSON.stringify(this.character, null, 2))
    }
  }
}
</script>