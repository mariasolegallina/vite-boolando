<script>
import PageHeader from './components/PageHeader.vue';
import PageFooter from './components/PageFooter.vue';
import ProductsCards from './components/ProductsCards.vue';
// import DbJson from './db.json';
import axios from 'axios'
import { store } from './store'

export default {
  components: {
    PageHeader,
    PageFooter,
    ProductsCards,
  },
  data() {
    return {
      // dbJson: DbJson,
      store: store,
      products: store.products,
    }
  },
  created() {
    axios.get('http://localhost:3000/products')
      .then(res => {
        const products = res.data;
        console.log(res, products)
        this.store.products = products
      })
      .catch(error => {
        console.error('Error fetching data:', error);
      });
  }

}
</script>

<template>
  <PageHeader />
  <main>
    <div class="section">
      <div class="container">
        <div class="row columnrow">
          <div v-for="(product, i) in store.products" :key="i" class="col-4">
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
