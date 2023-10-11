<template>
  <the-header ></the-header>
  <the-resources></the-resources>
  <!-- <storedResources :resources="storedResources"></storedResources> -->
</template>

<script>
// import StoredResources from './components/learning-resources/StoredResources.vue'
import TheHeader from './components/layouts/TheHeader.vue'
import TheResources from './components/learning-resources/TheResources.vue'
 export default{
  components:{TheHeader,TheResources},
    
 }

</script>

<style>

</style>
