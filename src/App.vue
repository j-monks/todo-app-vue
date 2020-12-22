<template>
<div>
  <h1>Vue 3 Todo App</h1>
  <form @submit.prevent="addNewTodo">
    <label>New Todo</label>
    <input name="newTodo" />
    <button>Add New Todo</button>
  </form>
</div>
</template>

<script>
export default {
  setup() {
    function addNewTodo() {
      console.log("Form was submitted");
    }

    return {
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
