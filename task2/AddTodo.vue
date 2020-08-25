<template>
  <div>
    <div>
      <h1>ToDoList</h1>
    </div>
       <div v-if="errormessage">
      <p>"Виправте наступні помилки"</p>
       <ul>
        <li>{{errormessage}}</li>
      </ul>
     </div>
    <div class="container">
      <input type="text" v-model="message" >
       <button @click="addlist" v-if="todoarray.length == 4 ?show = false :show=true">Add new todo</button>
    </div>

  </div>
</template>


<script>


export default{
  name: 'AddTodo',

  props: {
    todoarray: {
      type: Array
    }
  },

data() {
  return {
      message: '',
      errormessage: '',

   }
  },
 methods:{
   addlist: function() {
     this.errormessage = ''

     if (! this.message) {
       this.errormessage = 'Поле не може бути пусте';

     }
     else{

    this.$emit('addtodo', this.message)
       this.message = ''
     }
   },
 }
}
</script>

<style>

</style>