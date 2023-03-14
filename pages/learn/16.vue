<template>
	<view>
		<view class="mb-2 flex align-stretch">
			<view class="border-bottom flex align-center justify-center font px-2">+86</view>
			<input type="text" v-model="phone" placeholder="手机号" class="border-bottom p-2 flex-1"/>
		</view>
		<input class="uni-input" type="text" v-model="email" placeholder="请输入你要绑定的邮箱"/>
		
		<view class="py-2 px-3">
			<button class="bg-main text-white" style="border-radius: 50rpx;border: 0;" type="primary" @click="submit">绑定</button>
		</view>
	</view>
</template>

<script>
	// import {mapState} from 'vuex';
	export default {
		data() {
			return {
				email:"",
				phone:"",
			}
		},
		onLoad() {
			
		},
		methods: {
			checkPhone(){
				var rule = /^1[34578]\d{9}$/; 
				if (!rule.test(this.phone)) {
					uni.showToast({
						title:"手机号格式不正确",
						icon:"none"
					})
					return false;
				}
				return true
			},
			checkEmail(){
				let rule = /^([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2,4})$/;
				if (!rule.test(this.email)) {
					uni.showToast({
						title:"邮箱格式不正确",
						icon:"none"
					})
					return false;
				}
				return true
			},
			submit(){
				if (!this.checkPhone()) {
					return;
				};
				if (!this.checkEmail()) {
					return;
				};
		
			}
		}
	}
</script>

<style>

</style>
