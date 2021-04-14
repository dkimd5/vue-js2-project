<template>
  <div class="goods-list">
    <GoodsItem v-for="good in goods" :key="good"></GoodsItem>
  </div>
</template>

<script>
import GoodsItem from "./goods-item";

export default {
  name: "goods-list",
  props: {
    goods: Array,
  },
  components: {
    GoodsItem,
  },
};
</script>