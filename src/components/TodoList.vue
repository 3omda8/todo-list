<template>
  <ul>
    <TodoItem v-for="todo in todos" :key="todo.text" :todo="todo" />
  </ul>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
  components: { TodoItem },
  props: {
    todos: [],
  },
};
</script>
