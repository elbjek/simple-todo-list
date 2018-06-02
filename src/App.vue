<template>
  <div id="app">

    <todo />
  </div>
</template>

<script>
import Todo from './components/todo.vue'

export default {
  name: 'app',
  components: {
    Todo
  }
}
</script>

<style>
body{
    background-color: #FBFCFF;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #2c3e50; */
  margin-top: 60px;

}
</style>
