<template>
	<view>
		<view class="title">
			垃圾分类识别
		</view>
		<view class="title2">
			garbage classification
		</view>
		<view class="top" style="margin-top: 50px;">
			<view class="text">
				文字搜索
			</view>
			<view class="text2">
				search with text
			</view>
			<image src="../../static/文字.png" mode="scaleToFill" style="width: 70px;height: 70px; position: absolute; right: 60px;top: 35px;"></image>
		</view>
		<view class="top">
			<view class="text">
				拍照识别
			</view>
			<view class="text2">
				search with picture
			</view>
			<image src="../../static/相机 (1).png" mode="scaleToFill" style="width: 80px;height: 70px; position: absolute; right: 55px;top: 35px;"></image>
		</view>
		<view class="top">
			<view class="text">
				语音识别
			</view>
			<view class="text2">
				search with voice
			</view>
			<image src="../../static/语音.png" mode="scaleToFill" style="width: 70px;height: 70px; position: absolute; right: 60px;top: 35px;"></image>
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

<style scoped lang="scss">
.title{
	font-size: 30px;
	font-weight: 700;
	margin-left: 30px;
	margin-top: 50px;
	// color: #606266;
	color: #32793c;
}
.title2{
	font-size: 20px;
	font-weight: 700;
	margin-left: 30px;
	margin-top: 10px;
	// color: #606266;
	color: #32793c;
}
.top{
	height: 140px;
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
	// color: #606266;
	color: #32793c;
	font-weight: 700;
	margin-left: 35px;
	margin-top: 20px;
}
.text2{
	font-size: 15px;
	// color: #606266;
	color: #32793c;
	font-weight: 700;
	margin-left: 35px;
	margin-top: 5px;
}
</style>
