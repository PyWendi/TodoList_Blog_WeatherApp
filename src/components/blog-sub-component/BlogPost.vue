<template>
    <div>
        <div class="todo container justify-content-around">
            <div class="row">

                <div class="col-sm-6 col-md-6 animate__animated animate__fadeInRight">
                    <div class="card mb-5">
                        <div class="card-header bg-primary text-white">
                            <h2 class="card-title">All post</h2>
                        </div>

                        <!-- All post List -->
                        <div class="p-3 maxHeight" >
                            <div v-for="(post,i) in post_list"
                                :key="i"
                                class="card mb-3 d-flex flex-row justify-content-between">
                                <!-- Header -->
                                <div class="p-2">
                                    <h4 class="card-title text-primary">Post N°{{i+1}} Title :</h4>
                                    <div class="">
                                        <div class="card-text">
                                            <h5 class="">-{{ post.title }}</h5>
                                        </div>
                                    </div>
                                </div>
                                <p class="endline">
                                    <button @click="showPost(i)" @mouseover="look=false"
                                        class="btn btn-outline-success m-2">Look at the post</button>
                                </p>
                            </div>
                            <!-- End of all post -->

                        </div>

                    </div>
                </div>

                <!-- View post Details -->
                <div class="col-sm-6 col-md-6 animate__animated animate__fadeInRight">
                    <div class="card mb-2" >
                        <div class="card-header bg-primary text-white">
                            <h2 class="card-title">Blog post</h2>
                        </div>

                        <!-- Post view -->
                        <div class="m-4 card">
                            <!-- Header -->
                            <div class="p-2 card-header">
                                <h4 class="card-title text-primary animate__animated animate__fadeIn animate__delay-2s">Post Title :</h4>
                                <div class="">
                                    <div class="card-text">
                                        <h6 :class="{'animate__animated animate__fadeIn' : look}"
                                        class="">{{post_data.title}}</h6>
                                    </div>
                                </div>
                            </div>

                            <!-- Body -->
                            <div class="card-body" style="overflow-x:break-word;">
                                <h4 class="text-secondary animate__animated animate__fadeIn animate__delay-2s">Description :</h4>
                                <h6 :class="{'animate__animated animate__fadeIn' : look}"
                                class="">{{post_data.description}}</h6>
                            </div>

                            <!-- Footer -->
                            <div class="card-footer justify-content-between wrap align-items-center">
                                <div class="">
                                    <h6 class="text-primary animate__animated animate__fadeIn animate__delay-2s">Written by :</h6>
                                    <p :class="{'animate__animated animate__fadeIn' : look}"
                                    class="">{{post_data.email}}</p>
                                </div>

                                <div class="wrap">
                                    <button @click="look=false" class="btn m-1 btn-outline-primary">Edit</button>
                                    <button @click="delPost" class="btn m-1 btn-outline-danger">Delete</button>
                                </div>
                            </div>

                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'blog-post',
  props: ['post'],
  data () {
    return {
      post_data: {
        title: '...',
        description: '...',
        email: '...'
      },
      post_list: [],
      delIndex: null,
      look: false
    }
  },

  created () {
    this.post_list = this.post
    console.log('Data IN BLOG collected successfully')
    console.log(this.post_list)
    console.log('\n')
  },

  methods: {
    showPost: function (index) {
      console.log('LOOOK')
      this.look = true
      this.post_data.title = this.post_list[index].title
      this.post_data.description = this.post_list[index].description
      this.post_data.email = this.post_list[index].email
      this.delIndex = index
    },
    delPost: function () {
      if (this.delIndex === null) {
        console.log('NULL')
      } else {
        this.post_list.splice(this.delIndex, 1)
        this.delIndex = null
        this.post_data.title = '...'
        this.post_data.email = '...'
        this.post_data.description = '...'
      }
    }
  }
}
</script>

<style scoped>
h2 {
    text-align:center;
}
.endline {
    text-align: end;
}
.wrap{
    display:flex;
    flex-direction: row;
    flex-wrap: wrap;
}

@media screen and (min-width:1000px){
    .wrap{
        flex-wrap: wrap;
    }
}
.maxHeight {
    max-height: 450px;
    overflow-y: scroll;
}
</style>
