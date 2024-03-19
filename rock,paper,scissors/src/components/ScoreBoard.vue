<template>
    <div>
      <h2>Scores</h2>
      <h3>User: {{ userWins }}</h3>
      <h3>Computer: {{ computerWins }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      userWins: Number,
      computerWins: Number
    }
  }
  </script>
  
  <!-- Styles can be added here -->
  