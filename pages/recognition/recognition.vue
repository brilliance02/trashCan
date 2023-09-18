<template>
	<view class="body">
		<view class="uni-margin-wrap">
			<swiper class="swiper" circular indicator-dots="true" autoplay="true" interval="2500" duration="800">
				<swiper-item>
					<image class="item" src="../../static/pic.jpg" mode="aspectFill"></image>
				</swiper-item>
				<swiper-item>
					<image class="item" src="../../static/pic3.jpg" mode="aspectFill"></image>
				</swiper-item>
				<swiper-item>
					<image class="item" src="../../static/pic2.jpg" mode="aspectFill"></image>
				</swiper-item>
				<swiper-item>
					<image class="item" src="../../static/pic4.jfif" mode="aspectFill"></image>
				</swiper-item>
			</swiper>
		</view>
		<uni-search-bar radius="5" placeholder="文字搜索识别" clearButton="auto" cancelButton="auto" @confirm="search" />
		<view class="btn">
			<view class="item">
				<view class="text">
					拍照识别
				</view>
				<view class="text2">
					search with picture
				</view>
				<image src="../../static/相机.png" mode="scaleToFill" style="width: 80px;height: 70px; position: absolute; right: 50px;bottom: 70px;"></image>
			</view>
			<view class="item">
				<view class="text">
					语音识别
				</view>
				<view class="text2">
					search with voice
				</view>
				<image src="../../static/语音 (1).png" mode="scaleToFill" style="width: 70px;height: 73px; position: absolute; right: 60px;bottom: 70px;"></image>
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
			search(res) {
				uni.showToast({
					title: '搜索：' + res.value,
					icon: 'none'
				})
			},
		}
	}
</script>

<style scoped lang="scss">
.body{
	// background-color: #40974c;
}
.uni-margin-wrap,.swiper,.item{
	height: 200px;
	width: 100%;
}
.uni-margin-wrap{
	margin-bottom: 10px;
}
.btn{
	display: flex;
	justify-content: center;
	gap:12px;
	margin-top: 20px;
	.item{
		height: 280px;
		width: 45%;
		border-radius: 10px;
		box-shadow: 0 0 5px #D4D7DE;
		position: relative;
	}
}
.text{
	display: inline-block;
	font-size: 23px;
	color: #606266;
	font-weight: 700;
	margin-left: 20px;
	margin-top: 20px;
}
.text2{
	font-size: 15px;
	color: #606266;
	font-weight: 700;
	margin-left: 20px;
	margin-top: 5px;
}
</style>
