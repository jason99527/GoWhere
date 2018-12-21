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
				iconList:[{
					id:'01',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc:'热门景点'
				},{
					id:'02',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
					desc:'深圳必游'
				},{
					id:'03',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
					desc:'游乐场'
				},{
					id:'04',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
					desc:'海洋馆'
				},{
					id:'01',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc:'热门景点'
				},{
					id:'02',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
					desc:'深圳必游'
				},{
					id:'03',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
					desc:'游乐场'
				},{
					id:'04',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
					desc:'海洋馆'
				},{
					id:'01',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc:'热门景点'
				},{
					id:'02',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
					desc:'深圳必游'
				},{
					id:'03',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
					desc:'游乐场'
				},{
					id:'04',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
					desc:'海洋馆'
				}],
				swiperOption:{

				}
			}
		},
		computed:{
			pages(){
				var pages = []
				this.iconList.forEach((item,index)=>{
					let page = Math.floor(index/8)
					if(!pages[page]){
						pages[page] = []
					}
					pages[page].push(item)
				})
				return pages;
			}
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