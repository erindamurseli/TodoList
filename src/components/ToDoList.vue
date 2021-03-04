<template>
<div>
  <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
  <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p> 
  
  <Todo v-on:delete-todo="deleteTodo" 
        v-on:complete-todo="completeTodo" 
        v-for="todo in todos" 
        :todo="todo" 
        :key="todo.id" 
        />
<!-- <todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo" v-for="todo in todos"  :key="todo.id"></todo> -->
</div>
</template>

<script>
import Todo from './Todo';

export default {
  components: {
    Todo
  },
  name: 'ToDoList',
  props: ['todos'],

  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      // console.log(todo);
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    
    },

  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
