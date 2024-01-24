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
  <li>
    {{ toDo }}
  </li>
</ul>

</template>

<style>

</style>
