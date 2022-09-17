<template>
	<view class="container">
		<navbar :showsearch="true" title="首页"></navbar>
		<playerbar></playerbar>
		
		<!-- {{JSON.stringify(tuijian)}} -->
	</view>
</template>

<script>
	import {
		requestGet
	} from '../../utils/http.js'
	export default {
		data() {
			return {
				tuijian:[]
			}
		},
		onLoad(){
			this.getTuijian()
		},
		methods: {
			fabClick() {
				console.log("fabClick")
			},
			//请求示例
			async getTuijian(){
				const result = await requestGet("/fm2/broadcast_list.json",{
					offset:0,
					speaker_id:0,
					rows:10,
					key:"046b6a2a43dc6ff6e770255f57328f89"
				});
				if(result.code === 0){
					this.tuijian = result.data
				}
			}
		}
	}
</script>

<style lang="less">
	.container {
		font-size: 14px;
		line-height: 24px;



	}
</style>
