<template>
  <div>
    <div class="card">
      <h3>{{ todo.task }}</h3>
      <input type="checkbox" v-on:change="markCompleted" :checked="todo.completed">
      <br>
      <hr>
      <br>
      <button @click="$emit('del-todo',todo.id)">Delete</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markCompleted() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style>
.card {
  padding: 50px;
  border-radius: 12px;
  display: inline-block;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.15);
  margin: 20px;
  position: relative;
  background-color: white;
  margin-bottom: 50px;
  transition: all 0.2s ease-in-out;
}

.card:hover {
  /*box-shadow: 0 5px 22px 0 rgba(0,0,0,.25);*/
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.19), 0 6px 6px rgba(0, 0, 0, 0.23);
  margin-bottom: 54px;
}
</style>

