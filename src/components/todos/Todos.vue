<template>
    <div>
        <TodoMaker />
        <h1>Todos</h1>
    </div>
</template>

<script>
import TodoMaker from './TodoMaker.vue'

export default {
    name: 'Todos',
    components: {
        TodoMaker
    }
    
}
</script>

<style scoped>

</style>