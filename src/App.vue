<template>
  <div id="app">
    <h2>Todo list</h2>
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";

export default {
  name: "app",
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Go workout",
          completed: false
        },
        {
          id: 2,
          title: "Do laundry",
          completed: false
        },
        {
          id: 3,
          title: "Cook food",
          completed: false
        },
        {
          id: 4,
          title: "Clean up room",
          completed: false
        },
        {
          i: 5,
          title: "Finish work",
          completed: false
        }
      ]
    };
  },
  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    }
  }
};
</script>

<style>
#app {
  font-family: "Roboto", sans-serif;
  display: flex;
  flex-direction: column;
  text-align: center;
}
</style>
