<template>
  <div class="card">
    <div v-for="value in dados" :key="value.class" class="card-items">
      <div class="tipo border-5 padding-03">
        <span class="title">Tipo</span>
        <span>{{ value.class }}</span>
      </div>

      <div class="meanings border-5 padding-03">
        <span class="title">Significados</span>
        <ul>
          <li v-for="meaning in value.meanings" :key="meaning">
            {{ meaning }}
          </li>
        </ul>
      </div>

      <div v-if="value.etymology" class="origem border-5 padding-03">
        <span class="title">Origem</span>
        <span>{{ value.etymology }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['dados'],
}
</script>

<style lang="scss" scoped>
.card {
  border-radius: 5px;
  padding: 0.5rem;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;

  .card-items {
    background: white;
    border-radius: 5px;
    margin: 0.5rem 0;
    height: 300px;
    flex: 0 1 300px;
    overflow: hidden;
    overflow-y: auto;
    padding: 0.5rem;

    &::-webkit-scrollbar {
      width: 0;
      border-radius: 5px;
    }

    &::-webkit-scrollbar-track {
      border-radius: 5px;
      border: 2px solid #fafbf8;
    }

    &::-webkit-scrollbar-thumb {
      border-radius: 5px;
      background: #c1c2c0;
    }

    .title {
      font-weight: 800;
      margin-bottom: 0.2rem;
      display: block;
      padding-bottom: 0.2rem;
    }
    .border-5 {
      border-radius: 5px;
    }
    .padding-03 {
      padding: 0.3rem;
    }

    .tipo {
      background: #cce7f5;
      span {
        display: block;
      }
    }
    .meanings {
      background: #fad6b9;
      ul {
        li {
          list-style: none;
          margin: 0.3rem 0;
          text-align: justify;
          padding: 0.1rem;
          border-radius: 5px;
          background: #fafbf8;
        }
      }
    }
    .origem {
      background: #dfe6e8;
      span {
        display: block;
      }
    }

    & > div {
      margin: 1rem 0;
    }
  }
}
</style>