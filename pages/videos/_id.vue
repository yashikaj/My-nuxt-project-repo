<template>
    <div>
     <nuxt-child :video="video"/>
    </div>
</template>

<script>
export default {

     data(){
        return{
            videos: [{
                id:'16',
                name: 'Intro to Nuxt JS'
            
            },
            {
                id:'1',
                name: 'Intro to vue JS'
            },
            {
                 id:'25',
                name: 'Intro to vue JS nuxt'
            }]
        }
    },
    computed : {
        video(){
           return  this.videos.find(v => v.id ==this.$route.params.id)
        }
    }
    
}
</script>
<style lang="scss" scoped>
</style>