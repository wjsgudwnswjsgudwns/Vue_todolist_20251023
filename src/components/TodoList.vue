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
  background-color: rgb(229, 241, 241);
  padding: 10px;
  margin-bottom: 5px;
  border-radius: 5px;
}

.delete {
  padding: 8px 16px;
  background-color: rgb(252, 80, 74);
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}

.delete:hover {
  background-color: rgb(204, 19, 12);
}
</style>
