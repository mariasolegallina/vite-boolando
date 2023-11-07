<script>
import PageHeader from './components/PageHeader.vue';
import PageFooter from './components/PageFooter.vue';
import ProductsCards from './components/ProductsCards.vue';
import DbJson from './db.json';

export default {
  components: {
    PageHeader,
    PageFooter,
    ProductsCards,
  },
  data() {
    return {
      dbJson: DbJson,
    }
  },
  created() {
    console.log("che c'è qui?", this.dbJson.products)
  }
}
</script>

<template>
  <PageHeader />
  <main>
    <div class="section">
      <div class="container">
        <div class="row columnrow">
          <div v-for="(product, i) in dbJson.products" key="i" class="col-4">
            <ProductsCards :product="product" class="card" />
          </div>
        </div>
      </div>
    </div>

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
