<template>
  <div>

    <AddTodo
    @addtodo="addtodo"
    :todoarray ="todoarray"
    />
    <TodoList
        :todoarray ="todoarray"
        @deleteitem = 'deleteitem'
    />
  </div>
</template>

<script>

import AddTodo from "@/components/AddTodo";
import TodoList from "@/components/Frameworks/TodoList";
export default {
  name: 'App',
  components: {
    AddTodo,
    TodoList,
  },
  data() {
    return {
      todoarray: [],
       }
  },
  methods: {
    addtodo(event) {
      this.todoarray.push(event);
    },
    deleteitem(event) {

      for (let i = 0; i < this.todoarray.length; i++){
        if (this.todoarray[i] === event){
          this.todoarray.splice(i, 1)
      }}

    },

  }
}
</script>

<style>
</style>