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
					<image class="item" src="../../static/pic4.jpg" mode="aspectFill"></image>
				</swiper-item>
			</swiper>
		</view>
		<!-- <uni-search-bar radius="5" placeholder="文字搜索识别" clearButton="auto" cancelButton="auto" @confirm="search" /> -->
		<!-- <view class="btn">
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
		</view> -->
		<view class="top" style="margin-top: 30px;" @click="textSearch">
			<view class="text">
				文字搜索
			</view>
			<view class="text2">
				search with text
			</view>
			<image src="../../static/文字2.png" mode="scaleToFill" style="width: 70px;height: 70px; position: absolute; right: 60px;top: 35px;"></image>
		</view>
		<view class="top" @click="pictureSearch">
			<view class="text">
				拍照识别
			</view>
			<view class="text2">
				search with picture
			</view>
			<image src="../../static/相机.png" mode="scaleToFill" style="width: 80px;height: 70px; position: absolute; right: 55px;top: 35px;"></image>
		</view>
		<view class="top" @click="voiceSearch">
			<view class="text">
				语音识别
			</view>
			<view class="text2">
				search with voice
			</view>
			<image src="../../static/语音 (1).png" mode="scaleToFill" style="width: 70px;height: 70px; position: absolute; right: 60px;top: 35px;"></image>
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
			textSearch(){
				uni.navigateTo({
					url: '/pages/recognition/textSearch/textSearch'
				});
			},
			pictureSearch(){
				uni.navigateTo({
					url: '/pages/recognition/pictureSearch/pictureSearch'
				});
			},
			voiceSearch(){
				uni.navigateTo({
					url: '/pages/recognition/voiceSearch/voiceSearch'
				});
			}
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
	// margin-bottom: 10px;
}
// .btn{
// 	display: flex;
// 	justify-content: center;
// 	gap:12px;
// 	margin-top: 20px;
// 	.item{
// 		height: 280px;
// 		width: 45%;
// 		border-radius: 10px;
// 		box-shadow: 0 0 5px #D4D7DE;
// 		position: relative;
// 	}
// }
.top{
	height: 130px;
	width: 93%;
	border-radius: 10px;
	position: relative;
	box-shadow: 0 0 5px #D4D7DE;
	// box-shadow: 0 0 5px #32793c;
	// border: 2px solid #32793c;
	margin: 0 auto;
	margin-top: 20px;
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
