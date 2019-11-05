<template>
<div id="app">
  
  
   <main id="todolist">
      <h1>
      </h1>
      <Todolist v-bind:todos="todos" 
      @remove-todo="removeTodo" v-if="todos.length"
        />
      <p class="emptylist" v-else>Empty</p>
      <Newtark @add-todo="addTodo"/>
    </main>
</div>
  
  
</template> 

<script>
import Todolist from './components/Todolist'
import Newtark from './components/Newtask'

export default {
   name: 'app',
  data() {
    return {
      todos: [
        
      ]
    }
  },
  mounted() {
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t=> t.id !== id)
    },
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
  components: {
   Todolist,Newtark
  }
 }

</script>

<style>

</style>
