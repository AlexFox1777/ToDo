<template>
  <div class="root"> 
      <div class="todo-container">
        <h1>Todo List</h1>
        <todo-list :todos="todos" @complete-todo="completeToDo"></todo-list>
      </div> 
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
            const newTodo = {
                name: todo,
                completed: false,
            }
            this.todos.push(newTodo)
        },
        completeToDo(id){
            this.todos[id].completed = !this.todos[id].completed
            console.log(this.todos[id].completed)
        }
    }
}
</script>
    
<style>
.root{
    width: 40%;
    margin: auto;
    border: 1px solid gray;
    padding: 2%;
    background: white;
}
.todo-container{
    min-height: 100px;
}

</style>