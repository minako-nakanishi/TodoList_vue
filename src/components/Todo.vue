<template>
  <div class="list">
    <h1>{{title}}</h1>
    <p>{{todoList}}</p>
    <input type="text" v-model="todos" />
    <button>Click</button>
  </div>
</template>

<script>
  export default{
    name: 'Todo',
    props:{
      title: String
    },
    data: function(){
      return{
        todoList: '',
        todos:''
      }
    }
  }
</script>

<style>

</style>
