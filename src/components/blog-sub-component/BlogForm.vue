<template>
<div class="center">
    <div class="animate__animated animate__fadeInLeft">
    <div class="card mb-5  ">
        <form class="container p-5">
        <div class="form-group">
            <label class="mb-3"
            for="task">Title of your post :</label>
            <input placeholder="Enter your title..."
                type="text"
                name="task"
                id="task"
                class="form-control mb-4"
                required
                v-model="post_data.title">
            <label class="mb-3"
            for="task">Enter your Email :</label>
            <input placeholder="someone@body.com..."
                type="email"
                name="task"
                id="task"
                class="form-control mb-4"
                required
                v-model="post_data.email">
            <label class="mb-3"
            for="task">Description :</label>
            <textarea placeholder="Describe your subject..."
                name="descri"
                id="descri"
                cols="100"
                rows="3"
                class="form-control mb-4"
                required
                v-model="post_data.description"></textarea>
            <p v-if="error" class="mb-2 text-danger">Please fill correctly the fields below *</p>
            <p v-if="send" class="mb-2 text-success">Data Send Successfully. Proceed to "All blog post" section to see your post.</p>
            <button
            @click.prevent.self="addPost"
            class="btn btn-primary">Submit task</button>
        </div>
        </form>
    </div>
    </div>

</div>
</template>

<script>
export default {
  name: 'BlogView',
  props: ['post'],
  data () {
    return {
      post_data: {
        title: '',
        email: '',
        description: ''
      },
      post_copy_data: {
        title: '',
        email: '',
        description: ''
      },
      fake_data: [],
      error: false,
      send: false
    }
  },
  created () {
    this.fake_data = this.post
    console.log('Data faked')
    console.log(this.fake_data)
  },

  methods: {
    addPost: function () {
      if (this.post_data.title === '' || this.post_data.email === '' || this.post_data.description === '') {
        console.log('Empty value')
        this.error = true
        this.send = false
      } else {
        this.send = true
        this.error = false

        this.post_copy_data.title = this.post_data.title
        this.post_copy_data.email = this.post_data.email
        this.post_copy_data.description = this.post_data.description

        this.$emit('send-data', this.post_copy_data)
        this.post_data.title = ''
        this.post_data.email = ''
        this.post_data.description = ''
        console.log('Data send successfully')
        console.log(this.fake_data)
        console.log('\n')
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.center {
    width: 75%;
    margin: auto;
  }
</style>
