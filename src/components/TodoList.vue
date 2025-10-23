<template>
  <ul class="todo-list">
    <li v-for="todo in todos" :key="todo.id" class="todo-item">
      {{ todo.content }}
      <button class="delete" @click="$emit('delete-todo', todo.id)">
        삭제
      </button>
    </li>
  </ul>
</template>

<script>
export default {
  props: ["todos"],
};
</script>

<style>
.todo-list {
  list-style: none;
  padding: 0;
}
.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #f0f0f0;
  padding: 10px;
  margin-bottom: 5px;
  border-radius: 5px;
}
.delete {
  background-color: #e74c3c;
  color: white;
  border: none;
  cursor: pointer;
  padding: 5px 8px;
}
.delete:hover {
  background-color: #c0392b;
}
</style>
