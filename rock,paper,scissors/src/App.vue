<script setup lang="ts">
import { ref } from 'vue'
import GameComponent from './components/GameComponent.vue'
import ResultComponent from './components/ResultComponent.vue'
import ScoreBoard from './components/ScoreBoard.vue'

const userWins = ref(0)
const computerWins = ref(0)
const result = ref(null)

const handleChoice = () => {
  const randomNumber = Math.floor(Math.random() * 3)
  // 0: Lose, 1: Win, 2: Draw
  if (randomNumber === 0) {
    ResultComponent.value = 'Lose'
    computerWins.value++
  } else if (randomNumber === 1) {
    ResultComponent.value = 'Win'
    userWins.value++
  } else {
    ResultComponent.value = 'Draw'
  }
}

const resetGame = () => {
  userWins.value = 0
  computerWins.value = 0
  result.value = null
}
</script>

<template>
  <div id="app">
    <h1>Rock, Paper, Scissors</h1>
    <GameComponent @choice="handleChoice" />
    <div>
      <button @click="resetGame">Play Again</button>
    </div>
    <ScoreBoard :userWins="userWins" :computerWins="computerWins" />
    <div>
      <div v-if="userWins === computerWins">You are even</div>
      <div v-else>
        <div :style="{ color: userWins > computerWins ? 'black' : 'red' }">
          {{ userWins > computerWins ? 'You won!' : 'You lost!' }}
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
