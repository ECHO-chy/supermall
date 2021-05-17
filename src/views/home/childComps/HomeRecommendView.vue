<template>
	<div class="recommend">
		<div v-for="item in recommends" class="recommendItem">
			<a :href="item.link">
				<img :src="item.image" alt="">
				<div>{{item.title}}</div>
			</a>
		</div>
	</div>
</template>

<script>
export default {

  name: 'HomeRecommendView',

  props: {
  	recommends: {
  		type: Array,
  		default() {
  			return []
  		}
  	}
  }
}
</script>

<style lang="css" scoped>
.recommend{
	display: flex;
	text-align: center;
	padding: 20px 0 50px;
	border-bottom: 20px #e9e9e9 solid;
}
.recommendItem{
	flex: 1;
}
.recommendItem img{
	width: 150px;
	margin: 20px 0 10px;
}
</style>