<template>
  <div>
    <div id="header">
      <div id="main-container">
        <h2>To do's</h2>
      </div>
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
    Search, Todos, TodoAdd
  },
  data: function () {//Distribuir los datos a los componentes hijo
    return {
      todos:[
        {
          id: 0,
          task: "Comprar stand monitor",
          completed: false
        },
        {
          id: 1,
          task: "Cambiar collation MariaDB",
          completed: false
        },
        {
          id: 1,
          task: "Completar turoriales",
          completed: false
        }
      ],
      copyTodos:[],//Busqueda
      created: function () {
        // `this` hace referencia a la instancia vm
        console.debug('todos es: ' + this.todos)
        this.copyTodos=[... this.todos];//Copiar array con ES6
      }
    }
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
