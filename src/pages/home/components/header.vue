<template>
	<div>
		<div class="header">
			<div class="header-left">
				<span class="iconfont back-icon">&#xe624;</span>
			</div>
			<div class="header-input">
				<span class="iconfont">
					&#xe632;
				</span>
				输入城市/景点/游玩主题
			</div>
			<div class="header-right">
				城市
				<span class="iconfont arrow-icon">
					&#xe64a;
				</span>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name : 'HomeHeader'
	}
</script>

<style lang="stylus" scoped>

@import '~style/varibles.styl'

.header{
	display:flex;
	height:.86rem;
	background:$bgColor;
	color:#fff;
	align-items: center;
}
.header-left{
	width:.64rem;
}
.header-input{
	flex:1;
	background: #fff;
	border-radius:.1rem;
	margin:.12rem .2rem;
	height: .62rem;
	box-sizing: border-box;
	color:#ccc;
	line-height: .62rem;
	padding-left: .1rem
}
.header-right{
	width: 1.24rem;
	text-align:center;
}
.back-icon{
	margin-left:.1rem;
	font-size:.4rem;
}
.arrow-icon{
	font-size:.24rem;
}
</style>