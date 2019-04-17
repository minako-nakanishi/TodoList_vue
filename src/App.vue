<template>
  <div id="app">
    <Todo title="Todo List"/>
  </div>
</template>

<script>
  import Todo from './components/Todo.vue'

  export default{
    name: 'app',
    components:{
      Todo
    }
  }
</script>
