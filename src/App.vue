<script>
export default {
  name: 'App',
  data() {

    return {
      toDo: [
        { text: 'Andare dal barbiere per tagliare i capelli', done: false },
        { text: 'Lavare il pavimento', done: false },
        { text: 'Fare la spesa', done: false },
        { text: 'Fare esercizi', done: true }
      ]
    };
  },
  methods: {
    toggleDone(index) {
      this.toDo[index].done = !this.toDo[index].done;
    }
  }
};

</script>

<template>
<ul class="toDoList">
  <li v-for="(todo, index) in toDo" :key="index" @click="toggleDone(index)" :class="{ 'completed': todo.done }">
    {{ todo.text }}
  </li>
</ul>

</template>

<style>

</style>
