<template>
	<div>
		<home-header></home-header>
		<home-swiper></home-swiper>
		<home-icons></home-icons>
	</div>
</template>

<script>
	import HomeHeader from './components/header.vue'
	import HomeSwiper from './components/swiper.vue'
	import HomeIcons from './components/icon.vue'
	export default{
		name : 'Home',
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons
		}
	}

</script>

<style>
	
</style>