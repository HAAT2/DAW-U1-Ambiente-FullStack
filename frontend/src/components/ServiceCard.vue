<script setup>
defineProps({
  servicio: {
    type: Object,
    required: true
  }
})

const emit = defineEmits(['seleccionar'])
</script>

<template>
  <article class="service-card">
    <h3>{{ servicio.nombre }}</h3>
    <p>{{ servicio.descripcion }}</p>
    <p class="price">${{ servicio.precio }}</p>
    <button
      type="button"
      :aria-label="`Ver información de ${servicio.nombre}`"
      @click="emit('seleccionar', servicio)"
    >
      Ver información
    </button>
  </article>
</template>

<style scoped>
.service-card {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  background-color: var(--color-background-soft);
  border: 1px solid var(--color-border);
  transition:
    transform 0.2s,
    border-color 0.2s,
    box-shadow 0.2s;
}

.service-card:hover {
  transform: translateY(-4px);
  border-color: hsla(160, 100%, 37%, 1);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
}

.service-card h3,
.service-card p {
  margin: 0;
}

.price {
  font-size: 1.25rem;
  font-weight: bold;
  color: hsla(160, 100%, 37%, 1);
}

.service-card button {
  margin-top: auto;
  border: none;
  border-radius: 0.5rem;
  background-color: hsla(160, 100%, 37%, 1);
  color: #fff;
  font-weight: 600;
  transition: background-color 0.2s;
}

.service-card button:hover {
  background-color: hsla(160, 100%, 30%, 1);
}
</style>