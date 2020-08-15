<template>
  <div id="app">
    <h1>{{ todoTitle }}</h1>
    <div class="wrap">
<!--      <p>{{ todo }}</p>-->
      <input type="text" v-model="todo" placeholder="type todo ...">
      <button @click="todoAdd">add</button>
      <ul>
        <li v-for="(tod, index) in todos" :key="tod">

          <input type="checkbox" id="checkbox" v-model="lis">
          <p :class="{active : lis}">{{tod}}</p>
          <button @click="todos.splice(index, 1)">delete</button>

        </li>
      </ul>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      todoTitle: "Todo App",
      todo: "",
      todos: [],
      lis: false
    }
  },
  methods: {
    todoAdd() {
      if(this.todo !==""){
      this.todos.push(this.todo)
      console.log(this.todos)
      this.todo=""
    }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  text-align: center;
}
.active{
  text-decoration: line-through;
}
</style>
