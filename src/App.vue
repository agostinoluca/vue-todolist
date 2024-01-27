<script>
export default {
  name: 'App',
  data() {

    return {
      name: 'To Do List',
      newTodo: '',
      error: '',
      toDo: [
        { text: 'Andare dal barbiere per tagliare i capelli', done: false },
        { text: 'Fare la spesa', done: true },
        { text: 'Lavare la macchina', done: false },
        { text: 'Inviare mail', done: false },
        { text: 'Fare gli esercizi di Boolean', done: true }
      ],
      finish: 'Non hai nulla da fare. STUDIA! 🤓'
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
    },
    // aggiunge al array toDo l'input di newTodo (seguendo una condizione)
    addTodo() {
      if (this.newTodo.trim() !== '' && this.newTodo.length > 3) {
        this.toDo.push({ text: this.newTodo, done: false});
        this.error = '';
      } else if (this.newTodo.length <= 3) {
        this.error = 'Add at least 4 characters.';
      } else {
        this.error = 'You entered an invalid input.';
      };
      this.newTodo = '';
    },
  }
};

</script>

<template>
<div class="container mt-5">
  <div class="card p-3 w-75 m-auto">
    <div class="d-flex justify-content-around align-items-center">
      <h1 class="text-center">{{ name }}</h1>
      <div>
        <div class="d-flex gap-1 ">
          <input v-model="newTodo" type="text" name="newTodo" id="newTodo" placeholder="add new To Do here" @keypress.enter="addTodo">
          <button class="p-1" @click="addTodo">Add</button>
        </div>
        <div class="d-flex">
          <span class="text-danger"> {{ error }} </span>
        </div>
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
      <h3 class="finish fs-3 text-success p-5 text-center"> {{ finish }} </h3>
    </div>
  </div>
</div>

</template>

<style>

</style>
