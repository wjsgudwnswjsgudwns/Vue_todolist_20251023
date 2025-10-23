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
