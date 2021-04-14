<template>
  <div class="goods-item">
    <h3>{{ good.product_name }}</h3>
    <p>{{ good.price }}</p>
  </div>
</template>

<script>
export default {
  props: {
    good: {
      type: Object,
      required: true,
    },
  },

//   data() {
//     return {
//       gooditem: this.good,
//     };
//   },
};
</script>