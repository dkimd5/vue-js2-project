<template>
  <div class="goods-list">
    <GoodsItem v-for="good in goods" :good="good" v-bind:key="good"></GoodsItem>
  </div>
</template>

<script>
import GoodsItem from "./goods-item";

export default {
  props: {
    goods: Array,
  },
  components: {
    GoodsItem,
  },
};
</script>