<template>
  <div id="app">
    <ul>
      <todoItem
        v-for="(task, index) in taskList"
        v-bind:key="task.task"
        v-bind:taskData="task"
        v-bind:index="index"
        v-bind:deleteItem="deleteItem"
        >
      </todoItem>
    </ul>
    <form v-on:submit.prevent="addTask">
      <label>Add a new task:</label><br />
      <input v-model="newTask" type="text" />
      <input type="submit" />
    </form>
  </div>
</template>

<script>
import todoItem from './components/todo-item.vue';
export default {
  name: 'app',
  components: {
    todoItem
  },
  data() {
    return {
      newTask: '',
      taskList: [
        {
          done: false,
          task: 'Build a Vue app'
        },
        {
          done: false,
          task: 'Components!'
        },
        {
          done: false,
          task: 'Add in Async'
        }
      ]
    }
  },
  methods: {
    deleteItem(index) {
      this.taskList.splice(index, 1);
    },
    addTask(){
      var taskItem = {
        done: false,
        task: this.newTask
      }
      this.taskList.push(taskItem);
      this.newTask = '';
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
ul {
  list-style: none;
}
.done-task {
  text-decoration: line-through;
}
</style>
