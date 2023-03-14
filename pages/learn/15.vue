<template>
	<view>
		<view class="" style="display: flex;justify-content: space-between;">
			<view class="">
				<text>厂区</text>
			</view>
		<view class="" style="display: flex;justify-content: space-between;">
			<view class="" style="background: red;margin-right: 200rpx;">
				<text>厂区厂区<厂区<厂区</text>
			</view>
			<view class="" style="background: blue;">
				dsds
			</view>
		</view>
		</view>
		
		
			<view class="border" style="margin-bottom: 20rpx;">
				<input type="text" placeholder="昵称/手机/邮箱" style="border-bottom: 1rpx black;padding: 20rpx;" />
			</view>
		<view class="border" style="display: flex;margin-bottom:20rpx;align-items: stretch;">
			<input type="text" placeholder="请输入密码" style="padding-bottom: 20rpx;flex: 1;" />
			<view class="" style="display: flex;align-items: center;justify-content: center; background: blue;">
				dsds
			</view>
		</view>
<!-- 		<view class="">
		<template> -->
			<view class="" style="margin-bottom: 20rpx;margin: 20rpx;">
				<input type="" v-model="username" placeholder="昵称/手机号/邮箱" class="border" style="padding: 20rpx;"/>
			</view>
			<view class="border" style="margin: 20rpx; margin-bottom: 20rpx;display: flex;align-items: stretch;">
				<view class="border" style="display: flex; align-items: center;justify-content: center; width: 150rpx;">忘记密码？</view>
				<input type="" v-model="password" placeholder="请输入密码" class="border" style="padding: 20rpx;flex: 1;"/>
				<view class="border" style="display: flex; align-items: center;justify-content: flex-end; width: 200rpx;">忘记密码？</view>
				<image class="border" src="../../static/location.png" style="display: flex; align-items: center;justify-content: flex-end; width: 50rpx;height: 86rpx;" mode=""></image>
			</view>
	<!-- 	</template>
		</view> -->
		
		<view class="" >
			<view class="" style="margin: 20rpx;display: flex;align-items: center;">
			<text style="width: 150rpx;">旧密码：</text>
			<input class="uni-input" type="password" placeholder="请输入密码" v-model="oldpassword" />
			</view>
			<view class="" style="margin: 20rpx;display: flex;align-items: center;">
			<text style="width: 150rpx;">新密码：</text>
			<input class="uni-input" type="password" placeholder="请输入密码" v-model="newpassword" />
			</view>
			<view class="" style="margin: 20rpx; display: flex;align-items: center;">
			<text style="width: 150rpx;">确认密码：</text>
			<input class="uni-input" type="password" placeholder="请输入密码" v-model="renewpassword" />
			</view>
			<view class="">
				<button @click="submit" type="primary" :disabled="disabled" :class="disabled? 'bg-disabled':''">设置</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				oldpassword:"",
				newpassword:"",
				renewpassword:"",
			}
		},
		computed:{
			disabled(){
				return this.oldpassword==''||this.newpassword==''||this.renewpassword==''
			}
		},
		methods: {
			check(){
				if (this.newpassword !==this.renewpassword){
					uni.showToast({
						title: '两次密码不一致'
					});
					return false
				}
				return true
			},
			submit(){
				if (!this.check()){
					return;
				}
				uni.showToast({
							title: '提交成功'
						});
				// uni.navigateTo({
				// 	url: '../learn/01',
				// 	success: res => {
				// 	},
				// 	fail: () => {},
				// 	complete: () => {}
				// });
			}
			
		}
	}
</script>

<style>
	.bg-disabled{
		background-color: #b0b0b0!important;
		/* color: #b0b0b0; */
	}
	.border { 
		border: 1rpx solid #dee2e6;
		}
</style>
