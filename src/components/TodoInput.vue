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
    return {
      newTodo: "", // 초기값
    };
  },
  methods: {
    submitTodo() {
      if (this.newTodo.trim() === "") {
        alert("할 일을 입력 하세요");
        return;
      } else {
        this.$emit("add-todo", this.newTodo);
        //  상위 컴포넌트인 App의 addTodo 메소드의 인수로 newTodo 전달하여 호출
        this.newTodo = ""; // newTodo 초기화 -> input 창 포기화
      }
    },
  },
};
</script>

<style>
.todo-input {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-bottom: 20px;
}
.todo-input input {
  flex: 1;
  padding: 8px;
  border-radius: 8px;
}
button {
  padding: 8px 16px;
  background-color: #4caf50;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 8px;
}
button:hover {
  background-color: #45a049;
}
</style>
