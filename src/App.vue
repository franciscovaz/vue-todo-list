<template>
  <div id="app">
    <Header />
    <AddTodo />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import AddTodo from './components/AddTodo';
import Todos from './components/Todos';

export default {
  name: 'App',
  components: {
    Header,
    AddTodo,
    Todos,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Todo One',
          completed: false,
        },
        {
          id: 2,
          title: 'Todo Two',
          completed: true,
        },
        {
          id: 3,
          title: 'Todo Tree',
          completed: false,
        },
      ],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
