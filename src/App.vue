<template>
  <div id="app">
    <IndexHeader />

    <IndexMain />

  </div>
</template>

<script>
import IndexHeader from './components/IndexHeader.vue';
import IndexMain from './components/IndexMain.vue';


export default {
  name: 'App',
  components: {
    IndexHeader,
    IndexMain
  }
}
</script>

<style lang="scss">
@import '@/style/main-style.scss';

</style>
