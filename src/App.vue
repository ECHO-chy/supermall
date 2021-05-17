<template>
	<router-view></router-view>
	<MainTabBar></MainTabBar>
</template>

<script>
import MainTabBar from "@components/content/mainTabbar/MainTabBar"
export default {

  name: 'App',

  data () {
    return {

    }
  },
  components: {
  	MainTabBar
  }
}
</script>

<style>
	@import "assets/css/base.css"
</style>