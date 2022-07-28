<template>
  <div id="app" class="text-start">
    <Header/>
    <router-view/>
  </div>
</template>

<style>

</style>

<script>
import './App.css'
import Header from './components/Header.vue'
export default {
    name: "App",
    components: { Header }
}
</script>