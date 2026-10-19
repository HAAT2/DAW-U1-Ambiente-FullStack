<script setup>
import { useAuth } from '../services/auth'

const { user } = useAuth()
</script>

<template>
  <section class="dashboard">
    <div class="dashboard-hero">
      <div>
        <span class="badge">
          Panel principal
        </span>
        <h1>
          Bienvenido,
          {{ user?.nombre }}
        </h1>
        <p> Desde este espacio puedes consultar los módulos disponibles de la aplicación. </p>
      </div>
      <div class="hero-icon">
        <svg width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round">
          <path d="M12 2L2 7l10 5 10-5-10-5z"></path>
          <path d="M2 17l10 5 10-5"></path>
          <path d="M2 12l10 5 10-5"></path>
        </svg>
      </div>
    </div>

    <div class="dashboard-grid">
      <article class="dashboard-card card-blue">
        <div class="card-icon">
          <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <rect x="2" y="3" width="20" height="14" rx="2" ry="2"></rect>
            <line x1="8" y1="21" x2="16" y2="21"></line>
            <line x1="12" y1="17" x2="12" y2="21"></line>
          </svg>
        </div>
        <h2> Servicios </h2>
        <p> Consulta los servicios disponibles mediante la API.</p>
        <RouterLink to="/servicios" class="card-link">
          Consultar servicios →
        </RouterLink>
      </article>

      <article class="dashboard-card card-green">
        <div class="card-icon">
          <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
            <circle cx="12" cy="7" r="4"></circle>
          </svg>
        </div>
        <h2> Usuario </h2>
        <p class="user-handle">{{ user?.usuario }}</p>
        <strong class="user-role">{{ user?.rol }}</strong>
      </article>

      <article class="dashboard-card card-orange">
        <div class="card-icon">
          <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path>
          </svg>
        </div>
        <h2>Sesión</h2>
        <p>Acceso autenticado mediante el backend PHP.</p>
        <span class="session-active-indicator">Sesión activa</span>
      </article>
    </div>
  </section>
</template>
