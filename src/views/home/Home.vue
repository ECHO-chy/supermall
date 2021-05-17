<template>
	<div id="home">
		<nav-bar class='home-nav'>
			<template #center>购物街</template>
		</nav-bar>
		<HomeSwiper :banners="banners"/>
		<HomeRecommendView :recommends="recommends"/>
	</div>
</template>

<script>
import NavBar from '@components/common/navbar/NavBar';
import HomeSwiper from './childComps/HomeSwiper';
import HomeRecommendView from './childComps/HomeRecommendView';

import {getHomeMultidata} from '@network/home';
export default {

  name: 'Home',
  components: {
  	NavBar,
  	HomeSwiper,
  	HomeRecommendView
  },
  data(){
  	return {
  		banners: [],
  		recommends: []
  	}
  },
  created() {
  	getHomeMultidata().then(res => {
  		console.log(res)
  		this.banners = res.data.banner.list;
  		this.recommends = res.data.recommend.list;
  	})
  }
}
</script>

<style lang="css" scoped>
	.home-nav{
		background: var(--color-tint);
		color: #fff;
	}
</style>