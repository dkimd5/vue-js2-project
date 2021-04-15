<template>
  <div>
    <form @filterGoods="filterGoods" class="search-wrap">
      <input type="text" v-model="sLine" class="goods-search" />
      <button class="search-button" type="submit">Искать</button>
    </form>
    <form>
      <input type="text" v-model="sLine2" />
      <button type="button" v-on:click="filterGoods2">Search</button>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    // searchLine: String,
    filteredGoods: Array,
    goods: Array,
    good: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      // fGoods: this.filteredGoods,
      sLine: "",
      sLine2: "",
    };
  },

  methods: {
    filterGoods() {
      console.log(this.sLine);
    },
    filterGoods2() {
      console.log(this.sLine2);
    },
    // filterGoods(good_name) {
    //   console.log("starting");
    //   const regexp = new RegExp(good_name, "i");
    //   this.fGoods = this.goods.filter((good) => regexp.test(good.product_name));
    // },
  },
};
</script>