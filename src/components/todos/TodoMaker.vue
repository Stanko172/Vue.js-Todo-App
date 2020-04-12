<template>
    <div class="maker_box">
        <input type="text" v-model="title"/>
        <button @click.prevent="addTodo">Dodaj</button>
    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
    name: 'TodoMaker',
    data(){
        return{
            title: ''
        }
    },
    methods: {
        addTodo(){
            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false
            }
            this.$emit('new-todo',newTodo)
        }
    }
    
}
</script>

<style scoped>
    .maker_box{
        display: grid;
        grid-template-columns: 1fr auto
    }

    input{
        padding: 0.5em;
    }

    button{
        width: 7em;
    }
</style>