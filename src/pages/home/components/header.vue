<template>
	<div>
		<div class="header">
			<div class="header-left">返回</div>
			<div class="header-input">输入城市/景点/游玩主题</div>
			<div class="header-right">城市</div>
		</div>
	</div>
</template>

<script>
	export default{
		name : 'HomeHeader'
	}
</script>

<style scoped>
.header{
	display:flex;
	height:.86rem;
	background:#00bcd4;
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
</style>