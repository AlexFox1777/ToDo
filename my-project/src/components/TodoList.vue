<template>
  <div>
      <ul class="list">
        <li v-for="(todo, index) in todos"
        :key="index"
        @click="complete(index)"
        :class="{'cmplt-todo': todo.completed, todo}"
        >
         {{ todo.name }} 
        </li>
      </ul>
  </div>
</template>

<script>
export default {
    name: "TodoList",
    props: {
        todos: {
            reuqired: true,
            type: Array
        }
    },
    methods: {
        complete(id){
            this.$emit('complete-todo', id)
        }
    }
}
</script>

<style>
.list{
    display: flex;
    flex-direction: column;
    padding: 20px 0;
    font-size: 2.3rem;
}
.todo{
    user-select: none;
}
.cmplt-todo{
    text-decoration: line-through;
}
</style>