<script>

import Temperature from './components/Temperature.vue';
import Sun from './components/Sun.vue';
import Condition from './components/Condition.vue';

export default {
  components: {
    Temperature,
    Sun,
    Condition
  }
  
};

</script>

<template>

  <div class = "wrap">     
    <router-view></router-view>        
  </div>
       
</template>

<style scoped>


.wrap {
  display: grid;
  height: 70vh;
  width: 100vw;
  background: #FDF5E6;
  margin: 0;
  color: #292733;
  text-align: center;
  padding: 50px 0;
  align-content: center;
}

</style>
