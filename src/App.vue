<script>
export default {
  data() {
    return {
      message: "Hello World!",
      helloClass: "title",
    }
  }
}
</script>

<template>
  <h1 v-bind:class="helloClass">{{ message }}</h1>
</template>

<style>
.title {
  color: red;
}
</style>