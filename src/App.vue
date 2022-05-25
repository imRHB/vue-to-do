<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <!-- <to-dos /> -->
  <todo-list />
</template>

<script>
import TodoList from "./components/TodoList/TodoList.vue";
// import HelloWorld from "./components/HelloWorld.vue";
// import ToDos from "./components/ToDos.vue";

export default {
  name: "App",
  components: {
    TodoList,
    // HelloWorld,
    // ToDos,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
