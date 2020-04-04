<template>
  <div class="about">
    <TestCompont/>
    
  </div>
</template>


<script>
// @ is an alias to /src
// import LoginComponent from '@/components/LoginComponent.vue'
// import TestCompont from "@/components/TestCompont/index.vue";
import TestCompont from '../components/TestComponent/index.vue'

export default {
  name: "home",
  data() {
    return {blue:true,
    orange:true};
  },

  components: {
    // LoginComponent,
    // TestCompont
    TestCompont
  }
};
</script>
