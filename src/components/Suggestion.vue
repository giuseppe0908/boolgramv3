<template>
    <section>
        <div class="suggestion">
            <p class="color-gray">Suggerimenti per te</p>
            <p> <b>Mostra tutti</b></p>
        </div>
        <div class="persone" v-for="(person, index) in people" :key="index">
            <div class="profile">
                <img :src="person.profile_picture" alt="">
                <p><b>{{person.profile_name}}</b></p>
            </div>
            <div class="follow">
                <p>Segui</p>
            </div>
        </div>
    </section>
   
</template>

<script setup>
import axios from "axios";
import { ref, onMounted } from 'vue'


    const people = ref([])
    onMounted(() => {
        axios.get('https://flynn.boolean.careers/exercises/api/boolgram/posts').then(response => {
            people.value = response.data;
        });

        
    })

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .suggestion{
      display: flex;
      justify-content: space-between;
      
      margin: 0 20px;
  }
  .persone{
      display: flex;
      justify-content: space-between;
      
      margin: 10px;
      .profile{
          display: flex;
          align-items: center;
            img{
                height: 40px;
                width: 40px;
                border-radius: 50%;            
            }
            p{
                margin-left: 10px;
                
            }
            
          
      }
      .follow{
            p{
                color: #0095f6;                
            }
        }
  }
</style>
