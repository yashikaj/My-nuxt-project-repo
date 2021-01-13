<template>
  <div>
    <h1>{{message}}</h1>
    
  </div>
</template>

<script>
    import Input from './Input.vue';
  export default {
      data(){
          return {
              message: 'This is a great message'
          }
      },
      components: {
           Input
      }
    
  }
</script>