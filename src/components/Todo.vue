<template>
  <div class="list">
    <h1>{{title}}</h1>
    <p v-for="(todo,index) in todoList" :key="index">
      <input type="checkbox" v-show="todo.do !=''">{{todo.do}}
      <button v-show="todo.do !=''">X—</button>
    </p>
    <input id="submit" type="text" v-model="todos" />
    <button v-on:click="addTodo()">add</button>
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
        todoList:[
          {checkbox: false, do: '', deleteFlg: false}
        ],
        todos:'',

      }
    },
    methods: {
      addTodo: function(){
        this.todoList.push({checkbox: false, do: this.todos, deleteFlg: false});
        this.todos = "";
      }
    }
  }
</script>

<style>

</style>
