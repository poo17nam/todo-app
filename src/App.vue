<template>
  <div id="app">
    <!-- v-bind directive is used to pass the data from main component to TodoList component -->
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    'todo-list' : TodoList,
    'create-todo' : CreateTodo
  },
  data() {
    return {
      todos : [
        {
          title : 'Todo A',
          project : 'Project A',
          done: false
        },
        {
          title : 'Todo B',
          project : 'Project B',
          done: true
        },
        {
          title : 'Todo C',
          project : 'Project C',
          done: false
        },
        {
          title : 'Todo D',
          project : 'Project D',
          done: false
        }
      ]
    }
  },
  methods : {
    addTodo(title) {
      this.todos.push({
        title,
        done: false
      });
    }
  }
}
</script>

<style>
#app {

}
</style>
