<template>
  <div class="card card-w70">
    <component v-for='(it, idx) in items' :key='idx' :is='`app-${it.tag}`' :text='it.text' />
  </div>
</template>

<script>
import AppTitle from './UI/AppTitle'
import AppText from './UI/AppText'
import AppSubtitle from './UI/AppSubtitle'
import AppAvatar from './UI/AppAvatar'

export default {
  name: 'app-view',
  components: {
    AppTitle,
    AppText,
    AppSubtitle,
    AppAvatar,
  },
  props: {
    items: Array
  }
}
</script>

<style scoped></style>
