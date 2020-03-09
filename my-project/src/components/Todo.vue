<template>
  <div class="todo-container">
      <h1>Todo</h1>
      <todo-list :todos="todos"></todo-list>
      <create-todo @add-todo="addToDo"></create-todo>
  </div>
</template>

<script>
import TodoList from './TodoList.vue'
import CreateTodo from './CreateTodo.vue'
export default {
    components:{
        TodoList,
        CreateTodo,
    },
    name: 'Todo',
    data(){
        return {
            todos: []
        }
    },
    methods: {
        addToDo(todo){
            this.todos.push(todo)
        }
    }
}
</script>
    
<style>
.todo-container{
    border: 1px solid gray;
    width: 40%;
    margin: auto;
    padding: 2%;
}

</style>