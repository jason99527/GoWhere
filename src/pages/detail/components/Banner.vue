<template>
	<div>
		<div class="banner" @click="hadleBannerClick">
			<img :src="bannerImg" alt="" class="banner-img">
			<div class="banner-info">
				<div class="banner-title">{{this.sightName}}</div>
				<div class="banner-number">{{this.gallaryImgs.length}}</div>
			</div>
		</div>
		<fade>
			<common-gallary 
			:imgs="gallaryImgs" 
			v-show="showGallary"
			@close="hadleBannerClick"></common-gallary>
		</fade>
	</div>
</template>
<script>
	import CommonGallary from 'common/gallary/Gallary'
	import Fade from 'common/fade/fade'
	export default{
		name : "DetailBanner",
		components:{
			CommonGallary,
			Fade
		},
		data(){
			return {
				showGallary:false
			}
		},
		props:{
			sightName :'',
		  	bannerImg  :'',
		  	gallaryImgs :''
		},
		methods:{
			hadleBannerClick(){
				this.showGallary = !this.showGallary
			}
		}
	}
</script>
<style lang="stylus" scoped>
	.banner{
		position:relative;
		overflow:hidden;
		height:0;
		padding-bottom:55%;
	}
	.banner-img{
		width:100%
	}
	.banner-info{
		display:flex
		position:absolute;
		left:0;
		right:0;
		bottom:0;
		line-height:.6rem;
		color:#fff;
		background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
	}
	.banner-title{
		flex:1;
		font-size:.32rem;
		padding:0 .2rem;
	}
	.banner-number{
		marign-top:.14rem
		padding:0 .4rem;
		height:.32rem;
		line-height:.32rem;
		border-radius:.2rem;
		background:rgba(0,0,0,.8);
		font-size:.24rem
	}
</style>