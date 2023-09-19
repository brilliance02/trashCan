<template>
	<view class="all">
		<view class="search">
			<uni-search-bar
			placeholder="文字搜索识别" 
			clearButton="auto" 
			cancelButton="auto"
			@confirm="search" />
		</view>
		<view class="result" v-if="show">
			<view class="">
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
			<image 
				src="../../../static/缺省页_搜索无结果.png" 
				mode="aspectFill" 
				></image>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:true,
				src:'../../../static/4.png',
				text:'此垃圾属于厨余垃圾'
			}
		},
		methods: {
			search(){
				console.log(555)
			}
		}
	}
</script>

<style scoped lang="scss">
.search{
	width: 90%;
	margin: 0 auto;
	margin-top: 40px;
}
.noSearch{
	height: 50vh;
	display: flex;
	justify-content: center;
	align-items: center;
}
.result{
	// background-color: firebrick;
	height: 50vh;
	margin-top: 50px;
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
</style>
