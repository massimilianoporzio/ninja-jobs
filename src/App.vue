<template>
  <div id="nav" v-if="$route.name!=='404'">
    <div>
      <router-link to="/">Home</router-link> |
      <router-link :to="{name: 'About'}">About</router-link> |
      <router-link :to="{name: 'Jobs'}">Jobs</router-link>
    </div>

    <div style="margin-top: 30px">
      <button @click="redirect">Redirect</button>
      <button @click="back">Go back</button>
      <button @click="forward">Go forward</button>
    </div>

  </div>
  <router-view/>
</template>

<script setup>
import {useRouter} from "vue-router";
const router  = useRouter()
function redirect(){
  router.push({name: 'Home'})
}
function back(){
  router.go(-1)
}
function forward(){
  router.go(1)
}
</script>

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
  text-decoration: none;
  padding: 10px;
  border-radius: 4px;
}

#nav a.router-link-exact-active {
  color: white;
  background: crimson;
}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
}
</style>
