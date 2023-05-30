<template>
    <div>
      <h1 class="text-primary large animate__animated animate__fadeIn">Blog <span class="text-warning">app</span> <span class="rbor"></span></h1>

      <!-- Blog navigation -->
      <div id="navigation">
        <ul class="mb-4 nav nav-pills nav-justified animate__animated animate__fadeIn">
          <li class="nav-item">
            <button
            @click="Active('form')"
            :class="['nav-link', {'active': link.form}]" >Blog Form</button>
          </li>
          <li class="nav-item">
            <button
            @click="Active('post')"
            :class="['nav-link',{'active': link.post}]" >All blog post</button>
          </li>
        </ul>
      </div>

      <component :post="blog_data" @send-data="commitPost($event)" :is="componentId"></component>
    </div>
</template>

<script>
import BlogForm from '../components/blog-sub-component/BlogForm.vue'
import BlogPost from '../components/blog-sub-component/BlogPost.vue'

export default {
  name: 'blog-view',
  components: {
    'blog-form': BlogForm,
    'blog-post': BlogPost
  },

  data () {
    return {
      componentId: 'blog-form',

      link: {
        form: true,
        post: false
      },
      blog_data: defaultData
    }
  },

  methods: {
    Active: function (link) {
      switch (link) {
        case 'form':
          this.link.form = true
          this.link.post = false
          this.componentId = 'blog-form'
          break
        case 'post':
          this.link.form = false
          this.link.post = true
          this.componentId = 'blog-post'
      }
    },

    commitPost: function (data) {
      this.blog_data.push(data)
    }
  }
}

const defaultData = [
  {
    title: 'Protection of the environnement',
    description: 'To protect the environnement, We all need to stand for this and take our responsability for this duty',
    email: 'protector@save.world'
  },
  {
    title: 'Data integrity',
    description: 'The data integrity is a key factor for the numeric data developement',
    email: 'hackerData@hack.bin'
  },
  {
    title: 'Learning online',
    description: 'Nowaday, kids and youth dives in the tendance of leaning online using video or chatting with a numeric mentor',
    email: 'learning@kids.school'
  }
]
</script>

<style>
.large {
  padding: 10px;
  letter-spacing: 5px;
  box-shadow: 0 5px 7px rgb(236, 236, 236);
}

.rbor {
  margin-left:30px;
  border-left: 5px solid rgb(0, 102, 255);
}
</style>
