<template>
  <div id="tab_bar">
  	<slot></slot>
  </div>
</template>

<script>
export default {

  name: 'TabBar',

  data () {
    return {

    }
  }
}
</script>

<style lang="css" scoped>
	@import '//at.alicdn.com/t/font_2490757_0p5l41ii272d.css';
  #tab_bar{
    display: flex;
    backgr#48E2E2FFound: #f6f6f6;
    box-shadow: 0px 0px 4px #a0a0a0;
    height: 90px;
    flex: 1;
    justify-content: space-around;
    align-items: center;
    position: fixed;
    left: 0;
    bottom: 0;
    right: 0;
  }
</style>