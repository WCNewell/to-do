<template>
    <li id="todoItem"></li>
    <p v-bind:class="{ 'done-task' : task.done }">{{task.task}}</p>
    <input v-model="task.done" type="checkbox"/>
    <button v-on:click="deleteItem(index)">Delete</button>

</template>

<script>
import todoItem from './components/todo-item.vue'

    export default {
        name: 'todoItem',
        props: ['taskData', 'index']

    }
</script>

<style lang="css scoped">

</style>