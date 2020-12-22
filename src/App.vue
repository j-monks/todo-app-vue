<template>
<div>
  <h1>Vue 3 Todo App</h1>
  <form @submit.prevent="addNewTodo">
    <label>New Todo</label>
    <input v-model="newTodo" name="newTodo" />
    <button>Add New Todo</button>
  </form>
  <h2>{{ newTodo }}</h2>
</div>
</template>

<script>
// creates properties/variables/objects that respond to change and you can know when those things are changed
import { ref } from 'vue';

export default {
  setup() {
    // newTodo is similar to having a property in data that is initialized to an empty string 
    const newTodo = ref("");

    function addNewTodo() {
      console.log("Form was submitted");
    }

    return {
      // exposing variables to the template
      newTodo,
      addNewTodo,
    };
  }
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
input, textarea, button, p, div, section, article, select {
  display: 'block';
  width: 100%;
  font-family: sans-serif;
  font-size: 1em;
  margin: 0.5em;
}
</style>
