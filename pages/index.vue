<template>
  <div class="home">
    <HomeTemplate @valorPesquisa="pesquisar" :data="data" />
  </div>
</template>

<script>
export default {
  data(){
    return{
      data: []
    }
  },
  methods:{
    async pesquisar(e){
      try {
        const response = await this.$axios.$get(`/meanings/${e}`);
        console.log(response.status)
        this.data = response;
      } catch (error) {
        this.data = null
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
}

</style>

