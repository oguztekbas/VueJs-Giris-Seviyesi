<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <Login />
    <!-- <AxiosDeneme /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Login from "@/components/Login.vue";
// import AxiosDeneme from "@/components/AxiosDeneme.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
    Login
    // AxiosDeneme
  }
};
</script>
