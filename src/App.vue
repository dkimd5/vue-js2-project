<template>
  <div id="app">
    <header class="header">
			<search-goods></search-goods>
			<cart-goods></cart-goods>
		</header>
		<main>
			<goods-list :goods="filteredGoods"></goods-list>
			<h2>Todos:</h2>
			<ol>
				<li v-for="todo1 in todos" :key="todo1">
					<todo-list-item :todo="todo1" />
				</li>
			</ol>
		</main>
  </div>
</template>

<script>
import GoodsList from "./components/goods-list";

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

    cartShown() {
      if (this.cart.length() > 0) {
        this.isVisibleCart = true;
      }
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
