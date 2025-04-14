<template>
  <div class="container">
    <div class="row">
    <div class="col-md-3">
      <SideBar />
    </div>
    <div class="col-md-9">
      <StudentTable />
    </div>
  </div>
  </div>
</template>

<script>
import StudentTable from './StudentTable.vue'
import SideBar from './SideBar.vue'

export default {
  name: 'PageLayout',
  components:{
    StudentTable,
    SideBar,
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
  min-height: 70vh;
}
</style>
