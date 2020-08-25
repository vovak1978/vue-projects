<template>
  <div>

           <TodoItem
               v-for = "(element, i) in todoarray"
               :key = 'i'
               :element="element"
               @deletitem="deletitem"
           />

      </div>
   </template>

<script>
import TodoItem from "@/components/Frameworks/TodoItem";

export default {
  name: 'TodoList',
  components: {
    TodoItem
  },

  props: {
    todoarray: {
      type: Array
    }
  },

  methods: {
    deletitem(event){

      this.$emit("deleteitem", event)

    }

  }
}
</script>

<style>

</style>