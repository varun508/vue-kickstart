<template>
  <div>
    <div>
      <br>
      <h3>{{ todo.task }}</h3>
      <p v-if="todo.completed">This is completed</p>
      <p v-if="!todo.completed">This is not completed</p>
      <br>
      <hr>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"]
};
</script>

<style>
</style>

