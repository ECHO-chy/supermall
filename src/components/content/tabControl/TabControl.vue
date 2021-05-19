<template>
	<div class="tabControl" :style="{background: theme}">
		<div v-for="(item, index) in titles"
			@click="tabControlActive(index)">
			<span :class="{active: index === currentIndex}">{{item}}</span>
		</div>
	</div>
</template>

<script>
export default {
  name: 'TabControl',
  props: {
  	titles: {
  		type: Array,
  		default() {
  			return []
  		}
  	},
  	theme: {
  		type: String,
  		default: "#fff"
  	}
  },
  data() {
  	return {
  		currentIndex: 0
  	}
  },
  methods: {
  	tabControlActive(index) {
  		this.currentIndex = index;
      this.$emit('tabClick', index)
  	}
  }
}
</script>

<style lang="css" scoped>
	.tabControl{
		display: flex
	}
	.tabControl div{
		flex: 1;
		line-height: 90px;
		text-align: center;
	}
	.active{
		color: var(--color-high-text);
		border-bottom: 6px solid var(--color-tint);
		padding: 10px;
		transition: 0.2s;
	}
</style>