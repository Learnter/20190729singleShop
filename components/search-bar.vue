<template>
	<view>
		<view class="searchBox uni-flex">
		  <uni-icon type="scan" size="25"></uni-icon>
		  <view class="uni-flex-item inputBox uni-flex">
		    <uni-icon type="search" size="25"></uni-icon>
		    <input type="text" class="uni-flex-item" value="" placeholder="请输入您想收搜商品的关键字" placeholder-class="inputHolder">
		  </view>
		  <uni-icon type="chat" size="25"></uni-icon>
		</view>
	</view>
</template>

<script>
  import uniIcon from "@/components/uni-icon/uni-icon.vue";
	export default {
		data() {
			return {
				
			};
		},
    components:{
      uniIcon
    }
	}
</script>

<style lang="scss">
  .searchBox{
    height:60rpx;
    padding:20rpx;
    align-items:center;
    .inputBox{
      align-items:center;
      height:60rpx;
      padding: 0 10rpx;
      margin: 0 20rpx;
      background:#F3F3F3;
      border-radius:10rpx;
      .inputHolder{
        letter-spacing:2rpx;
        font-size:28rpx;
        padding-left:10rpx;
      }
    }
  }
</style>
