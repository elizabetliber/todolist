<template>
  <div id="app">
    <h1><em>{{ todoTitle }}</em></h1>
    <div class="container">

      <div class="input-group">
        <input type="text" class="form-control mr-1" aria-label="Text input with checkbox" v-model="todo">
        <button @click="todoAdd" class="btn btn-success">+ add</button>
      </div>
      <div v-for="(tod, index) in todos" :key="tod">

        <div class="input-group mt-1">
            <div class="input-group-prepend">
              <div class="input-group-text">
                <input v-model="lis"  type="checkbox" aria-label="Checkbox for following text input">
              </div>
            </div>

          <input type="text" class="form-control mr-1" aria-label="Text input with checkbox" :class="{'active': lis}" :value="tod">
          <button @click="todos.splice(index, 1)" class="btn btn-danger">delete</button>

        </div>
        </div>

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
      if (this.todo !== "") {
        this.todos.push(this.todo.trim())
        console.log(this.todos)
        this.todo = ""
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
.container {
  width: 600px;
}
.active{
  text-decoration: line-through;
}
</style>
