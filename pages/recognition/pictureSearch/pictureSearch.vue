<template>
	<view>
		<view class="result" v-if="show">
			<view>
				<image
					:src="src" 
					mode="scaleToFill"
					style="width: 300px;height: 300px;border-radius: 20px;"
					></image>
				<view class="text">
					{{text}}
				</view>
			</view>
		</view>
		<view class="noSearch" v-if="!show">
			<view>
				<image
					src="../../../static/缺省页_搜索无结果.png" 
					mode="aspectFill" 
					></image>
				<view class="text">
					{{text}}
				</view>
			</view>
		</view>
		<view class="btn">
			<view class="pic" @click="takePicture">
				点击拍照识别
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:false,
				src:'../../../static/4.png',
				text:'暂时木有内容呀～～'
			}
		},
		methods: {
			takePicture(){
				uni.chooseImage({
					count: 1, //默认9
					sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
					sourceType: ['camera'], //从相册选择
					success: function (res) {
						console.log(JSON.stringify(res.tempFilePaths));
					}
				});
			}
		},
		onLaunch() {
			
		}
	}
</script>

<style scoped lang="scss">
.noSearch{
	height: 50vh;
	display: flex;
	justify-content: center;
	align-items: center;
	margin-top: 50px;
}
.result{
	// background-color: firebrick;
	height: 50vh;
	margin-top: 70px;
	display: flex;
	justify-content: center;
	align-items: center;
}
.text{
	text-align: center;
	margin-top: 30px;
	font-size: 20px;
	color: #606266;
}
.btn{
	// background-color: orange;
	position: fixed;
	bottom: 20vh;
	height: 45px;
	width: 100%;
	.pic{
		text-align: center;
		font-size: 20px;
		width: 88%;
		margin: 0 auto;
		line-height: 45px;
		color: #606266;
		border-radius: 8px;
		// border: 1px solid #606266;
		box-shadow: 0 0 5px #D4D7DE;
	}
}
</style>
