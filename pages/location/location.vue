<template>
    <view class="content">
      <map style="width: 100%;height:100vh"
		:show-location='true'  
	  :latitude="latitude" :longitude="longitude" :markers="marker" 
	  :scale="scale"  @markertap="markertap"   @callouttap='callouttap'
	  >
       </map>
    </view>
</template>

<script>
    export default {
        data() {
            return {
				latitude:39.110388, //纬度
				longitude:117.196269,//经度
				scale:13,//缩放级别
				bottomData:false,
				marker: [
					{
						id:0,
						latitude: 39.110388,//纬度
						longitude: 117.196269,//经度
						iconPath: '',    //显示的图标  
						width:20,   //宽
						height:30,   //高
						//   title:'我在这里',//标注点名
						alpha:0.7,   //透明度
						callout:{//自定义标记点上方的气泡窗口 点击有效  
							content:'五大道',//文本
							color:'#ffffff',//文字颜色
							fontSize:14,//文本大小
							borderRadius:15,//边框圆角
							borderWidth:'10',
							bgColor:'#68AD33',//背景颜色
							display:'ALWAYS',//常显
						},
					},
					{ 
						id:5,
						latitude:  39.121607,//纬度
						longitude: 117.192895,//经度
						iconPath: '',    //显示的图标    
						width:20,   //宽
						height:30,   //高
						alpha:0.7,   //透明度
						callout:{//自定义标记点上方的气泡窗口 点击有效  
							content:'天津站',//文本
							color:'#ffffff',//文字颜色
							fontSize:14,//文本大小
							borderRadius:15,//边框圆角
							borderWidth:'8',
							bgColor:'#D25555',//背景颜色
							display:'ALWAYS',//常显
						},
					},
					{
						id:6,
						latitude:  39.121807,//纬度
						longitude: 117.243153,//经度
						iconPath: '',    //显示的图标        
						rotate:0,   // 旋转度数
						width:20,   //宽
						height:30,   //高
						alpha:0.7,   //透明度
						callout:{//自定义标记点上方的气泡窗口 点击有效  
							content:'巴拉巴拉',//文本
							color:'#ffffff',//文字颜色
							fontSize:14,//文本大小
							borderRadius:10,//边框圆角
							borderWidth:'5',
							bgColor:'#F0A010',//背景颜色
							display:'ALWAYS',//常显
						},
					}
				],
            }
        },
        onLoad() {

        },
        computed:{
		},
        methods:{
			//地图点击事件
            markertap(e) {
                console.log("===你点击了标记点===",e)
                },
            //地图点击事件
            callouttap(e){
                console.log('地图点击事件',e)
        }
        }
    }
</script>