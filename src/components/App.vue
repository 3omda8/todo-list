<template>
  <div class="all">
    <div class="container">
      <h1>My To-Do List</h1>
      <input
        class="msg"
        type="text"
        v-model="newTodoText"
        placeholder="Add a new task..."
      />
      <button @click="addTodo">Add</button>
      <TodoList :todos="todos" />
    </div>
  </div>
</template>

<script>
import TodoList from "./TodoList.vue";

export default {
  data() {
    return {
      todos: [],
      newTodoText: "",
    };
  },
  components: { TodoList },
  methods: {
    addTodo() {
      if (this.newTodoText.length > 0) {
        console.log("Adding todo:", this.newTodoText); // Log new text before push
        this.todos.push({
          text: this.newTodoText,
          completed: false,
        });
        this.newTodoText = "";
        console.log("Todos array:", this.todos); // Log updated todos array
      }
    },
  },
};
</script>

<style>
body {
  background-color: #8de2ff;
  background-repeat: no-repeat;
  max-width: 100%;
}
.all {
  display: flex;
  justify-content: center;
  height: 98vh;
  align-items: center;
}
::-webkit-scrollbar {
  display: none;
}
.container {
  width: fit-content;
  height: 80%;
  background-color: rgb(209, 227, 237);
  border-radius: 20px;
  padding: 20px;
  margin: 20px;
}
.container h1 {
  text-align: center;
}
.msg {
  width: 220px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 20px;
  font-size: 16px;
  color: #333;
  background-color: #fff;
  margin-bottom: 10px;
}

input:focus {
  outline: none;
  box-shadow: 0 0 3px rgba(0, 0, 0, 0.2);
}

button {
  background-color: #458bce; /* Green */
  border: none;
  color: white;
  padding: 8px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 8px 4px 16px;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background-color: #35a0f8; /* Green with slight darkening on hover */
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

li {
  margin-bottom: 10px;
}

.completed {
  text-decoration: line-through;
  color: #ccc;
}
</style>
