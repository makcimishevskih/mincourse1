<template>
  <div class="container">
    <p>
      <button @click='getComments' class="btn primary">Загрузить комментарии</button>
    </p>
    <div class="card">
      <h2>{{ comments.length ? 'Комментарии' : "Тут пока нет комментариев" }}</h2>
      <ul class="list">
        <li v-for='comment in comments' :key='comment.id' class="list-item">
          <div>
            <small>{{ comment.name }}</small>
            <p>
              <strong>{{ comment.email }}</strong>
              {{ comment.body }}
            </p>
          </div>
        </li>
      </ul>
    </div>
    <div class="loader" v-if='loader'></div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'app-comments',
  props: {},
  data () {
    return {
      // comments
      comments: [],
      // status
      loader: false,
      error: null,
    }
  },
  methods: {
    async getComments () {
      try {
        this.error = null;
        const response = await axios.get('https://jsonplaceholder.typicode.com/comments?_limit=42')

        this.comments = response.data
        // console.log(response.data)
      } catch (err) {
        this.error = err.message;
      }
    },
  }
}
</script>

<style scoped></style>
