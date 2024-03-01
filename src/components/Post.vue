<template>
    <div class="posts">
        <div class="post" v-for="(post,index) in posts" :key="index">
            <div class="header-post">
                <div class="img">
                    <img :src="post.profile_picture" alt="">
                </div>
                    <p>{{post.profile_name}}</p>
                <div class="menu">
                    <i class="fas fa-ellipsis-h"></i>
                </div>
            </div>
            <div class="img">
                <img :src="post.post_image" alt="">
            </div>

            <div class="info-post">
                
                <div class="icons">
                    <div class="icons-left">
                        <svg :class= "(like) ? 'piace' : 'non-piace'" @click="mi_piace(index)"
                        aria-label="Mi piace"
                        class="_8-yf5"
                        :fill="[(like && index == indice) ? '#ed4956' : '']"
                        height="24"
                        role="img"
                        viewBox="0 0 48 48"
                        width="24"
                        >
                        <path
                            :d="[(like && index == indice) ? heart_red : heart]"
                        ></path>
                        </svg>
                        <!-- <i :class= "(like) ? 'piace far fa-heart' : 'far fa-heart'" @click="mi_piace"></i> -->
                        <!-- <svg :class= "(like) ? 'piace' : 'non-piace'" @click="mi_piace" data-v-b4be2532="" aria-label="Mi piace" fill="#262626" height="24" role="img" viewBox="0 0 48 48" width="24" class="_8-yf5"><path data-v-b4be2532="" d="M34.6 6.1c5.7 0 10.4 5.2 10.4 11.5 0 6.8-5.9 11-11.5 16S25 41.3 24 41.9c-1.1-.7-4.7-4-9.5-8.3-5.7-5-11.5-9.2-11.5-16C3 11.3 7.7 6.1 13.4 6.1c4.2 0 6.5 2 8.1 4.3 1.9 2.6 2.2 3.9 2.5 3.9.3 0 .6-1.3 2.5-3.9 1.6-2.3 3.9-4.3 8.1-4.3m0-3c-4.5 0-7.9 1.8-10.6 5.6-2.7-3.7-6.1-5.5-10.6-5.5C6 3.1 0 9.6 0 17.6c0 7.3 5.4 12 10.6 16.5.6.5 1.3 1.1 1.9 1.7l2.3 2c4.4 3.9 6.6 5.9 7.6 6.5.5.3 1.1.5 1.6.5.6 0 1.1-.2 1.6-.5 1-.6 2.8-2.2 7.8-6.8l2-1.8c.7-.6 1.3-1.2 2-1.7C42.7 29.6 48 25 48 17.6c0-8-6-14.5-13.4-14.5z"></path></svg> -->
                        <svg id="pd-10" data-v-b4be2532="" aria-label="Commenta" fill="#262626" height="24" role="img" viewBox="0 0 48 48" width="24" class="_8-yf5"><path data-v-b4be2532="" clip-rule="evenodd" d="M47.5 46.1l-2.8-11c1.8-3.3 2.8-7.1 2.8-11.1C47.5 11 37 .5 24 .5S.5 11 .5 24 11 47.5 24 47.5c4 0 7.8-1 11.1-2.8l11 2.8c.8.2 1.6-.6 1.4-1.4zm-3-22.1c0 4-1 7-2.6 10-.2.4-.3.9-.2 1.4l2.1 8.4-8.3-2.1c-.5-.1-1-.1-1.4.2-1.8 1-5.2 2.6-10 2.6-11.4 0-20.6-9.2-20.6-20.5S12.7 3.5 24 3.5 44.5 12.7 44.5 24z" fill-rule="evenodd"></path></svg>
                        <svg data-v-b4be2532="" aria-label="Condividi il post" fill="#262626" height="24" role="img" viewBox="0 0 48 48" width="24" class="_8-yf5"><path data-v-b4be2532="" d="M47.8 3.8c-.3-.5-.8-.8-1.3-.8h-45C.9 3.1.3 3.5.1 4S0 5.2.4 5.7l15.9 15.6 5.5 22.6c.1.6.6 1 1.2 1.1h.2c.5 0 1-.3 1.3-.7l23.2-39c.4-.4.4-1 .1-1.5zM5.2 6.1h35.5L18 18.7 5.2 6.1zm18.7 33.6l-4.4-18.4L42.4 8.6 23.9 39.7z"></path></svg>
                    </div>
                    <div class="icone-right">
                        <i class="far fa-bookmark"></i>
                    </div>
                </div>
                <div class="like">
                    <img :src="post.likes[0].profile_picture" alt="">
                    <p>Piace a <b>{{post.likes[0].username}}</b> e <b>altri {{post.likes.length}}</b></p>
                </div>

                <div  class="comments">
                    <div class="comment" v-if=(!flag) >
                        <p><b>{{post.comments[0].username}}</b> {{post.comments[0].text}}</p>
                        <p v-if="(post.comments.length > 1 )" class="color-gray" @click="mostra(index)">mostra tutti e {{post.comments.length}}</p>
                    </div>

                    <div v-else  >
                        <div :class= "(indice == index) ? 'lista' : 'comment-visible'">
                            <p><b>{{post.comments[0].username}}</b> {{post.comments[0].text}}</p>
                            <p v-if="(post.comments.length > 1 )" class="color-gray" @click="mostra(index)">mostra tutti e {{post.comments.length}}</p>
                        </div>
                        <div class="comments-visible" v-for="(comment,indexx) in post.comments" :key="indexx">
                            <p :class= "(indice == index) ? 'show' : 'lista'"><b>{{comment.username}}</b> {{comment.text}}</p>
                        </div>

                    </div >
                </div>
                <div class="data">
                    <!-- <p>{{post.date.date}}</p> -->
                    <p><span class="color-gray">{{getdate(post.date.date)}}</span> ore fa</p>

                </div>
                <div class="insert-comment">
                    <div class="input">
                        <input  type="text" v-model="new_comment" placeholder="Aggiungi un commento">
                    </div>
                    <div class="send">
                        <p @click="publica(index)">Pubblica</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import axios from "axios";
