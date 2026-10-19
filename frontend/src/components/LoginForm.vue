<script setup>
import { ref } from 'vue'

defineProps({
  loading: {
    type: Boolean,
    default: false
  },
  error: {
    type: String,
    default: ''
  }
})

const emit = defineEmits(['submit'])

const usuario = ref('')
const contrasena = ref('')
const errorLocal = ref('')

function enviarFormulario() {
  errorLocal.value = ''

  if (!usuario.value.trim()) {
    errorLocal.value = 'Captura el usuario.'
    return
  }

  if (!contrasena.value) {
    errorLocal.value = 'Captura la contraseña.'
    return
  }

  emit('submit', {
    usuario: usuario.value.trim(),
    contrasena: contrasena.value
  })
}
</script>

<template>
  <form class="login-form" @submit.prevent="enviarFormulario">
    <div class="form-header">
      <div class="login-icon">
        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect>
          <path d="M7 11V7a5 5 0 0 1 10 0v4"></path>
        </svg>
      </div>
      <h1>Iniciar sesión</h1>
      <p>
        Ingresa tus credenciales para acceder a la aplicación.
      </p>
    </div>

    <div class="field">
      <label for="usuario">Usuario</label>
      <input
        id="usuario"
        v-model="usuario"
        type="text"
        autocomplete="username"
        placeholder="Ej. admin"
      >
    </div>

    <div class="field">
      <label for="contrasena">Contraseña</label>
      <input
        id="contrasena"
        v-model="contrasena"
        type="password"
        autocomplete="current-password"
        placeholder="Ingresa tu contraseña"
      >
    </div>

    <p v-if="errorLocal || error" class="form-message error" role="alert">
      {{ errorLocal || error }}
    </p>

    <button class="btn btn-primary" type="submit" :disabled="loading">
      {{ loading ? 'Validando...' : 'Iniciar sesión' }}
    </button>
  </form>
</template>
