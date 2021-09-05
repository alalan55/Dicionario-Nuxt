<template>
  <div class="container-box">
    <slot />
  </div>
</template>
<style lang="scss">
.container-box {
  width: 100%;
  height: 65vh;
  overflow-y: auto;
  padding: 0.5rem;

  &::-webkit-scrollbar{
    width: 10px;
    border-radius: 5px;
  }

  &::-webkit-scrollbar-track{
    border-radius: 5px;
    border: 2px solid #FAFBF8;
  }

  &::-webkit-scrollbar-thumb{
    border-radius: 5px;
    background: #c1c2c0;
  }
}
</style>