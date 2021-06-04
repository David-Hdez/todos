<template>
  <div>
    <!--v-bind para attach, para elemento del for debe ser identificado-->
    <div v-bind:key="todo.id" v-for="todo in todoslist">
      <TodoItem v-bind:todo="todo" />      
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

//Definiendo componente
export default{
  name: 'Todos',
  props: ['todoslist'],//Propiedad de tipo todos
  components: {TodoItem}
}
</script>
