<script>
export default {
  name: 'App',
  data() {

    return {
      name: 'To Do List',
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
<div class="container">
  <div class="paper">
    <h1>{{ name }}</h1>
    <ul class="toDoList">
      <li v-for="(todo, index) in toDo" :key="index" @click="toggleDone(index)" :class="{ 'completed': todo.done }">
        {{ todo.text }}
      </li>
    </ul>
  </div>
</div>

</template>

<style>

</style>
