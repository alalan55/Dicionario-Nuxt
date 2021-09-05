<template>
  <div class="input">
    <input
      v-model="valor"
      type="text"
      :placeholder="placeholder"
      @keypress="sendArgs"
    />

    <i class="fas fa-search"></i>
  </div>
</template>

<script>
export default {
  props: {
    placeholder: { type: String, required: true },
  },

  data() {
    return {
      valor: '',
    }
  },

  methods: {
    sendArgs(e) {
      if (e.key === 'Enter') {
        this.$emit('onkeyPress', this.valor)
        this.valor = ''
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.input{
  width: 100%;
  position: relative;

  input {
    width: 100%;
    border-radius: 5px;
    border: none;
    padding: 1rem 1rem;

  
    &:focus {
      outline: none;
    }
  }
  .fas{
    position: absolute;
    bottom: 16px;
    right: 10px;
    
  }
}
</style>