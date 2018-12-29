<template>
	<div class="banner-box">
	 <swiper :options="swiperOption" ref="mySwiper" v-if="showSwiper">
	    <!-- slides -->
	    <swiper-slide v-for="item of list" :key="item.id">
			<img :src="item.imgUrl" alt="" class="banner" >
	    </swiper-slide>
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
	</div>
</template>
<script>
	export default{
		name : 'HomeSwiper',
		data() {
	      return {
	        swiperOption: {
	          pagination:'.swiper-pagination',
	          loop:true,
	          autoplay:3000
	        }
	      }
	    },
	    props:{
	    	list:''
	    },
	    computed:{
	    	showSwiper(){
	    		return this.list.length
	    	}
	    }
	}
</script>
<style lang="stylus" scoped>
	.banner-box >>> .swiper-pagination-bullet-active {
	  background: #ffffff
	}
	
	.banner-box
	   width:100%
	   overflow:hidden
	   padding-bottom:31.25%;
	   height:0;
	  .banner
		width:100%	
</style>