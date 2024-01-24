<script>
export default {
  name: 'App',
  data() {

    return {
      name: 'To Do List',
      toDo: [
        { text: 'Andare dal barbiere per tagliare i capelli', done: false },
        { text: 'Lavare il pavimento', done: false },
        { text: 'Fare la spesa', done: true },
        { text: 'Andare in palestra', done: false },
        { text: 'Lavare la macchina', done: false },
        { text: 'Inviare mail', done: false },
        { text: 'Comprare il pane', done: false },
        { text: 'Sbattere tappeti', done: false },
        { text: 'Ritirare al bancomat', done: false },
        { text: 'Fare gli esercizi di Boolean', done: true }
      ]
    };
  },
  methods: {
    // l'elemento cambia lo stato booleano dell'attributo 'done' al click
    toggleDone(index) {
      this.toDo[index].done = !this.toDo[index].done;
    },
    // al click sulla x recupera l'index del toDo e lo elimina
    removeTodo(index) {
      this.toDo.splice(index, 1);
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
        <button @click="removeTodo(index)">x</button>
      </li>
    </ul>
  </div>
</div>

</template>

<style>

</style>
