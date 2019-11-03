<template>
  <div v-bind:class="{ 'completed' : todo.completed }">
    <p v-on:click="markComplete">{{ todo.title }}</p>
    <button @click="$emit('delete-todo', todo.id)">Delete</button>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.completed > p {
  text-decoration: line-through;
}
p {
  display: inline-block;
}
div {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
}
</style>