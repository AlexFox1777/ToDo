<template>
  <form @submit.prevent="onSubmit" >
      <input required v-model="todo" class="field"/>
      <input type="submit" value="Create  a TODO" class="btn"/>
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

<style scoped>
.field{
    width: 70%;
    padding: 0;
    margin: 0;
    border: none;
    height: 2rem;
    border-bottom: 1px solid violet;
}
.btn{
    width: 29%;
    height: 2rem;
    background: rgb(145, 53, 206);
    color: white;
    border: 0;
}
</style>