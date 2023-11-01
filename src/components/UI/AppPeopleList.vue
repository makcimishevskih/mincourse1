<template>
  <ul class='people-list'>
    <li v-for='people in peoples' :id='people.id' :key='people.id' class='card'>
      <span>
        User name is: <strong>{{ people.firstName }}</strong>
      </span>
      <button @click='$emit("deleteUser", people.id)' class='btn primary'>
        Delete user
      </button>
    </li>
  </ul>
  <div class='card' v-if='!peoples.length'>Нет пользователей</div>
</template>

<script>
export default {
  name: 'app-people-list',
  emits: ['deleteUser'],
  props: {
    peoples: Array
  },
  mounted () {
    this.peoples
  }
}
</script>

<style scoped>
.people-list {
  margin-top: 20px;
}

.people-item {
  margin-top: 12px;
}

button {
  margin-left: 20px;
  background-color: red;
  color: white;
}

.people-item:first-child {
  margin-top: 0px;
}
</style>
