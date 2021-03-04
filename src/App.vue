<template>
  <div id="app">
    <ToDoList v-bind:todos="todos"/>
    <CreateTodo @add-todo="addTodo"/>
  </div>
</template>

<script>
import ToDoList from './components/ToDoList.vue'
import CreateTodo from './components/CreateTodo.vue'
export default {
  name: 'App',
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
    }
  },
  methods: {
    addTodo(todo) {

      this.todos.push({
        title: todo.titleText,
        project: todo.projectText,
        done: false
      })

    }
  }
}
</script>

<style>
</style>
