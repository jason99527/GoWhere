<template>
	<div>
	<div class="search">
		<input type="text" v-model="keyword" class="search-input" placeholder="输入城市名或拼音">
	</div>
	<div class="search-content" ref="search" v-show="keyword">
		<ul>
			<li class="search-item border-bottom" 
			v-for="item of list" 
			:key="item.id"
			@click="handleCityClick(item.name)"
			>{{item.name}}</li>
			<li class="search-item border-bottom" v-show="hasNodata">没有找到匹配数据</li>
		</ul>
	</div>
	</div>
</template>

<script>
	import Bscroll from 'better-scroll'
	import {mapMutations} from 'vuex'
	export default{
		name : 'CitySearch',
		data(){
			return{
				keyword:'',
				list:[],
				timer:null
			}
		},
		methods:{
			handleCityClick(city){
				this.changeCity(city)
				this.$router.push('/')
			},
			...mapMutations(['changeCity'])
		},
		props:{
			cities:''
		},
		watch:{
			keyword(){
				if(this.timer){
					clearTimeout(this.timer)
				}
				if(!this.keyword){
					this.list=[]
					return
				}
				this.timer = setTimeout(()=>{
					const result = []
					for(let i in this.cities){
						this.cities[i].forEach((value)=>{
							if(value.spell.indexOf(this.keyword)>-1 ||
								value.name.indexOf(this.keyword)>-1){
								result.push(value)
							}
						})
					}
					this.list = result
				},100)
			}
		},
		mounted(){
			this.scroll = new Bscroll(this.$refs.search)
		},
		computed:{
			hasNodata(){
				return !this.list.length
			}
		}
	}
</script>

<style lang="stylus" scoped>

@import '~style/varibles.styl'
 .search{
 	height:.72rem;
 	background:$bgColor;
 	padding:0 .1rem;
 }
 .search-input{
 	height:.62rem;
 	width:100%;
 	padding: 0 .1rem;
 	line-height:.62rem;
 	text-align:center;
 	border-radius:.06rem;
 	box-sizing: border-box;
 }
 .search-content{
 	z-index:1;
 	overflow:hidden;
 	position:absolute;
 	top:1.58rem;
 	left:0;
 	right:0;
 	bottom:0;
 	top:1.58rem;
 	background:#eee
 }
 .search-item{
 	line-height:.62rem;
 	padding-left:.2rem;
 	background:#fff;
 	color:#666
 }
</style>