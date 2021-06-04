<template>
  <div>
    <div id="header">
      <div id="main-container">
        <h2>To do's</h2>
        <!--Implementando coponente-->
        <Todos v-bind:todos="copyTodos"/>
      </div>
    </div>
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
//import TodoAdd from './components/TodoAdd.vue'//Estructura de la aplicación

export default {
  name: 'App',
  components: {
    Todos
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
