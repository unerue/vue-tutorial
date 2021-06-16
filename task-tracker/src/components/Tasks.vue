<template>
  <div v-for="task in tasks" :key="task.id">
    <!-- <h3>{{ task.text }}</h3> -->
    <Task :task="task.text" />
  </div>
</template>

<script>
import Task from './Task'

export default {
  name: 'Tasks',
  props: {
    tasks: Array
  },
  components: {
    Task
  }
}
</script>