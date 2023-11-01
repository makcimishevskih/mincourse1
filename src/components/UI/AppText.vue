<template>
  <p>
    {{ text }}
  </p>
</template>

<script>
export default {
  name: 'app-text',
  props: {
    text: String
  }
}
</script>

<style scoped></style>
