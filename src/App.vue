<template>
  <Header />
  <MainComponent />
</template>

<script>
import { store } from './store.js';
import Header from './components/Header.vue';
import MainComponent from './components/MainComponent.vue';
export default {
  name: 'App',
  data() {
    return {
      store
    }
  },
  components: {
    Header,
    MainComponent
  }
}
</script>

<style lang="scss" scoped></style>