<template>
  <div>
    <!--v-bind para attach, para elemento del for debe ser identificado-->
    <div v-bind:key="item.id" v-for="item in todos">
        <div>{{ item.task }}</div>
    </div>
  </div>
</template>

<script>
//Definiendo componente
export default{
    name: 'Todos',
    props: ['todos']//Propiedades de tipo todos
}
</script>

<style>

</style>
