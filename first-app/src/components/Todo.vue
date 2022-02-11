<template>
  <div>
      <h1>Todo List</h1>
      <input v-model="val" type="text">
      <button v-on:click="handleClick">Add todo</button>
      <div v-for="List in todos" :key="List.id">
          <h1>{{List}}</h1>
      </div>
  </div>
</template>

<script>
export default {
  name: "Todo",
  data(){
      return{
          todos: [],
          val: ""
      }
  },
  methods:{
      handleClick(){
          this.todos.push(this.val);
          this.val = ""
          console.log(this.todos);
      }
  }
};
</script>
