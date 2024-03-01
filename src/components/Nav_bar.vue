<template>
    <nav>
      <div class="nav-bar">
          <!-- <div class="nav-sx"> -->
              <div class="logo">
                  <img src="../assets/img/logo.png" alt="logo"/>
              </div>
          <!-- </div> -->
          <div class="nav-cx">
             <input type="text" placeholder="Cerca">
          </div>
          <!-- <div class="nav-dx"> -->
              <div class="icons">
                  <!-- <i class="far fa-heart"></i> -->
                  <svg data-v-01c2886c="" aria-label="Feed attività" fill="#262626" height="22" role="img" viewBox="0 0 48 48" width="22" class="_8-yf5"><path data-v-01c2886c="" d="M34.6 6.1c5.7 0 10.4 5.2 10.4 11.5 0 6.8-5.9 11-11.5 16S25 41.3 24 41.9c-1.1-.7-4.7-4-9.5-8.3-5.7-5-11.5-9.2-11.5-16C3 11.3 7.7 6.1 13.4 6.1c4.2 0 6.5 2 8.1 4.3 1.9 2.6 2.2 3.9 2.5 3.9.3 0 .6-1.3 2.5-3.9 1.6-2.3 3.9-4.3 8.1-4.3m0-3c-4.5 0-7.9 1.8-10.6 5.6-2.7-3.7-6.1-5.5-10.6-5.5C6 3.1 0 9.6 0 17.6c0 7.3 5.4 12 10.6 16.5.6.5 1.3 1.1 1.9 1.7l2.3 2c4.4 3.9 6.6 5.9 7.6 6.5.5.3 1.1.5 1.6.5.6 0 1.1-.2 1.6-.5 1-.6 2.8-2.2 7.8-6.8l2-1.8c.7-.6 1.3-1.2 2-1.7C42.7 29.6 48 25 48 17.6c0-8-6-14.5-13.4-14.5z"></path></svg>
                  <!-- <i class="fas fa-home"></i> -->
                  <svg data-v-01c2886c="" aria-label="Home" fill="#262626" height="22" role="img" viewBox="0 0 48 48" width="22" class="_8-yf5"><path data-v-01c2886c="" d="M45.5 48H30.1c-.8 0-1.5-.7-1.5-1.5V34.2c0-2.6-2.1-4.6-4.6-4.6s-4.6 2.1-4.6 4.6v12.3c0 .8-.7 1.5-1.5 1.5H2.5c-.8 0-1.5-.7-1.5-1.5V23c0-.4.2-.8.4-1.1L22.9.4c.6-.6 1.6-.6 2.1 0l21.5 21.5c.3.3.4.7.4 1.1v23.5c.1.8-.6 1.5-1.4 1.5z"></path></svg>
                  <div id="img-profile">
                      <img src="../assets/img/profile.jpg" alt="foto-profilo"/>
                  </div>
              </div>
          <!-- </div> -->
      </div>
    </nav>
  </template>
  
  <script>

  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
      nav{
          
          position: fixed;
          z-index: 2;
          top: 0;
          left: 0;
          right: 0;
          border-bottom: 1px solid #d3d3d3;
          background-color: #fff;
          height: 60px;
          display: flex;
          align-items: center;
          .nav-bar{
              width: 70%;
              margin: 0 auto;
              display: flex;
              justify-content: space-between;
              align-items: center;
              
              // .nav-sx{
                  .logo{
                      display: flex;
                      img{
                          // height: 50px;
                          width: 100px;
                      }
                  }
              // }
              .nav-cx{
                  input{
                      width: 180px;
                      height: 28px;
                      border-radius: 4px;
                      border: 1px solid #d3d3d3;
                      text-align: center;
                      background-color: #fafafa;
                      // font-size: 21px;
                  }
              }
              // .nav-dx{
                  .icons{
                      display: flex;
                      align-items: center;
                      svg{
                          margin: 0 10px;
                          // font-size: 25px;
                      }
                      #img-profile{
                          margin-left: 15px;
                          display: flex;
                          img{
                              // height: 40px;
                              width: 30px;
                              border-radius: 50%;
                          }
                      }
                  }
                  
              // }
          }
      }
  </style>
  