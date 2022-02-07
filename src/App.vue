<template>
  <div id="app">
    <MyHeader/>
    <router-view />
  </div>
</template>

<script>
  // import Image from '@/assets/logo.png';
  import MyHeader from '@/components/Header.vue'

  export default {
    name: 'App',
    components: {
      MyHeader
    },

    data: ()=>({
     
    }),

    methods: {
      
    },
    computed: {
       
    } 

  }
</script>

<style>
  
</style>
