<template>
	<div class="icons">
		<swiper :options="swiperOption" >
			<swiper-slide v-for="(page,index) of pages" :key='index'>
				<div class="icon" v-for="(item,index) of page" :key="index">
					<div class="icon-img">
						<img :src="item.imgUrl" alt="">
					</div>
					<div class="icon-desc">
						{{item.desc}}
					</div>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>
<script>
	export default {
		name:'HomeIcons',
		data(){
			return{
				swiperOption:{

				}
			}
		},
		computed:{
			pages(){
				var pages = []
				this.list.forEach((item,index)=>{
					let page = Math.floor(index/8)
					if(!pages[page]){
						pages[page] = []
					}
					pages[page].push(item)
				})
				return pages;
			}
		},
		props:{
			list:''
		}
	}
</script>
<style lang='stylus' scoped>
@import '~style/varibles.styl'

.icons >>> .swiper-container{
	overflow:hidden 
	height:0 
	padding-bottom: 50%
}
.icon{
	overflow:hidden;
	height:0;
	width:25%
	float:left;
	padding-bottom:25%;
	position:relative;
}
.icon-img{
	position:absolute
	display:block;
	top:0;
	right:0;
	left:0;
	bottom:.4rem;
	box-sizing:border-box;
	padding:.1rem;
}
.icon-img img{
	height: 100%;
    display: block;
    margin: auto;
}
.icon-desc{
	position:absolute;
	left:0;
	right:0;
	bottom:0;
	height:.44rem;
	color:$darkTextColor;
	text-align:center
}
</style>