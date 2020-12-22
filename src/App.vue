<template>
  <div>
    <h1>Vue 3 Todo App</h1>
    <form @submit.prevent="addNewTodo">
      <label>New Todo</label>
      <input v-model="newTodo" name="newTodo" />
      <button>Add New Todo</button>
    </form>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <h3>{{ todo.content }}</h3>
      </li>
    </ul>
  </div>
</template>

<script>
// creates properties/variables/objects that respond to change and you can know when those things are changed
// object wrapper
import { ref } from "vue";

export default {
  setup() {
    // newTodo is similar to having a property in data that is initialized to an empty string
    const newTodo = ref("");
    const todos = ref([]);

    function addNewTodo() {
      todos.value.push({
        // id needs to be a unique value
        id: Date.now(),
        done: false,
        content: newTodo.value,
      });
    }

    return {
      // exposing variables to the template
      todos,
      newTodo,
      addNewTodo,
    };
  },
};
</script>

<style>
body {
  font-family: sans-serif;
  padding-top: 1em;
  padding-bottom: 1em;
  font-size: 2em;
  width: 80%;
  margin: 0 auto;
}
input,
textarea,
button,
p,
div,
section,
article,
select {
  display: "block";
  width: 100%;
  font-family: sans-serif;
  font-size: 1em;
  margin: 0.5em;
}
</style>
