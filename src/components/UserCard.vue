<template>
  <div class="user-card">
    <div class="user-card-image">
      <img :src="user.image" :alt="user.firstName" />
    </div>
    <div class="user-card-details">
      <h3>{{ user.firstName }} {{ user.lastName }}</h3>
      <p>{{ user.age }} años</p>
      <p>{{ user.email }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.user-card {
  display: flex;
  align-items: center;
  transition: transform 0.3s ease;
}

.user-card:hover {
  cursor: pointer;
  transform: scale(1.1);
}

.user-card-image img {
  width: 100px;
  height: 100px;
  object-fit: cover;
  border-radius: 50%;
  margin-right: 10px;
}

.user-card-details {
  flex-grow: 1;
  margin-top: 20px;
}

.user-card-details h3 {
  margin: 0;
}

.user-card-details p {
  margin: 5px 0;
}
</style>
