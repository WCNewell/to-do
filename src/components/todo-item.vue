<template>
  <li id="todoItem">
    <p v-bind:class="{ 'done-task' : taskData.done }">{{taskData.task}}</p>
    <input v-model="taskData.done" type="checkbox" />
    <button v-on:click="deleteItem(index)">Delete</button>
  </li>
</template>

<script>
export default {
  name: 'todoItem',
  props: ['taskData', 'index', 'deleteItem']
}
</script>

<style lang="css" scoped>
</style>
