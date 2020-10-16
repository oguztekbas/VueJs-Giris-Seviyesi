<template>
<div id="nav">
 <!-- {{$store.state.token}} -->
    <router-link v-if="this.$store.state.token == ''" to="/">Home</router-link>
    <div v-if="this.$store.state.token != ''"> 
    <router-link v-for="menu in list" :key="menu.id" :to="`${menu.menuName === 'Home' ? '/' : '/' + menu.menuName}`">{{menu.menuName + " "}}</router-link>
    </div>
    
  </div>
</template>

<script>

import axios from 'axios';


export default {

  name: "DynamicMenu",
  data(){
    return {
      list:[],  
    }
  },
  // created(){
  //   this.getMenus();
   
  // },
 
  methods: {
    getMenus(){
     let token = this.$store.state.token;
      axios.get('https://localhost:44373/api/dynamicmenu/getmenus',{
        headers: {
           Authorization: 'Bearer ' + token
         }
      })
      .then((res) => {
        
        console.log(res.data);
        this.list = res.data;
      })
      .catch((err) => {
        console.log(err);
      });
    }
  },
  watch : {
     '$store.state.token': 'getMenus'
  }
};
</script>




