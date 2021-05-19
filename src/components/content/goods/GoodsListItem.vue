<template>
	<div class="goodsItem">
		<img :src="goodsItem.show.img" alt="">
		<div>
	<!-- 		<div style="width:300px;text-overflow:ellipsis; white-space:nowrap; overflow:hidden;">实时订重置密码成功实时订重置密码成功实时订重置密码成功</div> -->
			<p>{{goodsItem.title}}</p>
			<span class="price">￥{{goodsItem.price}}</span>

			<span class="collect">&nbsp;★{{goodsItem.cfav}}</span>
		</div>
	</div>
</template>

<script>
export default {

  name: 'GoodsListItem',

  props: {
  	goodsItem: {
  		type: Object,
  		default() {
  			return {}
  		}
  	}
  },
}
</script>

<style lang="css" scoped>
	.goodsItem{
		flex: 1;
		text-align: center;
	}
	.goodsItem img{
		border-radius: 10px;
		width: 325px;
	}
	.goodsItem div{
		width: 325px;
		margin: 0 auto;
	}
	.goodsItem div p{
		overflow: hidden;
		text-overflow: ellipsis;
		word-break: break-all;
		-webkit-box-orient: vertical;
		display: -webkit-box;
		-webkit-line-clamp: 2;
	}
	.goodsItem div .price{
		color: var(--color-high-text);
	}
	.goodsItem div .collect{
		
	}
</style>