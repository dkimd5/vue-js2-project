<template>
  <div id="app">
<h1>what</h1>
  </div>
</template>

<script>
import GoodsList from './components/goods-list'

export default {
  name: "App",
  data() {
    return {
      goods: [],
      API_URL: 'https://raw.githubusercontent.com/GeekBrainsTutorial/online-store-api/master/responses',
    }
  },
  components: {
    GoodsList
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
