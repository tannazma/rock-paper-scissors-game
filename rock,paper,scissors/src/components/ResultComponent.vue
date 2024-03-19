<template>
  <div>
    <h2>Result:</h2>
    <p v-if="result">{{ result }}</p>
  </div>
</template>

<script>
export default {
  props: {
    result: String
  }
}
</script>

<!-- Styles can be added here -->
