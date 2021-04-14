<template>
  <div class="search-wrap">
    <input type="text" v-model="sLine" class="goods-search" />
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
  props: {
    searchLine: String,
    filteredGoods: Array,
    goods: Array,
    good: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      fGoods: this.filteredGoods,
      sLine: this.searchLine,
    };
  },

  methods: {
    filterGoods(good_name) {
      console.log("starting");
      const regexp = new RegExp(good_name, "i");
      this.fGoods = this.goods.filter((good) => regexp.test(good.product_name));
    },
  },
};
</script>