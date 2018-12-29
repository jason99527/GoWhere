<template>
<div>
	<div class="recommend-title">
		热销推荐
	</div>
	<ul>
		<li class="item border-bottom" v-for="item of list" :key="item.id">
			<img :src="item.imgUrl" alt="">
			<div class="item-info">
				<p class="item-title">{{item.title}}</p>
				<p class="item-desc">{{item.desc}}</p>
				<div class="item-button">查看详情</div>
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
				recommendLlist:[]
			}
		},
		props:{
			list:""
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
		display: flex;
		height: 1.9rem;
		align-items: center;
		padding: 0 .1rem
	}
	img{
		width: 1.7rem;
		height: 1.7rem;
		margin-right: .1rem
	}
	.item-info{
		flex: 1
		min-width:0
	}
	.item-title{
		line-height: .54rem;
		font-size:.32rem;
		ellipsis()
	}
	.item-desc{
		line-height: .4rem;
		color:#ccc;
	}
	.item-button{
		display: table;
		background: #ff9300;
		padding:0 .1rem;
		border-radius: .06rem;
		color:#fff;
		line-height:.44rem;
		margin-top: .16rem;
	}
</style>