<template>
  <div class="wrapper">
    <Header class="header" />
    <Searchbar
      :placeholder="placeholder"
      @onkeyPress="valorPesquisa"
      class="searchBar"
    />

    <BoxConteudo class="box-conteudo">
      <div v-if="data" class="conteudo1">
        <CardSignificado :dados="data" />
      </div>
      <div v-else class="conteudo2">
          <CardError/>
      </div>
    </BoxConteudo>
  </div>
</template>

<script>
export default {
  props: {
    data: { type: Array, required: true },
  },
  data() {
    return {
      placeholder: 'Pesquise uma palavra',
    }
  },
  methods: {
    valorPesquisa(e) {
      this.$emit('valorPesquisa', e)
    },
  },
}
</script>
<style lang="scss" scoped>
.wrapper {
  height: 100%;
  width: 100%;
  padding: 0.8rem;
  background: #eeeeec;
  .searchBar {
    margin: 1rem 0;
  }
}
</style>