<template>
  <NavigationBar />
  <div class="app">
    <h1>Lista de Usuarios</h1>
    <div class="user-cards">
      <UserCard
        v-for="user in users"
        :key="user.id"
        :user="user"
        @click="openModal(user)"
      />
    </div>
    <UserModal
      v-if="selectedUser"
      :selectedUser="selectedUser"
      @close="closeModal"
    />
  </div>
</template>

<script>
import UserCard from './components/UserCard.vue'
import UserModal from './components/UserModal.vue'
import NavigationBar from './components/NavigationBar.vue'

export default {
  name: 'App',
  components: {
    UserCard,
    UserModal,
    NavigationBar
  },
  data() {
    return {
      users: [],
      selectedUser: null
    }
  },
  mounted() {
    this.fetchUsers()
  },
  methods: {
    fetchUsers() {
      fetch('https://dummyjson.com/users')
        .then(response => response.json())
        .then(data => {
          this.users = data.users
        })
        .catch(error => {
          console.error('Error fetching users:', error)
        })
    },
    openModal(user) {
      this.selectedUser = user
    },
    closeModal() {
      this.selectedUser = null
    }
  }
}
</script>

<style>
body {
  background-color: #f5f5f5;
  margin: 0;
}
.app {
  padding: 30px;
  margin: 8px;
}

h1 {
  font-size: 3rem;
  text-align: center;
}

.user-cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-gap: 20px;
}
</style>
