<template>
  <div class="list">
    <h1>{{title}}</h1>
    <table align="center">
      <tr v-for="(todo,index) in todoList" :key="index">
        <td><input type="checkbox" v-show="todo.do !=''" v-model="todo.checkbox"></td>
        <td class="" v-bind:class="{done : todo.checkbox}">{{todo.do}}</td>
        <td><button v-show="todo.do !=''" v-on:click="delTodo(index)">X</button></td>
      </tr>
    </table>
    <input id="add" type="text" v-model="todos" />
    <button id="submit" v-on:click="addTodo()">add</button>
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
        todos:''
      }
    },
    methods: {
      addTodo: function(){
        this.todoList.push({checkbox: false, do: this.todos, deleteFlg: false});
        this.todos = "";
      },
      delTodo: function(index){
        this.todoList[index].deleteFlg = true;
        this.todoList.splice(index,1);
      }
    },
  }
</script>

<style>
#app{
  font-family: 'Avenir', Helvetia, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  text-align: center;
  color: #2c3e50;
}

#add{
  background-color: white;
  height: 20px;
  width: 200px;
}

#submit{
  background-color: orange;
  height: 26px;
}

.done{
  text-decoration: line-through;
}

</style>
