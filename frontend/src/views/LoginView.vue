<script setup>
import LoginForm from '../components/LoginForm.vue'
</script>

<template>
  <section class="login-page">
    <div class="login-presentation">
      <span class="presentation-tag"> Desarrollo de Aplicaciones Web </span>
      <h2> Aplicación Full Stack </h2>
      <p>
        Interfaz desarrollada con Vue, conectada a un backend PHP mediante una API.
      </p>
      <div class="presentation-features">
        <span>✓ Vue 3</span>
        <span>✓ Docker</span>
        <span>✓ PHP</span>
        <span>✓ API</span>
      </div>
    </div>

    <div class="login-container">
      <LoginForm />
    </div>
  </section>
</template>
