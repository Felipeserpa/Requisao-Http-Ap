<template>
  <div id="app">

<header>
  Vue nutri
</header>

<article v-for="item in nutri" :key="item.id">

<strong>{{item.titulo}}</strong><br>

<img src="item.capa"/><br>

<span>{{item.categoria}}</span>

<p>{{item.subtitulo}}</p>   
</article>



  </div>



 


</template>

<script>
 import api from "./services/api";


  export default{

    name: 'App',
    data(){
      return{
       nutri:[]

      }
    },
    
     async created(){

const response =  await api.get('/?api=posts');
console.log(response.data)
this.nutri = response.data

    }
  

    
  
  }
  
</script>

<style>



</style>