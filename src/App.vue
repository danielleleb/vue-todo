<template>
  <div>
    <to-do-list v-bind:todos="todos"></to-do-list>
    <create-todo v-on:add-todo="addTodo"></create-todo>
  </div>
</template>

<script>
import ToDoList from './components/ToDoList'
import CreateTodo from './components/CreateTodo'

export default {
  name: 'app',
  components: {
    ToDoList,
    CreateTodo
  },
  data() {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      },
      {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      },
      {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      },
      {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }]
    };
  },
  methods: {
    addTodo(data) {
      this.todos.push(data);
      console.log(this.todos);
    }
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
