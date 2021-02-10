<template>
  <header>
    <h1>SKY Todo</h1>
    <p>{{ timestamp }}</p>
  </header>
</template>

<script>
import getDate from "../assets/commonJS/getDate.js";

export default {
  data() {
    return {
      timestamp: ""
    };
  },
  created() {
    this.timestamp = `${getDate().month}/${getDate().date} ${getDate().week}`;
  }
};
</script>