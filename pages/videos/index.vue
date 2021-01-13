<template>
    <div>
        <h1>Videos</h1>
        <div v-for="video in videos" :key="video.id">
            <nuxt-link :to="`/videos/${video.id}`">{{video.name}}</nuxt-link>
        </div>
       
    </div>
</template>

<script>
export default {
  async  asyncData(context){
      let response= await context.$axios.$get(`http://localhost:3000/api/videos`)
      let videos = response.data.data.map(v => v.attributes);
      console.log(response);
      debugger
        return{
            videos
        }
    },
     
}
</script>
<style lang="scss" scoped>
</style> 