<template>
	<div>
		<div class="item" v-for="(item,index) of list" 
		:key="index"
		>
			<div class="item-title border-bottom">
				<span class="item-title-icon"></span>
				{{item.title}}
			</div>	
			<div v-if="item.children" class="item-children">
				<detail-list :list="item.children"></detail-list>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name : 'DetailList',
		props:{
			list:Array
		}
	}
</script>

<style lang="stylus" scoped>

@import '~style/varibles.styl'
	.item-title{
		line-height: .8rem;
		font-size:.32rem;
		padding:0 .2rem;
	}
	.item-title-icon{
	    display: inline-block;
		width: 0.36rem;
		height: 0.36rem;
		margin-right: 0.1rem;
		background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png)no-repeat;
		background-position-y: -0.34rem;
		background-size: .36rem;
		position: relative;
	    left: 0.06rem;
	    top: 0.04rem;
	}
	.item-children{
		padding:0 .2rem
	}
</style>