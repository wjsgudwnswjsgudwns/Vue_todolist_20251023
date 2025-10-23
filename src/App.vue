<template>
  <div id="app">
    <h1>Todo List</h1>
    <TodoInput @add-todo="addTodo" />
    <TodoList :todos="todos" @delete-todo="deleteTodo" />
  </div>
</template>

<script>
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";

export default {
  components: { TodoInput, TodoList },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    addTodo(newTodoText) {
      this.todos.push({
        id: Date.now(),
        content: newTodoText,
      });
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
      // 새로운 배열을 필터링해서 생성 -> 조건에 맞지 않는 요소들만 남김
    },
  },
};
</script>

<style>
.container {
  max-width: 400px;
  margin: 50px auto;
  text-align: center;
  font-family: "Noto Sans KR", sans-serif;
}
</style>
