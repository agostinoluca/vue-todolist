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
  }
};

</script>

<template>
<ul>
  <li v-for="(todo, index) in toDo" :key="index" :class="{ 'completed' : todo.done }">
    {{ todo.text }}
  </li>
</ul>

</template>

<style>

</style>
