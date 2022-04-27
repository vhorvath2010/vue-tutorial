<script>
export default {
    data() {
        return {
            titleClass: "title",
            counting: "",
            count: 0
        };
    },
    methods: {
        increment() {
            this.count++;
        }
    },
}
</script>

<template>
  <h1 :class="titleClass">Counter</h1>
  <input v-model="counting" placeholder="What are we counting?">
  <p v-if="counting">We are counting {{ counting }}</p>
  <button @click="increment">Count: {{ count }}</button>
</template>

<style>
.title {
  color: slateblue;
}
</style>