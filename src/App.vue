<script>
import PageHeader from './components/PageHeader.vue';
import PageFooter from './components/PageFooter.vue';

export default {
  components: {
    PageHeader,
    PageFooter,
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

  </main>
  <PageFooter />
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
