<script>
import HeaderView from './components/HeaderView.vue'
import HeroView from './components/HeroView.vue'
import PersonaView from './components/PersonaView.vue'
import TodoItemView from './components/TodoItemView.vue'
import ButtonView from './components/ButtonView.vue'
import CardView from './components/CardView.vue'

export default {
  data() {
    return {
      personas: [
        { foto: "https://avatars.githubusercontent.com/u/499550?v=4", nombre: "Evan You", descripcion: "Creador de Vue Js" },
        { foto: "https://cdn.britannica.com/99/124299-050-4B4D509F/Linus-Torvalds-2012.jpg?w=400&h=300&c=crop", nombre: "Linus Torvalds", descripcion: " Creador de Linux" },
        { foto: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQZ3LCoanmhnVe5TieG8TSzsNgO1Zte4Z1Pqg&s", nombre: "Robert C. Martin", descripcion: " Creador de Clean Code" }
        ,],
      tareas: [
        "Aprender Vue.js",
        "Contribuir a un proyecto open source",
        "Aprender Clean Code",
      ],
    }
  },
  components: {
    HeaderView,
    HeroView,
    PersonaView,
    TodoItemView,
    ButtonView,
    CardView
  },
  methods: {
    eliminarTarea(index) {
      this.tareas.splice(index, 1);
    }
  }
}
</script>

<template>
  <HeaderView />
  <!-- <HeroView/> -->
  <section class="personas">
    <div v-for="(persona, i) in personas" :key="persona">
      <PersonaView :foto="persona.foto" :nombre="persona.nombre" :descripcion="persona.descripcion"
        @eliminarPersona="personas.splice(i, 1)" />
    </div>
  </section>

  <section>
    <div v-for="(tarea, index) in tareas" :key="index">
      <TodoItemView :tarea="tarea" @eliminarTarea="eliminarTarea(index)" />
    </div>
  </section>

   <section>
    <ButtonView>
      <h3>Este es un slot</h3>
    </ButtonView>
  </section>


  <CardView imagen="https://via.placeholder.com/300">
    <h1>Mi Título</h1>
    <p>
      Esta es una breve descripción de la tarjeta.
    </p>
    <button>Ver Más</button>
  </CardView>
</template>

<style scoped>
.personas {
  width: 80%;
  margin: 30px auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
</style>
