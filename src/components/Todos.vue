<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
        <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo',todo.id)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "Todo",
  props: ["todos"],
  components: {
    TodoItem
  }
};
</script>

<style scoped>
</style>
