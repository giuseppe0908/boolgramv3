<template>
    <div class="stories">
        <div class="circle" v-for="(story,index) in stories" :key="index">
            <img :src="story.profile_picture" alt="{{story.profile_name}}">
            <small>{{story.profile_name}}</small>
        </div>
    </div>
</template>

<script setup>
import axios from "axios";
import { ref, onMounted } from 'vue'

    const stories = ref([])
    onMounted(() => {
        axios.get('https://flynn.boolean.careers/exercises/api/boolgram/profiles').then(response => {
            stories.value = response.data;
        });
    })

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
    .stories{
    //    height: 150px;
    //    width: 100%;
       display: flex;
       align-items: center;
    //    flex-wrap: wrap;
       overflow-y: scroll;
        height: 120px;
        background-color: #fff;
        border: 1px solid #d3d3d3;
        border-radius: 5px;
       .circle{
           margin: 10px;
           width: calc(100% / 6 - 20px);
           
           img{
               height: 60px;
               width: 60px;
               border-radius: 50%;
               border: 3px solid red;
           }
           p{
               margin: 0px;
           }
           
       }
   }
   small {
      text-align: center;
      display: block;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
      margin-top: 2px;
    }
</style>
