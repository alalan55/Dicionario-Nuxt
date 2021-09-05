<template>
  <div class="home">
    <HomeTemplate @valorPesquisa="pesquisar" :data="data" />
  </div>
</template>

<script>
export default {
  data(){
    return{
      data: undefined
    }
  },
  methods:{
    async pesquisar(e){
      try {
        const response = await this.$axios.$get(`/meanings/${e}`);
        this.data = response
      } catch (error) {
          console.error(error)
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.home{
  background: rgb(250,251,248);
  height: 100vh;
  padding: 2rem 1rem;
  position: relative;

  // &::before{
  //   content: '';
  //   position: absolute;
  //   top: 0;
  //   left: 0;
  //   width: 100%;
  //   height: 100%;
  //   background: linear-gradient(#000, #fff);
  //   clip-path: circle(30% at right 70%);
  //   opacity: .1;
    
  // }
}

</style>

