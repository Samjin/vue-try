<template>
    <small>Written by {{ author.firstName }} {{ author.lastName }}</small>
</template>

<script>
    export default {
      props: {
        author: {
          // This is for validating data that got passed in
          type: Object, // String, Number, Boolean, Function, Object, Array
          required: true
        }
      }
    }
</script>