<template>
  <div class="home">
    <div class="animate__animated animate__fadeInUp">
      <div class="card mb-5  ">
        <form class="container p-5">
          <div class="form-group">
            <label class="mb-3"
            for="task">Title of your post :</label>
            <input
                type="text"
                name="task"
                id="task"
                class="form-control mb-4"
                v-model="task">
                <label class="mb-3"
                for="task">Description :</label>
            <input
                type="text"
                name="task"
                id="task"
                class="form-control mb-4"
                v-model="task">
                <label class="mb-3"
            for="task">Enter your task below :</label>
            <textarea
                name="descri"
                id="descri"
                cols="100"
                rows="3"
                class="form-control mb-4"
                v-model="task"></textarea>
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
    </div>

  </div>
</template>

<script>
export default {
  name: 'BlogView'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
