<template>
		<ul class="list">
			<li class="item" v-for="item of letters"
			 :key="item"
			 :ref="item"
			  @click="handleLetterClick"
			  @touchstart="handleTouchstart"
			  @touchmove="handleTouchmove"
			  @touchend="handleTouchend"
			 >{{item}}</li>
		</ul>
</template>

<script>
	export default{
		name : 'CityAlphabet',
		props:{
			cities:''
		},
		computed:{
			letters(){
				const letters = []
				for(let i in this.cities){
					letters.push(i)
				}
				return letters
			}
		},
		data(){
			return {
				touchStatus:false
			}
		},
		methods:{
			handleLetterClick(e){
				this.$emit('change',e.target.innerText)
			},
			handleTouchstart(){
				this.touchStatus = true
			},
			handleTouchmove(e){
				if(this.touchStatus){
					const startY = this.$refs['A'][0].offsetTop
					const touchY = e.touches[0].clientY - 79
					const index = Math.floor((touchY - startY)/20)
					if(index >= 0 && index<this.letters.length )
					this.$emit('change',this.letters[index])
				}
			},
			handleTouchend(){
				this.touchStatus = false
			}
		}
	}
</script>

<style lang="stylus" scoped>

@import '~style/varibles.styl'
	.list{
		position:absolute;
		display:flex;
		flex-direction: column;
		justify-content:center
		top:1.58rem;
		right:0;
		bottom:0;
		width:.4rem;
	}
	.item{
		line-height:.4rem;
		text-align:center;
		color:$bgColor
	}
</style>