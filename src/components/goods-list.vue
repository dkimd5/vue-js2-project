<template>
  <div class="goods-list">
    <goods-item v-for="good in goods" :good="good"></goods-item>
  </div>
</template>

<script>
export default {
	setup() {
		
	},
}
</script>