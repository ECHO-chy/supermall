<template>
	<div class="goodsList">
		<goods-list-item v-for="item in goodsList" :goodsItem="item"/>
	</div>
</template>

<script>
import GoodsListItem from "./GoodsListItem"
export default {

  name: 'GoodsList',
  components: {
  	GoodsListItem
  },

  props: {
  	goodsList: {
  		type: Array,
  		default() {
  			return []
  		}
  	}
  }
}
</script>

<style lang="css" scoped>
	.goodsList{
		display: flex;
		flex-wrap: wrap;
    padding: 19px;
	}
</style>