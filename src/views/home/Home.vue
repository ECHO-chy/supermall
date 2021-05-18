<template>
	<div id="home">
		<nav-bar>
			<template #center>购物街</template>
		</nav-bar>
		<HomeSwiper :banners="banners"/>
		<HomeRecommendView :recommends="recommends"/>
		<FeatureView/>
    <TabControl class="tabControl" :titles="['流行', '新款', '精选']"/>
    <ul>
      <li v-for="item in 100">111111</li>
    </ul>
	</div>
</template>

<script>
import NavBar from '@components/common/navbar/NavBar';
import TabControl from '@components/content/tabControl/TabControl';

import HomeSwiper from './childComps/HomeSwiper';
import HomeRecommendView from './childComps/HomeRecommendView';
import FeatureView from './childComps/FeatureView';

import { getHomeMultidata, getHomeGoods } from '@network/home';
export default {

  name: 'Home',
  components: {
  	NavBar,
    TabControl,
  	HomeSwiper,
  	HomeRecommendView,
  	FeatureView
  },
  data(){
  	return {
  		banners: [],
  		recommends: [],
      goods: {
        'pop': {page: 0, list: []},
        'new': {page: 0, list: []},
        'sell': {page: 0, list: []},
      }
  	}
  },
  methods: {
    //请求首页的HomeSwiper、HomeRecommendView、FeatureView数据
    getHomeMultidata() {
      getHomeMultidata().then(res => {
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
      })
    },
    getHomeGoods(type){
      const page = this.goods[type].page + 1;
      getHomeGoods(type, page).then(res => {
        this.goods[type].list.push(...res.data.list);
        this.goods[type].page += 1;
      })
    }
  },
  created() {
    //请求首页的HomeSwiper、HomeRecommendView、FeatureView数据
  	this.getHomeMultidata();
    //请求商品数据
    this.getHomeGoods('pop');
    this.getHomeGoods('new');
    this.getHomeGoods('sell');
  }
}
</script>

<style lang="css" scoped>
  .tabControl{
    position: sticky;
    top: 90px;
  }
</style>