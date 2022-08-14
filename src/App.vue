<template>
    <h1>{{header}}</h1>
 <p ref="name">{{title}}</p>
 
<div v-if="showModal">
 <Modal :loginheader="loginheader" :theme="theme" @close="toggleModal">
     <p>Login to your account</p>
     
     <template v-slot:links> 
        <a href="#">Log in</a>
         <a href="#">More info</a>
     </template>
     
 </Modal>
</div>

 
<div v-if="showModal1">
 <Modal :regheader="regheader" @close="toggleModal1">
     
     <p>Register your account.</p>
     
     <template v-slot:links>
        <a href="#">Reigister</a>  
         <a href="#">More info</a>
     </template>
     
 </Modal>
</div>


<button @click="toggleModal">Login</button>
<button @click="toggleModal1"> Register</button>


</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components: {Modal},
  data(){
      return{
          title:'Welcome to the vue portal.',
          header:'Hello User',
          regheader:'Welcome visitor',
          loginheader:'Welcome back!',
          text:'This is the page text',
          theme:'sales',
          showModal:false,
          showModal1:false
      }
    }, 
      
      methods:{
        toggleModal()
        {
            this.showModal = !this.showModal
        },
        
         toggleModal1()
        {
            this.showModal1= !this.showModal1
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
