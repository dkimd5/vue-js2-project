<template>
  <div id="app">
    <header class="header">
      <SearchGoods></SearchGoods>
      <CartGoods></CartGoods>
    </header>
    <main>
      <GoodsList :goods="filteredGoods"></GoodsList>
    </main>
  </div>
</template>

<script>
import GoodsList from "./components/goods-list";
import SearchGoods from "./components/search-goods";
import CartGoods from "./components/cart-goods";

export default {
  name: "App",
  data() {
    return {
      goods: [],
      API_URL:
        "https://raw.githubusercontent.com/GeekBrainsTutorial/online-store-api/master/responses",
      filteredGoods: [],
      searchLine: "",
      cart: [],
    };
  },

  components: {
    GoodsList,
    SearchGoods,
    CartGoods,
  },

  methods: {
    fetchTodos() {
      return fetch(`${this.API_URL}/catalogData.json`)
        .then((response) => response.json())
        .then((response) => {
          this.filteredGoods = response;
          this.goods = response;
        });
    },
  },

  mounted() {
    this.fetchTodos();
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
