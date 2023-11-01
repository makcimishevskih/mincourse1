<template>
  <h3>
    {{ text }}
  </h3>
  <hr />
</template>

<script>
export default {
  name: 'app-subtitle',
  props: {
    text: String
  }
}
</script>

<style scoped></style>
