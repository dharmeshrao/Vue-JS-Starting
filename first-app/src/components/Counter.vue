<template>
  <div>
    <h1>Counter : {{ count }}</h1>
    <button v-on:click="Inc">Add One</button>
    <button v-on:click="Dec">Dec One</button>
  </div>
</template>

<script>
export default {
  name: "Counter",
  data() {
    return { show: true, count: 1 };
  },
  methods: {
    Dec() {
      this.count = --this.count;
    },
    Inc() {
      this.count = ++this.count;
    },
  },
};
</script>
