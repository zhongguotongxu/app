<template>
	<view>
		<view class="" v-for="(item,index) in banner" :key="index">
			<image :src="item.productImageBig" mode="widthFix"></image>
		</view>
		<!-- <button @click="btn">点击</button> -->
		<!-- <view class="" v-for="(item,index) in newsList" :key="index">
			<text selectable>
				{{item}}
			</text>
		</view> -->
		<view class="">
			<text selectable>
				hello
			</text>
		</view>
		<view class="">
			<text selectable>
				hello
			</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				newsList:['新闻1','新闻2','新闻3'],
				banner:[],
			}
		},
		onPullDownRefresh() {
			console.log("下拉刷新")
			this.newsList=['新闻3','新闻2','新闻1']
			uni.stopPullDownRefresh()
		},
		onReachBottom() {
			console.log('页面到达底部')
		},
		onLoad() {
			this.getList()
		},
		
		methods: {
			btn(){
			uni.startPullDownRefresh({
				
			})	
			},
			getList(){
				uni.request({
					url: 'http://api.mm2018.com:8090/api/goods/home',
					method: 'GET',
					data: {},
					success: res => {
						let object=res.data.result[0]
						console.log(res.data.result[0])
						this.banner=object.panelContents
					},
					fail: () => {},
					complete: () => {}
				});
			},
		}
	}
</script>

<style>

</style>
