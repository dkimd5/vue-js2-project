<template>
  <div class="search-wrap">
    <input type="text" v-model="searchLine" class="goods-search" />
    <button
      class="search-button"
      type="button"
      v-on:click="filterGoods(searchLine)"
    >
      Искать
    </button>
  </div>
</template>

<script>
export default {
  name: "search-goods",
  props: {
    searchLine: String,
    filteredGoods: Array,
    goods: Array,
  },

  methods: {
    filterGoods(good_name) {
      console.log("starting");
      const regexp = new RegExp(good_name, "i");
      this.filteredGoods = this.goods.filter((good) =>
        regexp.test(good.product_name)
      );
    },
  },
};
</script>