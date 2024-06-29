<template>
  <li :class="{ completed: todo.completed }">
    <input type="checkbox" v-model="todo.completed" />
    <span>{{ todo.text }}</span>
  </li>
</template>

<script>
export default {
  props: {
    todo: {},
  },
};
</script>

<style scoped>
input {
  margin-top: 8px;
  width: 20px;
}
input[type="checkbox"] {
  width: 16px;
  height: 16px;
  margin: 5px;
}
span {
  font-size: 24px;
  font-weight: bold;
  margin-left: 4px;
}
</style>
