<template>
    <div class="user-list">
      <h2>Pilih User</h2>
      <button @click="fetchUsers" v-if="!users.length" class="btn btn-primary mb-3">Load Users</button>
      <ul class="list-group">
        <li
          v-for="user in users"
          :key="user.id"
          @click="selectUser(user)"
          class="list-group-item list-group-item-action"
        >
          {{ user.name }}
        </li>
      </ul>
    </div>
</template>
  
<script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        users: [],
      };
    },
    methods: {
      async fetchUsers() {
        const response = await axios.get('https://jsonplaceholder.typicode.com/users');
        this.users = response.data;
      },
      selectUser(user) {
        this.$emit('user-selected', user);
      },
    },
  };
</script>
  
<style scoped>
  .user-list {
    margin-bottom: 20px;
  }
  .list-group-item {
    cursor: pointer;
  }
  .list-group-item:hover {
    background-color: #f8f9fa;
  }
</style>
  