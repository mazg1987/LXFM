<template>
	<uni-nav-bar statusBar="true" shadow fixed="true">
		<view class="title">
			{{title}}
			<uni-icons v-if="showsearch" class="search" type="search" size="20" @click="gosearch"></uni-icons>
		</view>
	</uni-nav-bar>
</template>

<script>
	export default {
		name: "navbar",
		props: ['title', 'showsearch'],
		data() {
			return {
				
			};
		},
		methods: {
			gosearch() {
				console.log("来到搜索")
			}
		}
	}
</script>

<style lang="less" scoped>
	.title {
		width: 100%;
		text-align: center;
		line-height: 44px;
		font-size: 14px;
		position: relative;

		.search {
			position: absolute;
			right: 30px;
		}
	}
</style>
