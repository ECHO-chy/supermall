<template>
	<div class="tab_bar_item" @click="itemClick">
    <div :style="isActive">
      <slot name="item-icon"></slot>
      <slot name="item-text"></slot>
    </div>
  </div>
</template>

<script>
export default {

  name: 'TabBarItem',
  props: {
  	path: String,
    activeStyle: {
      type: String,
      default: '#f00'
    }
  },
  computed: {
    isActive() {
      // return !this.$route.path.indexOf(this.path)
      // return this.$route.path.includes(this.path)
      return this.$route.path.includes(this.path) ? {color: this.activeStyle,transition: '0.2s'} : {}
    },
    activeColor() {
      return {color: this.activeStyle}
    }
  },
  methods: {
  	itemClick() {
  		this.$router.push(this.path)
  	}
  }
}
</script>

<style lang="css" scoped>
  .tab_bar_item{
    text-align: center;
  }
</style>