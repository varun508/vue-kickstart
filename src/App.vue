<template>
  <div id="app" style="background-color: #eeeeee">
    <Header/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="delTodo"></Todos>
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import Header from "./components/layouts/Header.vue";
import AddTodo from "./components/AddTodo.vue";

export default {
  name: "app",
  components: {
    Todos,
    Header,
    AddTodo
  },
  methods: {
    delTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      this.todos = [...this.todos,newTodo];
    }
  },
  data() {
    return {
      todos: []
    };
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Roboto;
  line-height: 1.4;
}
</style>
