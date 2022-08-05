<template>
 <h1 ref="name">{{title}}</h1>
 <button @click="handleClick" >click me</button>
</template>

<script>
export default {
  name: 'App',
  data(){
      return{
          title:'this page title'
      }
   
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
