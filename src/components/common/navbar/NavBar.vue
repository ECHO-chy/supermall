<template>
	<div class="nav-bar">
		<div class="left"><slot name="left"></slot></div>
		<div class="center"><slot name="center"></slot></div>
		<div class="right"><slot name="right"></slot></div>
	</div>
</template>

<script>
export default {

  name: 'NavBar',

  data () {
    return {

    }
  }
}
</script>

<style lang="css" scoped>
	.nav-bar{
		display: flex;
		height: 90px;
		line-height: 90px;
		text-align: center;
		box-shadow: 0px 1px 2px 0px rgb(125 125 125 / 20%);
	}
	.left,.right{
		width: 200px;
	}
	.center{
		flex: 1;
	}
</style>