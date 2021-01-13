<template>
  <div id="register">

    <h1>{{items}}</h1>
   
    <Input :listdata="items" />
     <h1>{{items}}</h1>
     <Input :listdata="items" />
   

   </div>
</template>

<script>
    import Input from '@/components/Input.vue'
   
export default {
    components: {
        Input
        
    },
    data: () => {
        return {
            items: ['first','Second','third'],
           
            
        }
    
   
        
    }
}
</script>