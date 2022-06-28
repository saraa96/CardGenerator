<template>
<nav class="navbar navbar-custom">
    <!-- <div> Test</div> -->
  <div class="container-fluid">
    <a class="navbar-brand" href="#">
      <img src="../assets/KSRNR_Logo.png" alt="" width="50" height="50" class="d-inline-block pt-n5">
<span class="pt-5">{{title}}</span>
    </a>
  </div>
</nav>
</template>
<script>
export default {
  name: 'Header',
  props:{
    title: String,
  }
}
</script>

<style>
.navbar-custom{
    background-color:#597163;
     border-top: 5px solid #a56433;
     color:#fff !important;
}
</style>