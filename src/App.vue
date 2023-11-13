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
      open: false,
      selectedProd: {}
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
  },
  methods: {
    showModal(prod) {
      console.log('show modal')
      this.selectedProd = prod
      this.open = true

    },
    closeModal() {
      console.log('click su chiudi')
      this.open = false
      this.selectedProd = {}
    },
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
            <ProductsCards @show="showModal" :product="product" />
          </div>
        </div>
      </div>
    </div>

  </main>
  <PageFooter />

  <!-- modal -->
  <div v-if="open" class="modal">
    <div class="card">
      <div class="card__header">
        <p @click="closeModal">chiudi</p>
      </div>
      <div class="card__body">
        <p>testo testo testo</p>
      </div>
    </div>
  </div>
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

.modal::after {
  content: '';
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 40;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal .card {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 50;
  background-color: white;
  border-radius: 20px;
  padding: 20px;
  width: 100%;
  max-width: 500px;
  box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.2);

  .card__header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 22px;
    font-weight: 700;
  }
}
</style>
