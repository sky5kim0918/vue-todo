<template>
  <div class="add">
    <input
      type="text"
      placeholder="할 일을 입력해주세요"
      v-model="newTodoItem"
      v-on:keyup.enter="addTodoItem"
    />
    <button v-on:click="addTodoItem">
      <span>Add</span>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: ""
    };
  },
  methods: {
    addTodoItem() {
      if (this.newTodoItem !== "") {
        this.$emit("addItem", this.newTodoItem);
        this.clearInput();
      }
    },
    clearInput() {
      this.newTodoItem = "";
    }
  }
};
</script>