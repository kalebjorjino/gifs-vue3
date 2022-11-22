<template>
  <div>
    <h1 class="text-center">Gif Router</h1>
    <img :src="img" :alt="nombre">
  </div>
</template>

<script>
export default {
   data()  {
    return{
      img: "",
      nombre: ""
    }
    
   },
   created(){
   this.getRandomGif()
   },
   methods: {
    async getRandomGif(){
      const data = await fetch('https://api.giphy.com/v1/gifs/random?api_key=5WSi6kQTuM14SMuQ1Zvw2jlBMXbiDM7R')
      const res = await data.json()

      this.img = res.data.images.original.url;
      this.name = res.data.title;
    }
   }
};
</script>

<style  scoped>

</style>