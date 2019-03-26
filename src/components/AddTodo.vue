<template>
  <div>
    <form @submit="addTodo">
      <input class="input-field" v-model="task" placeholder="Title" name="title" type="text">
      <input value="Submit" type="submit" class="btn">
    </form>
  </div>
</template>

<script>
import uuid from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      task: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: uuid.v4(),
        task: this.task,
        completed: false
      };

      this.$emit("add-todo", newTodo);
    }
  }
};
</script>


<style>
.btn {
  color: white;
  background-color: gray;
  font-family: Roboto;
  padding: 8px;
}

.input-field {
  padding: 0px;
  border: 20px;
  box-sizing: border-box;
}
</style>
