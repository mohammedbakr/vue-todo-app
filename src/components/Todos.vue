<template>
    <div>
        <div v-for="todo in todos" :key="todo.id">
            <app-todo :todo="todo" @delTodo="$emit('delTodo', todo.id)"></app-todo>
        </div>
    </div>
</template>

<script>
import Todo from './Todo';

export default {
    name: 'Todos',
    components: {
        appTodo: Todo,
    },
    props: ['todos']
}
</script>

<style scoped>

</style>