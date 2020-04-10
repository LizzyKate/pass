<template>
  <div class="container">
  <div class="row max-height align-items-center">
   <div class="col-10 mx-auto col-md-8 message-container text-center p-3">
    <h4 class="text-capitalize">A message you would like to pass</h4>
    <form id="message-form" ref="form">
     <input type="text"  id="message" class="w-100 my-3 p-2" >
     <button type="submit" id="submitBtn" class="btn btn-lg" v-on:click.prevent="readRefs()" >Submit</button>
     
    </form>
    <h5 class="p-2 alert alert-danger my-3 text-capitalize feedback" >please enter a value to pass</h5>
    <h4 class="text-capitalize my-3">last message delivered</h4>
    <h4 class="message-content text-uppercase">{{hello}}</h4>

   </div>
  </div>
 </div>
 
</template>

<script>
export default {
  data () {
    return {
      hello:'hello world',
      feedback:false
    }
  },
 methods:{
   readRefs(){
     this.hello = this.$refs.form[0].value;
     this.$refs.form[0].value=''
     console.log(this.$refs.form[0].value)
   }
 }
}
</script>

<style>
:root {
  --lightBlue: #95b8d1;
  --mainwhite: #f5f5f5;
  --mainBlack: #333333;
}
.max-height {
  min-height: 100vh;
}
body {
  background: var(--lightBlue);
}
.message-container {
  background: var(--mainwhite);
}
.message-content {
  color: var(--lightBlue);
}
#submitBtn {
  background: var(--lightBlue);
  color: var(--mainwhite);
}
#submitBtn:hover {
  color: var(--lightBlue);
  color: var(--mainBlack);
}

.feedback {
  display: none;
}

.show {
  display: block;
}
</style>
