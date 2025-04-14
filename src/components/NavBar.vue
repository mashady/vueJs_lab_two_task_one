<template>
  <nav class="navbar navbar-light bg-light">
    <a class="navbar-brand" href="">Minia os</a>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  props: {
    msg: String
  }
}
</script>

<style scoped>
nav{
  padding-right: 10px;
  padding-left: 10px;
}
</style>