<template>
	<view>
		<view class="">
		<button @click="handleNavigte">跳转</button>
		<button @click="handleRadirect">重定向</button>
		</view> 

		<view class="">
			<button type="primary" @click="go()">页面刷新</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			//保留当前页面跳转到应用内的某个页面
			handleNavigte(){
				uni.navigateTo({
					url: 'learn',
				});
			},
			//关闭当前页面跳转到应用内的某个页面
			handleRadirect(){
				uni.redirectTo({
					url: 'learn',
				});
			},
			go(){
				uni.request({
					url: '',
					method: 'GET',
					data: {},
					success: res => {
						console.log(res)
						uni.showToast({
							title: '提交成功'
						});
						this.$forceUpdate();
						// uni.navigateBack();
					},
					fail: () => {},
					complete: () => {}
				});
			}
			
		}
	}
</script>

<style>

</style>
