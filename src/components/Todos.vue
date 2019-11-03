<template>
  <div>
    <h2>Todo list</h2>
    <AddTodo v-on:add-todo="addTodo" />
    <ul>
      <li v-bind:key="todo.id" v-for="todo in todos">
        <Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)" />
      </li>
    </ul>
  </div>
</template>

<script>
import Todo from "./Todo";
import AddTodo from "./AddTodo";

export default {
  name: "Todos",
  components: {
    Todo,
    AddTodo
  },
  props: ["todos"]
};
</script>

<style scoped>
ul {
  margin: 0;
  padding: 0;
  text-align: left;
  display: flex;
  flex-direction: column;
  
}
li {
  list-style: none;
}
</style>