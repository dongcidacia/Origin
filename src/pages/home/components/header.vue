<template>
<div class="header">
	<div class = "header-left">
		<div class="iconfont back-icon">&#xe666;</div>
	</div>
	<div class="header-input">
		<span class="iconfont">&#xe67d;</span>
		输入城市景点游玩主题</div>
	<router-link to='/city'>
		<div class="header-right">{{this.city}}
			<span class="iconfont">&#xe66b;</span>
		</div>
	</router-link>
</div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
	  ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
  .header
  	line-height: .86rem
  	display: flex
  	background: $bgColor
  	color: #fff
  	.header-left
  		width: .64rem
  		float: left
		 .back-icon
		   text-align: center
		   font-size: .4rem
  	.header-input
  		flex: 1
  		margin-top: .12rem
  		height: .64rem
  		line-height: .64rem
  		margin-left: .2rem
		  padding-left: .2rem
  		background: #fff
  		border-radius: .1rem
  		color: #ccc
  	.header-right
  		min-width: 1.04rem
		  padding: .1rem
  		float: right
  		text-align: center
		  color:#fff
</style>