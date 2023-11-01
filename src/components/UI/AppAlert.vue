<template>
  <div class="alert card" v-if='alert'>
    <h3>{{ alert.title }}</h3>
    <p>{{ alert.text }}</p>
    <button class='btn' :class='alert.type' @click='$emit("close")'>Закрыть</button>
  </div>
</template>

<script>
export default {
  emits: ['close'],
  name: 'app-alert',
  props: {
    alert: Object
  }
}
</script>

<style scoped></style>
