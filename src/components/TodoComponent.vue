<template>
  <div>
    <div class="card mb-5 animate__animated animate__fadeInUp ">
      <form class="container p-5">
        <div class="form-group">
          <label class="mb-3"
          for="task">Enter your task below :</label>
          <input
              type="text"
              name="task"
              id="task"
              class="form-control mb-4"
              v-model="task">
          <button
              @click.prevent="addTask"
              class="btn btn-primary">Submit task</button>
        </div>
      </form>
    </div>

    <!-- List of tasks -->
    <todo-task-list :tasks="tasks"
    class="animate__animated animate__fadeInUp"></todo-task-list>
  </div>
</template>

<script>
import TodoTasks from './todo-sub-component/TodoList.vue'

export default {
  name: 'TodoComponent',
  components: {
    'todo-task-list': TodoTasks
  },

  data () {
    return {
      task: '',
      tasks: ['HTML', 'CSS', 'VUE JS 3', 'Django + REST Framework (DRF API) + Vue JS 3 = Beautifull dynamic WebApp']
    }
  },
  methods: {
    addTask: function () {
      this.tasks.push(this.task)
      this.task = ''
    }
  }

}
</script>

<style>

</style>
