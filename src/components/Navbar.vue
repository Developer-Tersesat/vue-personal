<template>
     <div class="my-navbar">
          <div class="my-navbar-left" v-on:click="toggleNavbar">
               <div class="my-toggle">
                    <span></span>
                    <span></span>
                    <span></span>
               </div>
               <h1>JUAL<span>sepatu</span></h1>
               <div class="my-navbar-list" :class="{active : navbar}">
                    <li><router-link to="/">Brand</router-link></li>
                    <li><router-link to="/">Home</router-link></li>
                    <li><router-link to="/">Kategori</router-link></li>
                    <li><router-link to="/about">About</router-link></li>
               </div>
              
          </div>
          <div class="my-navbar-right"> 
               <li><router-link to="/">Log In</router-link></li> 
               <li><a href="">|</a></li>
               <li><router-link to="/">Sig Up</router-link></li>
               <div class="my-seacrh">
                    <input type="search" name="" placeholder="Cari Disini  !!"><button type="submit"><i class="fas fa-search"></i></button>
               </div>
               <i class="fas fa-shopping-bag"></i>
          </div>
    </div>
   
</template>

<script>
export default {
     data : function(){
          return {
               navbar : false
          }
     },
     methods : {
          toggleNavbar : function(){            
               this.navbar = !this.navbar
          }
     }
     
}
</script>

<style lang="scss">
      $primary-color : rgb(43, 44, 44);
      $secondary-color : rgb(50, 51, 51);
      $nav-color : rgb(238, 238, 238);
     .my-navbar-list{
          display: flex;
     }
     .my-navbar{
       padding: 0px 15px;
       background-color:$primary-color;
       display: flex;
       width: 100%;
       justify-content: space-between;
       .my-navbar-left{
            display: flex;
            h1{
                color: rgb(214, 54, 54);
                 span{
                      color:$nav-color;
                 }
            }
            li{
                   padding: 10px 20px;
            }

       }
       li{
            display: flex;
            list-style: none;
          
          
       }
       a{
            margin: auto 0px;
            text-decoration: none;
            color: rgb(238, 238, 238);
       }
       .my-navbar-right{
            display: flex;
            li{
                 color: $nav-color;
                 padding: 0px 10px;
                
            }
            .my-seacrh{
                 border: solid darkgrey 3px;
                 border-radius: 5px;
                 height: max-content;
                 margin: auto 0px;
                 background-color: rgb(255, 255, 255);
            }
            input[type=search]{
                 border: none;
                 border-radius: 5px;
                 background-color: transparent;
            }
            button[type=submit]{
                 border: none;
               background-color: transparent;
            }
            .fa-shopping-bag{
                 font-size: x-large;
                 margin-left: 15px;
                 align-self: center;
                 color: white;
            }
       }
     }
     @media screen and (max-width: 575.98px){
           @keyframes growDown {
                         0% {
                              transform: scaleY(0)
                         }
                         80% {
                              transform: scaleY(1.1)
                         }
                         100% {
                              transform: scaleY(1)
                         }
          }
          
          .my-navbar-list, .my-navbar-right li {    
               
               display: none;    
              
                   
          }
          .my-toggle{
                 display: flex;
                 flex-direction: column;
                 justify-content: space-evenly;
                 cursor: pointer;
                 margin-right:10px ;
                 span{
                      display: block;
                      height: 6px;
                      width: 50px;
                      background-color: white;
                 }
            }
          .my-navbar-list.active{
               animation: growDown 400ms ease-in-out forwards;
               position: absolute;
               background-color:$secondary-color;
               top: 56px;
               left: 0;
               width: 100%;
               display: flex;
               flex-direction: column;
               transform-origin: top;
               
          }
          input[type=search]{
               display: none;
          }
     }
</style>