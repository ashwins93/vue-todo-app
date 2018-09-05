<template>
  <div>
    <ul>
      <li v-for="todo in todos" v-bind:key="todo.id">
        {{ todo.text }}
        <span class="delete-button" v-on:click="deleteTodo(todo.id)">&times;</span>
      </li>
    </ul>
    <input type="text" placeholder="Add new todo" v-model="input" v-on:keydown.enter="addTodo"/>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  data: function() {
    return {
      todos: [
        { id: 0, text: 'Learn JavaScript' },
        { id: 1, text: 'Learn Vue' },
        { id: 2, text: 'Build something awesome' },
      ],
      input: ''
    };
  },
  methods: {
    addTodo: function(event) {
      this.todos.push({
        id: Date.now(),
        text: this.input
      });
      this.input = '';
    },
    deleteTodo: function(id) {
      this.todos.splice(this.todos.findIndex(todo => todo.id ===  id), 1);
    }
  }
};
</script>


<style scoped>
ul {
  list-style-type: none;
  border-bottom: 1px solid #eee;
  margin-bottom: 2rem;
}
li {
  list-style: none;
  padding: 2rem 1rem;
  border-top: 1px solid #eee;
  cursor: pointer;
  position: relative;
}
.delete-button {
  position: absolute;
  top: 50%;
  right: 1rem;
  transform: translateY(-50%);
  cursor: pointer;
}
input {
  display: block;
  padding: 1rem;
  width: 100%;
  border: none;
  font-size: inherit;
  font-family: inherit;
  border-radius: 3px;
  background-color: rgba(255, 255, 255, 0.5);
  border-bottom: 2px solid orangered;
  transition: all 0.2s;
}
input::placeholder {
  color: #777;
}
input:focus {
  outline: none;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.4);
}
</style>
