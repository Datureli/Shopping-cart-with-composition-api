<template>
<div>
  <div id="nav">
    <Navbar />

  </div>
    <router-view />
</div>

</template>

<script lang="ts">
import Navbar from "../src/components/Navbar.vue";
import { defineComponent } from "vue";

export default defineComponent({
  components: {
    Navbar,
  },
 // setup() {},
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #b6c9db;
}


#nav a {
  font-weight: bold;
  color: #437bb3;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
