<template>
  <div>
      <ul class="list">
        <li v-for="(todo, index) in todos" :key="index"> {{ todo }} </li>
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
    }
}
</script>

<style>
.list{
    display: flex;
    flex-direction: column;
    padding: 20px 0;
}
</style>