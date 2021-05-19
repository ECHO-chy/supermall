<template>
	<div id="home">
		<nav-bar>
			<template #center>购物街</template>
		</nav-bar>
		<home-swiper :banners="banners"/>
		<home-recommend-view :recommends="recommends"/>
		<feature-view/>
    <tab-control class="tabControl"
      :titles="['流行', '新款', '精选']"
      @tabClick="tabClick"
      />
    <goods-list :goodsList="showGoods"/>
	</div>
</template>

<script>
import NavBar from '@components/common/navbar/NavBar';
import TabControl from '@components/content/tabControl/TabControl';
import GoodsList from '@components/content/goods/GoodsList';

import HomeSwiper from './childComps/HomeSwiper';
import HomeRecommendView from './childComps/HomeRecommendView';
import FeatureView from './childComps/FeatureView';

import { getHomeMultidata, getHomeGoods } from '@network/home';
export default {

  name: 'Home',
  components: {
  	NavBar,
    TabControl,
    GoodsList,
  	HomeSwiper,
  	HomeRecommendView,
  	FeatureView,
  },
  data(){
  	return {
  		banners: [],
  		recommends: [],
      goods: {
        'pop': {page: 0, list: []},
        'new': {page: 0, list: []},
        'sell': {page: 0, list: []},
      },
      currentType: "pop"
  	}
  },
  computed: {
    showGoods() {
      return this.goods[this.currentType].list
    }
  },
  methods: {
    /**
     * 事件监听相关的方法
     */
     tabClick(index) {
      switch (index) {
        case 0:
        this.currentType = 'pop'
        break
        case 1:
        this.currentType = 'new'
        break
        case 2:
        this.currentType = 'sell'
        break
      }
     },


    /**
     * 网络请求相关的方法
     */
    //请求首页的HomeSwiper、HomeRecommendView、FeatureView数据
    getHomeMultidata() {
      getHomeMultidata().then(res => {
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
      })
    },
    //请求商品数据
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