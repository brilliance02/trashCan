<template>
	<view>
		<view class="score">
			<image
				src="@/static/score.png" 
				mode="scaleToFill"
				style="width: 100px;height: 100px;border-radius: 20px;"
			></image>
			<view class="text">
				我的积分:{{score}}分
			</view>
		</view>
		<view class="text1">
			好物兑换
		</view>
		<view class="goods">
			<view class="item">
				<image
					src="@/static/phone.png" 
					mode="scaleToFill"
					style="width: 100px;height: 100px;margin-top: 30px;"
				></image>
				<view class="name">
					头戴式蓝牙耳机
				</view>
				<view class="price">
					1000分
				</view>
				<view class="btn" @click="toggle()">
					兑换
				</view>
			</view>
			<view class="item" >
				<image
					src="@/static/object.png" 
					mode="scaleToFill"
					style="width: 100px;height: 100px;margin-top: 30px;"
				></image>
				<view class="name">
					保温水杯
				</view>
				<view class="price">
					200分
				</view>
				<view class="btn"  @click="toggle()">
					兑换
				</view>
			</view>
			<view class="item">
				<image
					src="@/static/object2.png" 
					mode="scaleToFill"
					style="width: 100px;height: 100px;margin-top: 30px;"
				></image>
				<view class="name">
					20000毫安充电宝
				</view>
				<view class="price">
					500分
				</view>
				<view class="btn"  @click="toggle()">
					兑换
				</view>
			</view>
			<view class="item">
				<image
					src="@/static/object3.png" 
					mode="scaleToFill"
					style="width: 100px;height: 100px;margin-top: 30px;"
				></image>
				<view class="name">
					碳素签字笔
				</view>
				<view class="price">
					100分
				</view>
				<view class="btn" @click="toggle()">
					兑换
				</view>
			</view>
			<view class="item">
				<image
					src="@/static/object4.png" 
					mode="scaleToFill"
					style="width: 100px;height: 100px;margin-top: 30px;"
				></image>
				<view class="name">
					毛绒玩具
				</view>
				<view class="price">
					500分
				</view>
				<view class="btn" @click="toggle()">
					兑换
				</view>
			</view>
		</view>
		<view>
			<uni-popup ref="popup" background-color="#fff">
				<view style="padding: 50px 30px;">
					<uni-forms ref="baseForm" :modelValue="baseFormData" class="popup">
						<uni-forms-item label="收件人" required>
							<uni-easyinput v-model="baseFormData.name" placeholder="请输入收件人姓名" />
						</uni-forms-item>
						<uni-forms-item label="电话" required>
							<uni-easyinput v-model="baseFormData.phone" placeholder="请输入电话" />
						</uni-forms-item>
						<uni-forms-item label="收货地" required>
							<uni-easyinput v-model="baseFormData.address" placeholder="请输入收货地址" />
						</uni-forms-item>
					</uni-forms>
					<button type="primary" size="mini" style="float: right;"
					@click="change"
					>一键兑换</button>
				</view>
			</uni-popup>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				baseFormData: {
					name: '',
					phone:'',
					address:''
				},
				score:200
			}
		},
		methods: {
			toggle() {
				if(3<2){
					uni.showToast({
						title: '积分不足',
						icon:'error',
						duration: 2000
					});
				}else{
					this.$refs.popup.open()
				}
			},
			change(val) {
				console.log(555)
				uni.showToast({
					title: '兑换成功',
					duration: 2000
				});
			},
		}
	}
</script>

<style scoped lang="scss">
.score{
	text-align: center;
	// background-color: red;
	margin-top: 30px;
	padding-bottom: 30px;
	border-bottom: 2px dotted #D4D7DE;
	.text{
		font-size: 20px;
		font-weight: 700;
		color: #1296db;
	}
}
.text1{
	font-size: 18px;
	font-weight: 700;
	color: gray;
	padding-left: 30px;
	margin-top: 20px;
}
.goods{
	width: 90%;
	margin: 0 auto;
	// background-color: red;
	display: flex;
	justify-content: space-between;
	flex-wrap: wrap;
	padding-bottom: 30px;
	.item{
		display: inline-block;
		// margin-left: 20px;
		border-radius: 5px;
		height: 270px;
		width: 45%;
		border: 1px solid #D4D7DE;
		text-align: center;
		margin-top: 20px;
		.name{
			margin-top: 25px;
			color: #606266;
		}
		.price{
			margin-top: 15px;
			color: #1296db;
		}
		.btn{
			color: #606266;
			margin-top: 15px;
			height: 30px;
			line-height: 30px;
			font-weight: 700;
			border-top: 1px solid #D4D7DE;
			// background-color: rebeccapurple;
		}
		
	}
}
.popup{
	padding: 20px;
}
</style>
