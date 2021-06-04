<template>
    <div id="add-container">            
        <form @submit="addTodo">
            <input type="text" v-model="task">
        </form>
    </div>
</template>

<script>
import { uuid } from "vue-uuid";

export default{
    name:"TodoAdd",
    data(){
        return {
            task: ''
        }
    },
    methods:{
        addTodo(event){
            event.preventDefault();

            const newTodo={
                id:uuid.v4(),
                task:this.task,
                completed:false
            };
            
            this.task='';

            this.$emit('add-todo',newTodo);
        }
    }   
}
</script>

<style scoped>
#add-container{
    padding: 10px;
}

input{
    padding: 10px;
    outline: none;
    border: solid 1px #ccc;
    width: 100%;
}
</style>
