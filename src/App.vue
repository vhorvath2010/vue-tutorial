<script>
export default {
  data() {
    return {
      message: "Hello World!",
      helloClass: "title",
      count: 0,
    }
  },
  methods: {
    increment() {
      this.count++;
    }
  }

}
</script>

<template>
  <h1 :class="helloClass">{{ message }}</h1>
  <button @click="increment">{{ "Count: " + count }}</button>
</template>

<style>
.title {
  color: red;
}
</style>