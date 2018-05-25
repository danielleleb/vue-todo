<template>
    <div>
        <div class="ui basic content center aligned segment">
            <div class="ui basic green label">
                <i class="check circle icon"></i> Completed Tasks: {{todos.filter(todo => {return todo.done ===true}).length}}
            </div>
            <div class="ui basic red label">
                <i class="ellipsis horizontal icon"></i> Pending Tasks: {{todos.filter(todo => {return todo.done ===false}).length}}
            </div>
        </div>
        
        <todo v-on:complete-todo="completeTodo" v-on:delete-todo="deleteTodo" v-for="todo in todos" :key="todo.id" v-bind:todo="todo"></todo>
        
    </div>
</template>

<script type = "text/javascript" >

import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
      deleteTodo(todo) {
          const todoIndex = this.todos.indexOf(todo);
          this.todos.splice(todoIndex, 1);
      },
      completeTodo(todo) {
          const todoIndex = this.todos.indexOf(todo);
          this.todos[todoIndex].done = true;
    }
  }
};
</script>


<style>
    .centered {
        margin: auto;
    }

</style>

