<template>
  <div>
    <span>
      {{element}}
      <button @click="deletitem">Delete</button>

    </span>

  </div>
</template>

<script>

export default {
  name: 'TodoItem',

  props:{
    element:{
      type: String
    }
  },


  methods: {
    deletitem(){
      this.$emit("deletitem", this.element)

    }

  }
}
</script>