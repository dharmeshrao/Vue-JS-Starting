<template>
  <div>
    <h1>Todo List</h1>
    <input v-model="state" type="text" />
    <button v-on:click="handleTodo">Add Todo</button>
    <div v-for="one in todo" :key="one.id">
      <div>
        <h1>{{ one.name }}</h1>
        <button v-on:click="() => deleteTodo(one.id)">Delete</button>
        <button v-on:click="() => toggleTodo(one.id)">Toggle</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todo",
  data() {
    return {
      todo: [],
      state: "",
    };
  },
  methods: {
    handleTodo() {
      if (!this.state) return;
      const payload = {
        name: this.state,
        id: Math.random(),
        status: false,
      };
      this.todo.push(payload);
      this.state = "";
    },
    deleteTodo(e) {
        console.log(e);
      this.todo = this.todo.filter((l) => {
        return l.id !== e;
      });
    },
    toggleTodo(id) {
        console.log(this.todo);
    this.todo = this.todo.map((e)=>{
        if(e.id === id){
            return { ...e,status: false}
        }
        return e;
     })
    },
  },
};
</script>
