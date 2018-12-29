<template>
<div style="background:#eee">
	<div class="recommend-title">
		周末去哪儿
	</div>
	<ul>
		<li class="item" v-for="item of list" :key="item.id">
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
		name:"Weekend",
		data(){
			return{
				recommendLlist:[
				]
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