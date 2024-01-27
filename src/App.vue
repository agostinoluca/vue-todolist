<script>
export default {
  name: 'App',
  data() {

    return {
      name: 'To Do List',
      newTodo: '',
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
    console.log(newTodo);
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
<div class="container mt-5">
  <div class="card p-3 w-75 m-auto">
    <div class="d-flex justify-content-around align-items-center">
      <h1 class="text-center">{{ name }}</h1>
      <div class="d-flex gap-1 ">
        <input v-model="newTodo" type="text" name="newTodo" id="newTodo" placeholder="add new To Do here">
        <button class="p-1">Add</button>
      </div>
    </div>
    <ul class="list-group fs-3" v-if="toDo.length > 0">
      <li class="list-group-item d-flex justify-content-between" v-for="(todo, index) in toDo" :key="index" @click="toggleDone(index)" :class="{ 'completed': todo.done }">
        {{ todo.text }}
        <span>
          <button @click="removeTodo(index)">x</button>
        </span>
      </li>
    </ul>
    <div v-else>
      <h3 class="finish fs-3 text-success">Non hai nulla da fare. STUDIA! &#128540 </h3>
    </div>
  </div>
</div>

</template>

<style>

</style>
