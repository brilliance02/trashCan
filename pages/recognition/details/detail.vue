<template>
  <view class="all">
    <view class="noSearch" v-if="!trashList.length">
      <view>
        <image src="../../../static/none.png" mode="aspectFill"></image>
        <view class="text"> 暂时木有内容呀~~ </view>
      </view>
    </view>
    <view class="card-box" v-for="(item, index) in trashList" :key="index">
      <view class="card">
        <img :src="item.img" alt="" style="height: 100%" />
        <img src="../../../static/1.png" alt="" style="height: 100%" />
      </view>
    </view>
  </view>
</template>

<script>
export default {
  onPullDownRefresh() {
    setTimeout(() => {
      uni.stopPullDownRefresh();
    }, 1000);
    this.getList();
  },
  data() {
    return {
      trashList: [
        {
          id: 0,
          img: "https://img2.baidu.com/it/u=682045266,716038761&fm=253&fmt=auto&app=138&f=PNG?w=281&h=243",
        },
        {
          id: 0,
          img: "https://img2.baidu.com/it/u=682045266,716038761&fm=253&fmt=auto&app=138&f=PNG?w=281&h=243",
        },
      ],
    };
  },
  mounted() {
    this.getList();
  },
  methods: {
    getList() {
      console.log("获取");
    },
  },
};
</script>

<style scoped lang="scss">
.all {
  min-height: 100vh;
  background-color: #f3f3f3;
  display: flex;
  flex-direction: column;
  align-items: center;
  .card-box {
    box-sizing: border-box;
    padding: 10px;
    width: 100%;
    height: 160px;
    .card {
      box-sizing: border-box;
      display: flex;
      justify-content: space-around;
      align-items: center;
      width: 100%;
      height: 100%;
      border-radius: 10px;
      background-color: #fff;
      padding: 10px;
    }
  }
}
.noSearch {
  height: 50vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 50px;
  .text {
    text-align: center;
    margin-top: 30px;
    font-size: 20px;
    color: #606266;
  }
}
</style>