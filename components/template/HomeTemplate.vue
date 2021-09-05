<template>
 <div class="wrapper">
    <Header class="header"/>
    <Searchbar :placeholder='placeholder' @onkeyPress="valorPesquisa" class="searchBar"/>

    <BoxConteudo class="box-conteudo">
        
        <div  v-if="data" class="conteudo1">
            <CardSignificado :dados="data"/>
        </div>
        <div  v-else class="conteudo2">
            <!-- <CardSignificado :dados="data"/> -->
            nada
        </div>
    </BoxConteudo>

    

 </div>
</template>

<script>
export default {
    props:['data'],
    data(){
        return{
            placeholder: 'Pesquise uma palavra'
        }
    },
    methods:{
        valorPesquisa(e){
            this.$emit('valorPesquisa', e)
        }
    }
}
</script>
<style lang="scss" scoped>
.wrapper{
    height: 100%;
    width: 100%;
    padding: .8rem;

      background: #EEEEEC;

    .header{
        
    }
    .searchBar{
        margin: 1rem 0;
    }
    .box-conteudo{

    }
}

</style>