<template>
    <div>
        <TodoMaker />
            <div v-for="todo in sortedTodos" :key="todo.id" class="todo-item">
                <div>
                    <input type="checkbox" @change="changeComplete(todo)"/>
                    <span :class="{'completed-todo': todo.completed}">
                        {{todo.title}}
                    </span>
                </div>
                <button type="submit" class="delete-button">X</button>
            </div>
    </div>
</template>

<script>
import TodoMaker from './TodoMaker.vue'

export default {
    name: 'Todos',
    components: {
        TodoMaker
    },
    props: [
        'todos'
    ],
    methods: {
        changeComplete(todo){
            //ako prosljedimo id kao parametar
            //const currentTodoIndex = this.todos.findIndex(x => x.id === id)
            //const currentTodo = this.todos[currentTodoIndex] 
            //currentTodo.completed = !currentTodo.completed
            todo.completed = !todo.completed
        },
        compare(a, b){
            if(a.completed === true && b.completed === false){
                return 1;
            }
            if(a.completed === false && b.completed === true){
                return -1;
            }
            return 0
        }
    },
    computed: {
        sortedTodos(){
            const newTodos = [...this.todos]
            newTodos.sort(this.compare)
            return newTodos
        }
    }
    
}
</script>

<style scoped>
    .todo-item{
        display: grid;
        grid-template-columns: 1fr auto;
        background: #f4f4f4;
        padding: 1em;
        margin-bottom: 0.3em;
    }

    .delete-button{
        background: red;
        width: 1.5em;
        border-radius: 50%;
        color: white;
        padding: 0.3em;
        border: none;
    }

    .completed-todo{
        text-decoration: line-through;
    }
</style>