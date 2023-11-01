<template>
  <h1>
    {{ text }}
  </h1>
</template>

<script>
export default {
  name: 'app-title',
  props: {
    text: String
  }
}
</script>

<style scoped></style>
