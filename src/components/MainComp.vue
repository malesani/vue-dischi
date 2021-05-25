<template>
  <div class="sfondo pt-5">
    <div class="container">
      <ul class="row">
        <li class="col-1" v-for="(album, index) in albums" :key="index" >
          <img :src="album.poster" alt="">
          <div class="title">{{album.title}}</div>
          <div class="text">{{album.genre}}</div>
          <div class="text">{{album.year}}</div>
        </li>
        
      </ul>
    </div>
  </div>
</template>

<script>
  import axios from 'axios';

  export default {

    data(){
      return{
        axios,
        albums:[]
      }
    },

    created(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then(res => {
        this.albums = res.data.response
        console.log(res.data.response)
      })
      .catch(err => {
        console.log(err);
      })
    }
  }

  
</script>

<style lang="scss">
  .sfondo{
    width: 100%;
    height: calc(100% - 50px);
    overflow: auto;
    background-color: #1E2D3B;
    .container{
      
      ul{
        padding: 0;
        li{
          width: calc(100% / 5 - 20px);
          min-width: 200px;
          height:250px;
          background-color: #2E3A46;
          color: white;
          margin: 15px 10px;
          padding: 20px 10px;
          text-align: center;
          img{
            width: 65%;
            margin-bottom: 10px;
          }
          .title{
            text-transform: uppercase;
            margin-bottom: 7px;
          }
          .text{
            color: rgb(119, 118, 118);
            font-size: 13px;
            
            
          }
        }
      }
    }
  }
</style>