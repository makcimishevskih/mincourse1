<template>
  <div class="avatar">
    <img :src='text' alt='avatar' />
  </div>
</template>

<script>
export default {
  name: 'app-avatar',
  props: {
    text: String,
  }
}
</script>

<style scoped></style>
