<template>
  <div>
      <ul>
          <li v-for="(value,index) in listdata"
          :key="index"
          @click="$emit('clickedItem',value)">
          {{ value }}
          </li>
      </ul>
      

  </div>
</template>

<script>
   
  export default {
     props: {
    
         listdata: {
             type: Array,
             required: true,
             validator:(value) => {
                 return value.length <= 5;
             }
         }
     }
    
  }
</script>