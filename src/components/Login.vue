<template>
  <div>

    <form v-if="this.$store.state.token == ''"  class="row" action="" v-on:submit.prevent="true">
        <label>Kullanıcı Adı : </label>
        <input style="margin-left:10px; margin-right:10px;" type="text" v-model="username">
     
        <label>Şifre : </label>
        <input style="margin-left:10px;" type="password" v-model="password">  <br /> <br />
        
        <button v-on:click="LoginProcess" style="width:100px; padding:10px;" >GİRİŞ</button>
   </form>
   
    
  </div>
</template>

<script>

import axios from 'axios';


export default {

  name: "Login",
  data(){
    return {
      username : "",
      password : "",
    }
  },
  methods: {
   LoginProcess(){
     
      axios.post('https://localhost:44373/api/authentication/login',
        {
          "username" : this.username,
          "password" : this.password
        }
      )
      .then((res) => {
        this.$store.state.token = res.data.token;
        this.$router.push('/about');
        console.log(res.data);
        
        
      })
      .catch((err) => {
        this.$store.state.token = "";
        console.log(err);
      });
    }
  }
};
</script>




