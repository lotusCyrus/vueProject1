 <template>
  <div class="back-drop" @click.self="closeModal">
    <div class="modal" :class="{sales: theme ==='sales'}">
        <h2>{{regheader}}</h2>
        <h2>{{header}}</h2>
        <h2>{{loginheader}}</h2>
      <p>{{text}}</p>
     
     <slot></slot>
   <div class="actions" >
     <slot name="links">
         
     </slot>
   </div>
      
    </div>
  </div>
</template>

<script>
    export default 
    {
      props:['header', 'text' , 'regheader', 'loginheader' , 'theme'],
    
    methods:
    {
        closeModal()
        {
            this.$emit('close')
        }
    }
   }
</script>

<style>
  .modal{
   width:200px;
   padding:20px;
   margin:100px auto;
   background:white;
   border-radius:10%;

  }
  .back-drop
  {
   top:0;
   position:fixed;
   background:rgba(0,0,0,0.5);
   width:100%;
   height:100%;
   
  }
  
  .modal .actions
  {
      text-align: center;
      margin:7px 0 2px 0;
      color:#333;
  }
  
  .modal .actions a{
      padding:2px;
      border:1px solid #eee;
      border-radius:2px;
      text-decoration:none;
      margin:2px;
      font-size:13px;
  }
  
  
  .modal.sales{
     background-color:red;
     color:white;
  }
</style>