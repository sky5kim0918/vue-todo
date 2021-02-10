<template>
  <ul>
    <li v-for="(todoItem, index) in propsdata" v-bind:key="todoItem.item">
      <label v-bind:for="todoItem.item">
        <p>{{ todoItem.item }} | {{ todoItem.date }}</p>
        <button v-on:click="removeTodo(todoItem, index)">
          <div>삭제</div>
        </button>
        <button v-on:click="updateTodo(todoItem, index)">
          <div>수정</div>
        </button>
      </label>
    </li>
  </ul>
</template>

<script>
export default {
  props: ["propsdata"],
  methods: {
    removeTodo(todoItem, index) {
      this.$emit("removeItem", todoItem, index);
    }
  }

};
</script>

<style>
 ul {list-style:none;} 
 </style>
