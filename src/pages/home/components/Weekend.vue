<template>
<div style="background:#eee">
	<div class="recommend-title">
		周末去哪儿
	</div>
	<ul>
		<li class="item" v-for="item of recommendLlist" :key="item.id">
			<img :src="item.imgUrl" alt="">
			<div class="item-info">
				<p class="item-title">{{item.title}}</p>
				<p class="item-desc">{{item.desc}}</p>
			</div>
		</li>
	</ul>
</div>
</template>
<script>
	export default{
		name:"HomeRecommend",
		data(){
			return{
				recommendLlist:[{
					id:'0101',
					imgUrl:'http://img1.qunarzz.com/sight/source/1505/fa/ca65fde9677de2.jpg_r_640x214_4500e3ff.jpg',
					title:'深圳必打卡',
					desc:'来到深圳，你需要来这里签到'
				},
				{
					id:'0110',
					imgUrl:'http://img1.qunarzz.com/sight/source/1505/b9/f9d8ace21c06.jpg_r_640x214_1f239a81.jpg',
					title:'粤东泡汤好去处',
					desc:'全时四季的温泉，度假的天堂，这里独特的矿物质温泉是您养生、养颜疗神的宝地'
				},{
					id:'012',
					imgUrl:'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
					title:'南国冰雪乐园',
					desc:'这里可以让你在南国感受到北国风光，让南国的你“零距离”感受北国银装素裹壮观之景'
				}
				]
			}
		}
	}
</script>
<style lang="stylus" scoped>

  @import '~style/mixins.styl'
	
	.recommend-title{
		line-height: .8rem;
		background: #eee;
		text-indent: .2rem
	}
	.item{
		//display: flex;
		//height: 1.9rem;
		align-items: center;
		margin-bottom:0.1rem;
		background:white
		//padding: 0 .1rem
	}
	img{
		width: 100%;
	}
	.item-info{
		flex: 1
		min-width:0;
		padding:.1rem .2rem
	}
	.item-title{
		line-height: .54rem;
		font-size:.28rem;
		ellipsis()
	}
	.item-desc{
		line-height: .4rem;
		font-size:.24rem;
		color:#616161;
		ellipsis()
	}
</style>