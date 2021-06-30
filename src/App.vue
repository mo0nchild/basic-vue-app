<template>
  <div id="app">

    <InputField v-on:add-todos = "addTodos"/>
    <p>Click on Action to Delete</p>
    <TodoList v-bind:todos = "todos" v-on:delete-todo = "deleteTodo"/>
    
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';
import InputField from './components/InputField.vue';

export default {
  name: 'App',
  data(){
    return {
      todos: ['Work', 'Studing', 'Cocking', 'Sleeping'],
      isEmpty: false,
    }
  },
  components: {
    TodoList, InputField
  },
  methods: {
    deleteTodo(index){
      this.todos.splice(index, 1);
    },
    addTodos(item){
      this.todos.push(item);
    }
  },
  watch: {
    todos: function(){
      if(this.todos.length == 0)
      {
        this.todos = ['Empty'],
        this.isEmpty = true;
      }
    }
  }
}
</script> 

<style scoped>
  div{
    text-align: center;
    color: white;
    font-size: 20px;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  }
  
</style>
