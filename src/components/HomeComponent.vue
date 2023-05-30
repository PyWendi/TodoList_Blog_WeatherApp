<template>
    <div class="mt-4">
        <div v-if="show"
        class="card container mb-5 bg-success p-5 animate__animated animate__fadeIn">
            <h1 style="text-align:center;" class="text-white">First Vue JS 3 Multi App in a SPA </h1>
        </div>

        <div class="todo justify-content-around">
          <div class="row">
            <div class="col-sm-6 col-md-6 animate__animated animate__fadeInLeft">
              <div class="card mb-5">
                <div class="card-header bg-primary text-white">
                  <h2 class="card-title">Todo list app</h2>
                </div>
                <div class="card-body">
                    <img src="../assets/img/ben-griffiths-4wxWBy8Jo1I-unsplash.jpg" class="timg">
                </div>
                <div class="card-footer">
                  <p class="card-text">This is a Todo list app with no backend which mean that this app will not store whatever you put in</p>
                  <p class="endi"><button class="btn btn-outline-success">
                    <router-link class="text-white nolink" to="/todo">See the app</router-link>
                  </button></p>
                </div>
              </div>
          </div>
          <div class="col-sm-6 col-md-6 animate__animated animate__fadeInRight">
            <div class="card mb-2">
              <div class="card-header bg-primary text-white">
                <h2 class="card-title">Blog app</h2>
              </div>
              <div class="card-body">
                <img src="../assets/img/carlos-muza-hpjSkU2UYSU-unsplash.jpg" class="timg">
              </div>
              <div class="card-footer">
                <p class="card-text">This is a Blog app which is use to look for some blog title and to view the entire blog review, you can also put other blog post</p>
                <p class="endi"><button class="btn btn-outline-success">
                  <router-link class="text-white nolink" to="/blog">See the app</router-link>
                </button></p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- </div> -->
</template>

<script>
export default {
  el: '#demo',
  data () {
    return {
      show: true
    }
  },
  methods: {
    rev: function () {
      this.show = !this.show
    }
  }
}

</script>

<style scoped>
.todo {
    width: 85%;
    display:flex;
    flex-direction: row;
    flex-wrap:wrap;
    margin: auto;
}
.todo-sub {
  width:40%;
}
.timg {
    width: 100%;
}

.endi {
  text-align: end;
}

.card {
    box-shadow:0 0 7px grey;
}
.nolink {
  text-decoration:none;
}
</style>
