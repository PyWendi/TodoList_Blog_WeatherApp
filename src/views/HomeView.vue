<template>
  <home-compo/>
</template>

<script>
// @ is an alias to /src
import Home from '@/components/HomeComponent.vue'

export default {
  name: 'HomeView',
  components: {
    'home-compo': Home
  }
}
</script>
