<template>
  <div class="modal">
    <div class="modal-content">
      <div class="modal-image">
        <img :src="selectedUser.image" :alt="selectedUser.firstName" />
      </div>
      <h3>{{ selectedUser.firstName }} {{ selectedUser.lastName }}</h3>
      <p>Edad: {{ selectedUser.age }} años</p>
      <p>Email: {{ selectedUser.email }}</p>
      <p>Dirección: {{ selectedUser.address.address }}</p>
      <p>Ciudad: {{ selectedUser.address.city }}</p>
      <p>Teléfono: {{ selectedUser.phone }}</p>
      <p>Fecha de nacimiento: {{ selectedUser.birthDate }}</p>
      <p>Tipo sanguíneo: {{ selectedUser.bloodGroup }}</p>
      <button class="ui-btn" @click="closeModal"><span>Cerrar</span></button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    selectedUser: {
      type: Object,
      required: true
    }
  },
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}
</script>

<style scoped>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  backdrop-filter: blur(1px);
}

.modal-content {
  background-color: black;
  color: #f5f5f5;
  padding: 20px;
  border-radius: 5px;
}

.ui-btn {
  --btn-default-bg: rgb(41, 41, 41);
  --btn-padding: 15px 20px;
  --btn-hover-bg: rgb(51, 51, 51);
  --btn-transition: 0.3s;
  --btn-letter-spacing: 0.1rem;
  --btn-animation-duration: 1.2s;
  --btn-shadow-color: rgba(0, 0, 0, 0.137);
  --btn-shadow: 0 2px 10px 0 var(--btn-shadow-color);
  --hover-btn-color: #fac921;
  --default-btn-color: #fff;
  --font-size: 16px;
  /* 👆 this field should not be empty */
  --font-weight: 600;
  --font-family: Menlo, Roboto Mono, monospace;
  /* 👆 this field should not be empty */
}

/* button settings 👆 */

.ui-btn {
  box-sizing: border-box;
  padding: var(--btn-padding);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--default-btn-color);
  font: var(--font-weight) var(--font-size) var(--font-family);
  background: var(--btn-default-bg);
  border: none;
  cursor: pointer;
  transition: var(--btn-transition);
  overflow: hidden;
  box-shadow: var(--btn-shadow);
}

.ui-btn span {
  letter-spacing: var(--btn-letter-spacing);
  transition: var(--btn-transition);
  box-sizing: border-box;
  position: relative;
  background: inherit;
}

.ui-btn span::before {
  box-sizing: border-box;
  position: absolute;
  content: '';
  background: inherit;
}

.ui-btn:hover,
.ui-btn:focus {
  background: var(--btn-hover-bg);
}

.ui-btn:hover span,
.ui-btn:focus span {
  color: var(--hover-btn-color);
}

.ui-btn:hover span::before,
.ui-btn:focus span::before {
  animation: chitchat linear both var(--btn-animation-duration);
}

@keyframes chitchat {
  0% {
    content: '#';
  }

  5% {
    content: '.';
  }

  10% {
    content: '^{';
  }

  15% {
    content: '-!';
  }

  20% {
    content: '#$_';
  }

  25% {
    content: '№:0';
  }

  30% {
    content: '#{+.';}35%{content: '@}-?';
  }

  40% {
    content: '?{4@%';
  }

  45% {
    content: '=.,^!';
  }

  50% {
    content: '?2@%';
  }

  55% {
    content: '\;1}]';
  }

  60% {
    content: '?{%:%';
    right: 0;
  }

  65% {
    content: '|{f[4';
    right: 0;
  }

  70% {
    content: '{4%0%';
    right: 0;
  }

  75% {
    content: "'1_0<";
    right: 0;
  }

  80% {
    content: '{0%';
    right: 0;
  }

  85% {
    content: "]>'";
    right: 0;
  }

  90% {
    content: '4';
    right: 0;
  }

  95% {
    content: '2';
    right: 0;
  }

  100% {
    content: '';
    right: 0;
  }
}
</style>
