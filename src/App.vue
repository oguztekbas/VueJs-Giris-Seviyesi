<template>
  <DynamicMenu />
  <Logout />
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

<script>
import DynamicMenu from "@/components/DynamicMenu.vue";
import Logout from "@/components/Logout.vue";

export default {
  
  components: {
    DynamicMenu,
    Logout
  }

}
</script>
