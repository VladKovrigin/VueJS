<template>
  <div id="app" class="row justify-content-center">
    <todo-list class="row col-lg-6 col-12 justify-content-center flex-column"/>
  </div>
</template>

<script>
import todoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    todoList
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

html, body {
  margin: 5px;
  padding: 0;
  font-size: 20px;
}

li {
  list-style: none;
  margin: 5px 0;
}

.sort p {
  margin: 0 5px 0 0;
}
</style>
