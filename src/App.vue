<template>
  <NavBar />
  <PageLayout msg="Welcome to Your Vue.js App"/>
  <FooTer />
</template>

<script>
import PageLayout from './components/PageLayout.vue'
import NavBar from './components/NavBar.vue'
import FooTer from './components/FooTer.vue'
export default {
  name: 'App',
  components: {
    PageLayout,NavBar,FooTer
  }
}
</script>

<style>
#app {

}
</style>
