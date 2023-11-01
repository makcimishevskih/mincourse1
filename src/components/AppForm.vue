<template>
  <form class="card card-w30" @submit.prevent='submitForm'>
    <div style='color: red' v-if='error'>{{ error }}</div>
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select v-model='select' id="type">
        <option value="" disabled>Выберите тип</option>
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea v-model='textarea' id="value" rows="3"></textarea>
    </div>

    <button :disabled='buttonAccess' class="btn primary">Добавить</button>
  </form>
</template>

<script>
export default {
  name: 'app-form',
  emits: ["submitForm"],
  data () {
    return {
      // inputs
      select: '',
      textarea: '',
      error: null
    }
  },
  methods: {
    submitForm () {
      const reg = /(http) ? s ?:? (\/\/[^"']*\.(?:png|jpg|jpeg|gif|png|svg))/i
      this.error = null

      if (this.select === 'avatar' && !(reg)
        .test(this.textarea)) {
        this.error = 'Please type correct image url'
      } else if (this.select) {
        this.$emit('submitForm', { tag: this.select, text: this.textarea })
      } else {
        this.error = 'Choose type of tag'
      }
    },
  },
  computed: {
    buttonAccess () {
      return this.textarea.length < 3
    }
  }
}
</script>

<style scoped></style>
