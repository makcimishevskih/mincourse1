<template>
  <div class="container column">
    <!-- FORM -->
    <app-form @submitForm='submitForm'></app-form>
    <!-- VIEW -->
    <app-view :items='items'></app-view>

  </div>

  <!-- COMMENTS WITH LOADER-->
  <app-comments></app-comments>
</template>

<script>

import AppView from './components/AppView'
import AppForm from './components/AppForm'
import AppComments from './components/AppComments'

export default {
  components: {
    AppForm,
    AppComments,
    AppView
  },
  data () {
    return {
      items: [],
    }
  },
  methods: {
    submitForm (item) {
      this.items.push(item)
    },
  },
  mounted () {
    // this.getComments()
  }
}
</script>

<style>
.avatar {
  display: flex;
  justify-content: center;
}

.avatar img {
  width: 150px;
  height: auto;
  border-radius: 50%;
}
</style>
