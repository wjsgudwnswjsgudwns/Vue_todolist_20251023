<template>
  <div class="todo-input">
    <input
      v-model="newTodo"
      placeholder="할일을 입력하세요"
      @keyup.enter="submitTodo"
    />
    <button @click="submitTodo">추가</button>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    submitTodo() {},
  },
};
</script>
