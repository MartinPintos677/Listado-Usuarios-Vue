<template>
  <div class="navbar">
    <div class="logo">
      <img alt="Vue logo" src="../assets/logo.png" />
    </div>
    <button>Login</button>
  </div>
</template>

<script>
export default {
  name: 'NavigationBar'
}
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  background-color: #212f45;
  border-bottom: 1px solid #333;
}

.logo {
  margin-left: 52px;
}

.logo img {
  width: 50px;
  height: auto;
}

/*.btn-login {
  padding: 8px 16px;
  font-size: 14px;
  background-color: #e83e8c;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin-right: 117px;
}*/

button {
  --green: #1bfd9c;
  margin-right: 117px;
  font-size: 15px;
  padding: 0.7em 2.7em;
  letter-spacing: 0.06em;
  position: relative;
  font-family: inherit;
  border-radius: 0.6em;
  overflow: hidden;
  transition: all 0.3s;
  line-height: 1.4em;
  border: 2px solid var(--green);
  background: linear-gradient(
    to right,
    rgba(27, 253, 156, 0.1) 1%,
    transparent 40%,
    transparent 60%,
    rgba(27, 253, 156, 0.1) 100%
  );
  color: var(--green);
  box-shadow: inset 0 0 10px rgba(27, 253, 156, 0.4),
    0 0 9px 3px rgba(27, 253, 156, 0.1);
}

button:hover {
  color: #82ffc9;
  box-shadow: inset 0 0 10px rgba(27, 253, 156, 0.6),
    0 0 9px 3px rgba(27, 253, 156, 0.2);
  cursor: pointer;
}

button:before {
  content: '';
  position: absolute;
  left: -4em;
  width: 4em;
  height: 100%;
  top: 0;
  transition: transform 0.4s ease-in-out;
  background: linear-gradient(
    to right,
    transparent 1%,
    rgba(27, 253, 156, 0.1) 40%,
    rgba(27, 253, 156, 0.1) 60%,
    transparent 100%
  );
}

button:hover:before {
  transform: translateX(15em);
}
</style>
