<template>
	<div class="nav-bar">
		<div class="left"><slot name="left"></slot></div>
		<div class="center"><slot name="center"></slot></div>
		<div class="right"><slot name="right"></slot></div>
	</div>
	<div class="nav-bar-fake"></div>
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
		background: var(--color-tint);
		color: #fff;
		height: 90px;
		line-height: 90px;
		text-align: center;
		box-shadow: 0px 1px 2px 0px rgb(125 125 125 / 20%);
		position: fixed;
		left: 0;
		right: 0;
		top: 0;
		z-index: 9;
	}
	.nav-bar-fake{
		height: 90px;
	}
	.left,.right{
		width: 200px;
	}
	.center{
		flex: 1;
	}
</style>