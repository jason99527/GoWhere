<template>
	<div>
		<div class="header">
			城市选择
			<router-link to="/">
				<span class="iconfont header-back">&#xe624;</span>
			</router-link>
		</div>
	</div>
</template>

<script>
	export default{
		name : 'CityHeader'
	}
</script>

<style lang="stylus" scoped>

@import '~style/varibles.styl'
 .header{
 	position:relative;
 	overflow:hidden;
 	heigght:.86rem;
 	line-height:.86rem;
 	text-align:center;
 	color:#fff;
 	background:$bgColor
 }
 .header-back{
 	position:absolute;
 	top:0;
 	left:0;
 	width:.64rem;
 	text-align:center;
 	font-size:.4rem;
 	color:#fff
 }
</style>