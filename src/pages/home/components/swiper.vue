<template>
	<div class="banner-box">
	 <swiper :options="swiperOption" ref="mySwiper" >
	    <!-- slides -->
	    <swiper-slide v-for="item of swiperList">
			<img :src="item.imgUrl" alt="" class="banner" :key="item.id">
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
	          loop:true
	        },
	        swiperList:[{
	        	id:'01',
	        	imgUrl:'http://img1.qunarzz.com/piao/fusion/1809/12/856f100069809e02.jpg_750x200_e3485a2b.jpg'
	        },{
	        	id:'02',
	        	imgUrl:'http://img1.qunarzz.com/piao/fusion/1812/d6/daa880b254940402.jpg_750x200_b114308a.jpg'
	        },{
	        	id:'03',
	        	imgUrl:'http://img1.qunarzz.com/piao/fusion/1811/7c/8e5c4ab8ee8b7402.jpg_750x200_dd7a38dd.jpg'
	        }]
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
	   padding-bottom:calc(100vw * (1 / 3.75));
	   height:0;
	  .banner
		width:100%	
</style>