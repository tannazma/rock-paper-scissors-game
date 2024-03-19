<template>
  <div>
    <h2>Choose Your Move:</h2>
    <button @click="choose('rock')">🪨</button>
    <button @click="choose('paper')">🧻</button>
    <button @click="choose('scissors')">✂️</button>
  </div>
</template>

<script>
export default {
  methods: {
    choose(move) {
      this.$emit('choice', move)
    }
  }
}
</script>

<!-- Styles can be added here -->
