<template>
	<view>
		<view class="result" v-if="show">
			<view style="text-align: center;">
				<image
					:src="src" 
					mode="scaleToFill"
					style="width: 300px;height: 300px;border-radius: 20px;margin: 0 auto;"
					></image>
				<view class="text">
					{{ text }}
				</view>
			</view>
		</view>
		<view class="noSearch" v-if="!show">
			<view>
				<image src="../../../static/none.png" mode="aspectFill"></image>
				<view class="text">
					{{ text }}
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
				src:'../../../static/3.png',
				text:'暂时木有内容呀～～',
				userId:0,
				filePath:''
			}
		},
		methods: {
			takePicture(){
				let _self=this
				uni.chooseImage({
					count: 1,
					sizeType: ['original', 'compressed'],
					sourceType: ['camera'],
					success: function (res) {
						// console.log(JSON.stringify(res.tempFilePaths));
						_self.filePath=res.tempFilePaths[0]
						//另一种请求方式
						// _self.identify()
						uni.uploadFile({
						  url: "https://rmb.sipcoj.com/garbage/identify", 
						  filePath: _self.filePath,
						  name: "file",
						  formData: {
						    userId:_self.userId,
						    garbageId:2
						  },
						  header: {
						    "content-type": "multipart/form-data",
						  },
						  success: (res) => {
								if(res.data.code=='00000'){
									_self.show=true
									var list=res.data.data.list
									_self.src=res.data.data.url
									_self.text='此图片中包含有'
									for(var i=0;i<list.length;i++){
										_self.text=_self.text+list[i]+' '
									}
								} else {
									_self.show=false
									_self.src='../../../static/3.png'
									_self.text='暂时木有内容呀～～'
								}
							}
						});
					}
				});
			},
			identify(){
				uni.request({
					url: 'https://rmb.sipcoj.com/garbage/identify',
					method:"POST",
					data: {
						file:this.filePath,
						userId:this.userId,
						garbageId:2
					 },
					 header: {
						 "content-type":"multipart/form-data",
					 },
					 success: (res) => {
						if(res.data.code=='00000'){
							this.show=true
							var list=res.data.data.list
							this.src=res.data.data.url
							this.text='此图片中包含有'
							for(var i=0;i<list.length;i++){
								this.text=this.text+list[i]+' '
							}
						} else {
							this.show=false
							this.src='../../../static/3.png'
							this.text='暂时木有内容呀～～'
						}
					 }
				});
			},
		},
		onLoad() {
			this.userId = uni.getStorageSync('userId');
		}
	}
</script>

<style scoped lang="scss">
.noSearch {
	height: 50vh;
	display: flex;
	justify-content: center;
	align-items: center;
	margin-top: 50px;
}

.result {
	// background-color: firebrick;
	height: 50vh;
	margin-top: 70px;
	display: flex;
	justify-content: center;
	align-items: center;
}

.text {
	text-align: center;
	padding: 0 30px;
	margin-top: 30px;
	font-size: 20px;
	color: #606266;
}

.btn {
	// background-color: orange;
	position: fixed;
	bottom: 20vh;
	height: 45px;
	width: 100%;

	.pic {
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
