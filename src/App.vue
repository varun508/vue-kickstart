<template>
  <div id="app" style="background-color: #eeeeee">
    <Todos v-bind:todos="todos"></Todos>
  </div>
</template>

<script>
import Todos from "./components/Todos";
export default {
  name: "app",
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          task: "Task number 1",
          completed: false
        },
        {
          id: 2,
          task: "Task number 2",
          completed: true
        },
        {
          id: 3,
          task: "Task number 3",
          completed: false
        },
      ]
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
