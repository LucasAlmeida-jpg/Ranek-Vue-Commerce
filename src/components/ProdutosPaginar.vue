<template>
  <div>
    <p>Páginas {{ paginasTotal }}</p>
    <ul>
      <li v-for="pagina in paginasTotal" :key="pagina">
        <router-link :to="{ query: { _page: pagina } }">{{ pagina }}</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    produtosPorPagina: {
      type: Number,
      default: 1,
    },
    produtosTotal: {
      type: Number,
      default: 1,
    }
  },
  computed: {
    paginasTotal() {
      const total = this.produtosTotal / this.produtosPorPagina
      return (total !== Infinity) ? Math.ceil(total) : 0
    }
  }
}
</script>

<style></style>