<template>
  <div id="tab_bar">
  	<slot></slot>
  </div>
  <div class="tab_bar_fake"></div>
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
	@import 'https://at.alicdn.com/t/font_2490757_0p5l41ii272d.css';
  #tab_bar{
    display: flex;
    background: #f6f6f6;
    box-shadow: 0px 0px 4px #fefefe;
    height: 90px;
    flex: 1;
    justify-content: space-around;
    align-items: center;
    position: fixed;
    left: 0;
    bottom: 0;
    right: 0;
  }
  .tab_bar_fake{
    height: 90px;
  }
</style>