<template>
	<div class="container" @click="handleGallaryClick">
		<div class="wapper">
			<swiper :options="swiperOption" >
			    <!-- slides -->
			    <swiper-slide v-for="(item,index) in imgs" :key="index">
					<img alt="" class="img" :src="item">
			    </swiper-slide>
			   
			    <!-- Optional controls -->
			    <div class="swiper-pagination"  slot="pagination"></div>
			</swiper>
		</div>
	</div>
</template>
<script>
	export default{
		name:'CommonGallary',
		props:{
			imgs:{
				type:Array
			}
		},
		data(){
			return{
				swiperOption:{
					pagination:'.swiper-pagination',
					paginationType:'fraction',
					observer:true,
					observeParents:true,
				}
			}
		},
		methods:{
			handleGallaryClick(){
				this.$emit('close')
			}
		}
	}
</script>
<style lang="stylus" scoped>
	.wapper >>> .swiper-wrapper{
		align-items:center
	}
	.wapper >>> .swiper-container{
		overflow:inherit
		
	}
	.container{
		z-index:99;
		display:flex;
		flex-direction:column;
		justify-content:center
		position:fixed;
		left:0;
		right:0;
		top:0;
		bottom:0;
		background:#000
	}
	.wapper{
		width:100%
	}
	.img{
		width:100%
	}
	.swiper-pagination{
		color:#fff;
		bottom:-1rem;
	}
</style>