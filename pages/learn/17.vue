<template>
	<view style="flex-direction: column;">
		<view class="" style="display: flex;">
			<text>a：</text>
			<input type="text" value="" v-model="a" />
		</view>
		<view class="" style="display: flex;">
			<text>b：</text>
			<input type="text" value="" v-model="b" />
		</view>
		<view class="" style="display: flex;">
			<text>c：</text>
			<text>{{c}}</text>
		</view>
		<view class="" style="display: flex;">
			<text>d：</text>
			<text>{{d}}</text>
		</view>
		<view class="" style="display: flex;">
			<text>e：</text>
			<text>{{e}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				a:"1",
				b:"2",
				c:"",
				d:"",
				e:"",
			}
		},
		onLoad() {
			this.getData()
		},
		methods: {
			getData(){
					this.c=Number(this.a)+Number(this.b)//字符串转换为数字
					this.d=String(this.a)+String(this.b)//数字转换为字符串
					this.e=parseInt(this.a)+parseInt(this.b)//字符串转换为数字
			},
		}
	}
</script>

<style>

</style>
