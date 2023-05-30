<template>
    <div>
        <div class="card p-2 maxHeight">
            <div v-for='(task,i) in task_list'
                :key="i"
                class="d-flex flex-row align-items-center
                animate__animated animate__fadeIn justify-content-between p-2">
                <p>{{ task }}</p>
                <div>
                    <button @click.prevent="deleteTask(i)"
                    class="btn btn-outline-danger">Delete</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'todo-task-list',
  props: ['tasks'],

  data () {
    return {
      task_list: []
    }
  },

  created () {
    this.task_list = this.tasks
    console.log('Affectation done')
  },

  methods: {
    deleteTask: function (index) {
      this.task_list.splice(index, 1)
      console.log('Data deleted')
    }
  }
}
</script>

<style scoped>
    p{
        margin: 0 !important;
    }
    .maxHeight{
      max-height: 300px;
      overflow-y: scroll;
    }
</style>
