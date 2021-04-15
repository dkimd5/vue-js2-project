<template>
  <form>
    <input type="text" v-model="sLine" />
    <button type="button" v-on:click="filterGoods">Search</button>
  </form>
</template>

<script>
export default {
  props: {
    filteredGoods: Array,
    goods: Array,
    good: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      sLine: "",
    };
  },

  methods: {
    filterGoods() {
      console.log(this.sLine);
      const s = this.sLine.trim();
      this.$emit("searching-good", s);
    },
  },
};
</script>