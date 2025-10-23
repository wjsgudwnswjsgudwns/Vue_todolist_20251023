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
      newTodo: "",
    };
  },
  methods: {
    //이벤트 처리 함수 선언
    submitTodo() {
      if (this.newTodo.trim() === "") {
        //참이면 공란 입력 불가!
        alert("할일을 입력하세요!");
        return;
      } else {
        this.$emit("add-todo", this.newTodo);
        //상위 컴포넌트인 App의 addTodo 메서드의 인수로 newTodo 전달하며 호출
        this.newTodo = ""; //newTodo 공백으로 초기화->input 입력창 공란으로 변경
      }
    },
  },
};
</script>

<style>
.todo-input {
  display: flex;
  gap: 10px;
  justify-content: center;
  margin-bottom: 20px;
}

.todo-input input {
  padding: 10px;
  border: 1px solid rgb(116, 114, 114);
  border-radius: 4px;
  font-size: 16px;
}

.todo-input button {
  padding: 8px 16px;
  background-color: coral;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}

.todo-input button:hover {
  background-color: rgb(221, 60, 2);
}
</style>
