<template>
  <div>
    <div id="header">
      <Search v-on:query-change="querySearch"/>
    </div>
    <div id="main-container">
      <h2>To do's</h2>
      <!--Implementando coponentes-->
      <TodoAdd v-on:add-todo="addTodo"/>
      <Todos v-bind:todoslist="copyTodos" v-on:delete-todo="deleteTodo"/>
    </div>    
  </div>
</template>

<script>
import Search from './components/Search.vue'
import Todos from './components/Todos.vue'
import TodoAdd from './components/TodoAdd.vue'//Estructura de la aplicación

export default {
  name: 'App',
  components: {
    Todos, TodoAdd, Search
  },
  methods:{
    deleteTodo(id){
      this.todos=this.todos.filter(todo => todo.id != id);//Regresa todos los elementos, exepto el que se va a eliminar
      this.copyTodos=[... this.todos];
    },
    addTodo(todo){
      this.todos.push(todo);
      this.copyTodos=[... this.todos];
    },
    querySearch(query){
      if (query.trim()==='') {
        this.copyTodos=[... this.todos]
      } else {
        const temp=this.todos.filter(todo =>{
          return todo.task.includes(query);
        });

        this.copyTodos=[... temp]
      }
    }
  },
  data(){
    return{
      todos:[
        {
          id:0,
          task:"Comprar stand para monitor",
          completed:false
        },
        {
          id:1,
          task:"Juego de Epic Games",
          completed:false
        },
        {
          id:2,
          task:"Terminar turoriales",
          completed:false
        },
        {
          id:3,
          task:"Descargar juego",
          completed:true
        }
      ],
      copyTodos:[]
    }
  },
  created(){
    this.copyTodos=[... this.todos]
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.5em;
  padding: 0;
  margin: 0;
}

#main-container{
  border: solid 1px #ccc;
  width: 600px;
  margin: 100px auto;
}

#header{
  background: black;
  padding: 10px;
}

h2{
  padding: 0 10px;
}
</style>
