<template>
  <div>
    <div id="navigation">
        <ul class="nav nav-tabs nav-justified">
          <li class="nav-item">
            <router-link
            @click="Active('home')"
            :class="['nav-link p-3', {'active': link.home}]" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link
            @click="Active('todo')"
            :class="['nav-link p-3',{'active': link.todo}]" to="/Todo">Todo App</router-link>
          </li>
          <li class="nav-item">
            <router-link
            @click="Active('blog')"
            :class="['nav-link p-3',{'active': link.blog}]" to="/Blog">Blog App</router-link>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled">Weather app</a>
          </li>
        </ul>
      </div>

    <div id="main_view">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      link: {
        home: true,
        todo: false,
        blog: false
      }
    }
  },
  methods: {
    Active: function (link) {
      switch (link) {
        case 'home':
          this.link.home = true
          this.link.todo = false
          this.link.blog = false
          break
        case 'todo':
          this.link.home = false
          this.link.todo = true
          this.link.blog = false
          break
        case 'blog':
          this.link.home = false
          this.link.todo = false
          this.link.blog = true
          break
      }
    }
  }
}
</script>

<style lang="scss">

body{
  padding: 0;
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
}

#navigation{
  width: 100%;
}
</style>
