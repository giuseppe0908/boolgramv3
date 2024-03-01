<template>
  <main>
      <div class="main-sx">
          <Main_sx />
      </div>
      <div class="main-dx">
          <Main_dx />
      </div>
  </main>
</template>

<script setup>
import Main_sx from "./Main-sx.vue";
import Main_dx from "./Main-dx.vue";

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
   main{
       display: flex;
       padding-top: 90px;
       .main-sx{
           width: 70%;
       }
       .main-dx{
           width: 30%;
           position: relative;
       }
   }
</style>
