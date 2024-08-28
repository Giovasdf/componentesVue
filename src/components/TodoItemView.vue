<template>
    <div class="todo-item">
      <p>{{ tarea }}</p>
      <button @click="$emit('eliminarTarea')">Eliminar</button>
    </div>
  </template>
  
  <script>
  export default {
    props: ["tarea"],
  }
  </script>
  