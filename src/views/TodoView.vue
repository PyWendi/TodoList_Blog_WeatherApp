<template>
  <div>
    <h1 class="mb-5 text-primary large animate__animated animate__fadeIn">Todo <span class="text-warning">app</span> <span class="rbor"></span></h1>
    <div class="center">
      <todo-compo></todo-compo>
    </div>
  </div>
</template>

<script>
import TodoComponent from '../components/TodoComponent.vue'

console.log('On todo import ')

export default {
  name: 'todoView',
  components: {
    'todo-compo': TodoComponent
  },
  created () {
    console.log('Inside todo view')
  }
}
</script>

<style scoped>
  .large {
    padding: 10px;
    letter-spacing: 5px;
    box-shadow: 0 5px 7px rgb(236, 236, 236);
  }

  .rbor {
    margin-left:30px;
    border-left: 5px solid rgb(0, 102, 255);
  }
  .center {
    width: 75%;
    margin: auto;
  }
</style>
