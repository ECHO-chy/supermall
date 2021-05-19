<template>
  <TabBar>
    <TabBarItem path='/home' activeStyle='#FF8198'>
      <template #item-icon>
        <i class="iconfont icon-001_shouye"></i>
      </template>
      <template #item-text>
        <div>首页</div>
      </template>
    </TabBarItem>
    <TabBarItem path='/category' activeStyle='#FF8198'>
      <template #item-icon>
        <i class="iconfont icon-001_fenlei"></i>
      </template>
      <template #item-text>
        <div>分类</div>
      </template>
    </TabBarItem>
    <TabBarItem path='/cart' activeStyle='#FF8198'>
      <template #item-icon>
        <i class="iconfont icon-001_gouwuche"></i>
      </template>
      <template #item-text>
        <div>购物车</div>
      </template>
    </TabBarItem>
    <TabBarItem path='/profile'>
      <template #item-icon>
        <i class="iconfont icon-001_wode"></i>
      </template>
      <template #item-text>
        <div>我的</div>
      </template>
    </TabBarItem>
  </TabBar>
</template>

<script>
import {TabBar, TabBarItem} from '@components/common/tabbar'
export default {

  name: 'MainTabBar',

  data () {
    return {

    }
  },
  components: {
    TabBar,
    TabBarItem
  }
}
</script>

<style lang="css" scoped>
.iconfont{
  font-size: 50px
}
</style>