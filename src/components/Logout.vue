<template>
  <div v-if="this.$store.state.token != ''" >

  <span v-on:click="Logout">Çıkış Yap</span>
   
    
  </div>
</template>

<script>

export default {

  name: "Logout",
  methods: {

    Logout(){
      if(this.$store.state.token != ""){
        this.$router.push('/');
        this.$store.state.token = "";
      }
    }

  }
};
</script>




