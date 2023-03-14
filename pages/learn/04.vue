<template>
	<view>
		<view class="top">
			smartiscan
		</view>
		<view class="banner">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" circular="">
				<swiper-item>
					<view class="swiper-item">123</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">456</view>
				</swiper-item>
			</swiper>
			
		</view>
		<view class="index_ad">
			<view class="index_ad_item">
				<image src="../../static/c1.png" mode="widthFix"></image>
			</view>
			<view class="index_ad_item">
				<image src="../../static/c2.png" mode="widthFix"></image>
			</view>
			<view class="index_ad_item">
				<image src="../../static/c3.png" mode="widthFix"></image>
			</view>
			<view class="index_ad_item">
				<image src="../../static/c4.png" mode="widthFix"></image>
			</view>
		</view>
		<view class="index_hotDtail">
			<view class="index_hotDtail_menu">
				热门商品
			</view>
			<view class="index_hotDtail_main">
				<view class="index_hotDtail_main_item">
					<image src="../../static/shuijiao.jpg" mode="widthFix"></image>
					<text>商品名称</text>
					<text>商品价格</text>
				</view>
				<view class="index_hotDtail_main_item">
					<image src="../../static/shuijiao.jpg" mode="widthFix"></image>
					<text>商品名称</text>
					<text>商品价格</text>
				</view>
			</view>
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
			
		}
	}
</script>

<style>
.top{
	width: 750rpx;
	height: 80rpx;
	background: #000;
	line-height: 80rpx;
	text-align: center;
	color: #fff;
}
.banner{
	width: 750rpx;
	height: 300rpx;
	background: #c0c0c0;
}
.index_ad{
	width: 700rpx;
	border: 2rpx solid #dbdbdb;
	margin: 0 auto;
	margin-top: 30rpx;
	border-radius: 10rpx;
	overflow: hidden;
	border-right: 0rpx;
	border-bottom: 0rpx;
}
.index_ad_item{
	width: 50%;
	float: left;
	border-right: 2rpx solid #dbdbdb;
	box-sizing: border-box;
	border-bottom: 2rpx solid #dbdbdb;
}
.index_ad_item image{
	width: 100%;
	display: block;
}
.index_hotDtail{
	/* overflow: hidden; */
	width: 700rpx;
	margin: 0 auto;
	margin-top: 30rpx;
}
.index_hotDtail_menu{
	width: 700rpx;
	font-size: 28rpx;
	font-weight: bold;
	color: #5e5e5e;
	margin-bottom: 30rpx;
}
.index_hotDtail_main{
	width: 700rpx;
	display: flex;
	justify-content: space-between;
	/* flex-direction: row; */
}
.index_hotDtail_main_item{
	width: 337rpx;
	background: #f2f2f2;
	/* height: 300rpx; */
	border-radius: 10rpx;
	overflow: hidden;
	padding-bottom:20rpx;
}
.index_hotDtail_main_item image{
	width: 60%;
	display: block;
	margin: 0 auto;
	margin-top: 30rpx;
	margin-bottom: 20rpx;
}
.index_hotDtail_main_item text{
	display: block;
	text-align: center;
	font-size: 28rpx;
	line-height: 40rpx;
}
</style>
