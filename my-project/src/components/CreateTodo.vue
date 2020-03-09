<template>
  <form @submit.prevent="onSubmit">
      <input required v-model="todo"/>
      <input type="submit" value="Create  a TODO" />
  </form>
</template>

<script>
export default {
    name: 'CreateTodo',
    data(){
        return{
            todo: ""
        }
    },
    methods:{
        onSubmit(){
            this.$emit('add-todo', this.todo)
            this.todo = ''
        }
    }
}
</script>

<style>

</style>