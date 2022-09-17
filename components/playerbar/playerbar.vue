<template>
	<view class="music" @click="goplayer">
		<image class="icon" :class="{anim:isplayer}" src="../../static/images/music.png" mode="widthFix"></image>
	</view>
</template>

<script>
	export default {
		name:"playerbar",
		data() {
			return {
				//控制小音乐图标旋转，这边数据应该放到vuex中
				isplayer:true
			};
		},
		methods:{
			goplayer(){
				console.log("来到播放页面")
			}
		}
	}
</script>

<style lang="less">
.music{
	position: fixed;
	right: 20px;
	bottom: 30px;
	width: 50px;
	height: 50px;
	background-color: rgba(120, 120, 110, 0.5);
	border-radius: 10px;
	display: flex;
	justify-content: center;
	align-items: center;
	.icon{
		width: 60%;
		height: 60%;
		
	}
	.anim{
		animation: mymove 3.0s linear 0s infinite;
	}
	
	@keyframes mymove {
		from{
			transform: rotate(0deg);
		}
		to{
			transform: rotate(360deg);
		}
	}
}
</style>