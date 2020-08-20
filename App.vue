<template>
  <div>
    <div class="container">
    <input v-model="message">
   <button v-on:click="addlist" v-if="todoarray.length == 10 ?show = false :show=true">Add new todo</button> <br>    
    </div>
  <div class="container">
  <ul>
    <li v-for="(element, index) in todoarray" :key="index">{{element}} <button v-on:click="remove(index)" > Remove </button> </li>
  </ul>
  </div>
    
  </div>
</template>

<script>
export default{
  name: 'App',
  
data() {
  return {
  message: '',  
  todoarray: [],
   }
  },

methods: {
  addlist: function() {
        console.log(this.message) 
       this.todoarray.push(this.message);
       this.message = ''
       },
  
  remove: function(index) {
        this.todoarray.splice(index,1)
  }
}
}
</script>

<style>
.container{
  display: flex;
 justify-content: center;
}
</style>
