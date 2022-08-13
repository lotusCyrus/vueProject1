<template>
 <h1 ref="name">{{title}}</h1>
 
<div v-if="showModal">
 <Modal :header="header" :text="text" :theme="theme" @close="toggleModal">
     <p>what a cool app</p>
     <template v-slot:links> 
        <a href="#">Signup</a>
         <a href="#">More info</a>
     </template>
 </Modal>
</div>
<button @click="toggleModal">click me</button>

</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components: {Modal},
  data(){
      return{
          title:'this page title',
          header:'This header of this modal',
          text:'This is the page text',
          theme:'sales',
          showModal:false
      }
    },
      
      methods:{
        toggleModal()
        {
            this.showModal = !this.showModal
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
