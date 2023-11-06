<script>
import PageHeader from './components/PageHeader.vue';
import PageFooter from './components/PageFooter.vue';
import ProductsCards from './components/ProductsCards.vue';

export default {
  components: {
    PageHeader,
    PageFooter,
    ProductsCards,
  },
  data() {
    return {

    }
  }
}
</script>

<template>
  <PageHeader />
  <main>
    <ProductsCards />
  </main>
  <PageFooter />
</template>

<style lang="scss">
@use './styles/general.scss';

main {
  padding: 40px 0 15px 0;
}

.col-4 {
  flex-basis: calc((100% / 12) * 4);
}

.columnrow>[class^="col-"] {
  padding: 0 10px 30px 0;
}
</style>