import { ref, onMounted, onUpdated } from 'vue'

    const products = ref([])
    const posts = ref([])
    const flag= ref(false)
    const comments = ref([])
    const filtercomments = ref([])
    const indice = ref(0)
    const like = ref(false)
    const not_like = ref(true)
    const heart = ref('M34.6 6.1c5.7 0 10.4 5.2 10.4 11.5 0 6.8-5.9 11-11.5 16S25 41.3 24 41.9c-1.1-.7-4.7-4-9.5-8.3-5.7-5-11.5-9.2-11.5-16C3 11.3 7.7 6.1 13.4 6.1c4.2 0 6.5 2 8.1 4.3 1.9 2.6 2.2 3.9 2.5 3.9.3 0 .6-1.3 2.5-3.9 1.6-2.3 3.9-4.3 8.1-4.3m0-3c-4.5 0-7.9 1.8-10.6 5.6-2.7-3.7-6.1-5.5-10.6-5.5C6 3.1 0 9.6 0 17.6c0 7.3 5.4 12 10.6 16.5.6.5 1.3 1.1 1.9 1.7l2.3 2c4.4 3.9 6.6 5.9 7.6 6.5.5.3 1.1.5 1.6.5.6 0 1.1-.2 1.6-.5 1-.6 2.8-2.2 7.8-6.8l2-1.8c.7-.6 1.3-1.2 2-1.7C42.7 29.6 48 25 48 17.6c0-8-6-14.5-13.4-14.5z')
    const heart_red = ref("M34.6 3.1c-4.5 0-7.9 1.8-10.6 5.6-2.7-3.7-6.1-5.5-10.6-5.5C6 3.1 0 9.6 0 17.6c0 7.3 5.4 12 10.6 16.5.6.5 1.3 1.1 1.9 1.7l2.3 2c4.4 3.9 6.6 5.9 7.6 6.5.5.3 1.1.5 1.6.5s1.1-.2 1.6-.5c1-.6 2.8-2.2 7.8-6.8l2-1.8c.7-.6 1.3-1.2 2-1.7C42.7 29.6 48 25 48 17.6c0-8-6-14.5-13.4-14.5z")
    const bo = ref("M43.5 48c-.4 0-.8-.2-1.1-.4L24 29 5.6 47.6c-.4.4-1.1.6-1.6.3-.6-.2-1-.8-1-1.4v-45C3 .7 3.7 0 4.5 0h39c.8 0 1.5.7 1.5 1.5v45c0 .6-.4 1.2-.9 1.4-.2.1-.4.1-.6.1zM24 26c.8 0 1.6.3 2.2.9l15.8 16V3H6v39.9l15.8-16c.6-.6 1.4-.9 2.2-.9z")
    const new_comment = ref('')
    const mostra = ((i) =>{
        flag.value = true ;
        indice.value= i;
    })

    const mi_piace=((i)=>{
            like.value = !like.value ;
            indice.value = i;
            const new_like = {
                profile_picture:" ",
                username: "peppe",
            }
            if(like.value){
                posts[i].likes.value.push(new_like);
            }else{
               posts[i].likes.value.splice(-1, 1);
            }
    })

    const getdate= ((date)=>{
        let data = new Date(date);
            let ore = data.getHours(data);
            let now_date = new Date();
            let ore_now = data.getHours(now_date);
            // let min_now = data.getMinutes();
           
            return ore ;
    })

    

    const publica = (index) => {
        posts.value[index].comments.push({
            text: new_comment.value,
            username: "gisieed" 
        });
      
        // Resetta il campo del nuovo commento dopo l'aggiunta 
        new_comment.value = '';       
    };

    onUpdated(() => {
        window.publica = publica;
    });
    onMounted(() => {
        axios.get('https://flynn.boolean.careers/exercises/api/boolgram/posts').then(response => {
            posts.value = response.data;
        });
    
    })

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .post{
        .header-post{
            display: flex;
            margin-top: 20px;
            align-items: center;
            // width: 100%;
            border-radius: 4px;
            border: 1px solid #d3d3d3;
            .menu{
                display: flex;
                width: 100%;
                justify-content: flex-end;
                align-items: center;
                margin-right: 15px;
            }
            .img{
               height: 52px;
               border-radius: 50%;
               display: flex;
               align-items: center;
            //    margin: 0 10px;
               img{
               width: 40px;
               height: 40px;
               border-radius: 50%;
               margin: 0 20px;
               border: 2px solid red;

                 }

            }
        }
        .img{
            // height: 700px;
            height: 550px;
            // width: 150px;
            img{
                // height: 200px;
                // width: 100px;
                // margin: 10px 0;
                width: 100%;
                height: 100%;
            }
        }
        .info-post{
            border-radius: 4px;
            border: 1px solid #d3d3d3;
            padding: 0px 10px;

            .icons{
            display: flex;
            justify-content: space-between;
                svg{
                    margin: 10px 0px;

                    &#pd-10{
                        margin:10px 20px;
                    }
                }
                i{
                    font-size: 40px;
                    margin: 10px;
                }
            }
            .like{
                display: flex;
                align-items: center;
                img{
                    width: 30px;
                    height: 30px;
                    border-radius: 50%;
                    margin-right: 10px;
                }
            }
            .comments{
                text-align: left;
            }
            .data{
                text-align: left;
            }
            .insert-comment{
                display: flex;
                justify-content: space-between;
                align-items: center;
            }
        }
    }
    .posts{
        width: 100%;

    }
    .lista{
        display: none;
    }
    .color-gray{
        color: gray;
    }
    // .piace{
    //     background-color: red;
    // }
</style>
