<template>
    <section id="dx">
    <div class="profile">
        <div class="img">
            <img src="../assets/img/profile.jpg" alt="foto-profilo">
            <div class="name">  
                <p id="name">gisieed</p>
                <p id="lastname" class="color-gray">ok</p>
            </div>
        </div>
        
        <div class="pass-as">
            <a href="">Passa a</a>
        </div>

    </div>
    <div class="suggerimenti">
        <Suggestion />
    </div>
    </section>
    
</template>

<script setup>
import Suggestion from "./Suggestion.vue";

 
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
   #dx{
        position: fixed;
        z-index: 2;
        // top: 90px;
        // right: 170px;
        //207px;
        // width: 30%;

       .profile{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 0 20px;
       .img{
           display: flex;
           align-items: center;
           img{
                height: 50px;
                border-radius: 50%;
           }
           .name{
               p{
                   margin: 0px 5px;
               }
           }
       }
       .pass-as{
           a{
               text-decoration: none;
               color: #0095f6;
           }
       }
   }
   .color-gray{
       color: gray;
   }
   }
   
</style>
