<template>
  <div id="app">
    <app-header></app-header>
    <app-add-todo @addTodo="addTodo"></app-add-todo>
    <app-todos :todos="todos" @delTodo="deleteTodo"></app-todos>
  </div>
</template>

<script>
import Header from './components/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    appHeader: Header,
    appTodos: Todos,
    appAddTodo: AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Todo One',
          completed: false
        },
        {
          id: 2,
          title: 'Todo Two',
          completed: false
        },
        {
          id: 3,
          title: 'Todo Three',
          completed: false
        }
      ]
    }
  },
  methods: {
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
