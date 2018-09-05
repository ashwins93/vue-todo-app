<script>
import HelloWorld from './components/HelloWorld.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: 'app',
  components: {
    HelloWorld,
    TodoList,
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 62.5%;
}

body {
  font-size: 1.6rem;
  font-family: 'Lato', sans-serif;
  font-weight: 400;
  background-image: linear-gradient(to right, #607d8b, #90a4ae);
  color: #fafafa;
}

#app {
  padding: 5rem;
  max-width: 50rem;
  margin: 0 auto;
}
</style>

<template>
  <div id="app">
    <HelloWorld msg="To Do List"/>
    <TodoList />
  </div>
</template>
