<template>
	<view class="content">
		<image src="/static/image/invite/2019sc_94.png" mode=""></image>
    <view class="in_picture">
      <image src="/static/image/invite/2019sc_93.png" mode=""></image>
    </view>
    <view class="in_content">
       <view class="inc_title">
         分享二维码
       </view>
       <view class="qr_Code">
          <image src="/static/image/invite/2019sc_92.png" mode=""></image>
       </view>
       <view class="inc_vertical incv_left">
          <image src="/static/image/invite/2019sc_91.png" mode=""></image>
       </view>
       <view class="inc_vertical incv_right">
          <image src="/static/image/invite/2019sc_91.png" mode=""></image>
       </view>
       <text class="inc_tips">邀请好友成功,可获得80元现金抵押卷</text>
       <button class="inc_btn" type="primary">立即分享</button>
    </view>
    
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
  page,.content{
    height:100%;
    position:relative;
    overflow:hidden;
  }
  .in_picture{
    width:230rpx;
    height:212rpx;
    position:absolute;
    left:44%;
    transform:translateX(-44%);
    top:140rpx;
  }
  
  .in_content{
    position:absolute;
    left:50%;
    transform:translateX(-50%);
    top:340rpx;
    width:454rpx;
    height:579rpx;
    background:rgba(205,26,26,1);
    border-radius:12rpx;

  }
  .inc_title{
    height:100rpx;
    line-height:100rpx;
    text-align:center;
    margin:0 auto;
    font-size:40rpx;
    color:#fff;
    letter-spacing:10rpx;
    padding:30rpx 0;
  }
  .qr_Code{
   width:329rpx;
   height:329rpx;
   box-shadow:0rpx 4rpx 49rpx 0rpx rgba(55,57,61,1);
   margin:0 auto;
   padding:20rpx;
   background:#fff;
  }
  
  .inc_vertical{
     width:24rpx;
     height:187rpx;
  }
  .incv_left{
    position:absolute;
    top:0;
    left:40rpx;
   }
 .incv_right{
   position:absolute;
   top:0;
   right:40rpx;
  }
  
  .inc_tips{
    position:absolute;
    width:100%;
    top:105%;
    color:#F4A500;
    font-size:26rpx;
    text-align:center;
  }
  
  .inc_btn{
    position:absolute;
    top:120%;
    width:100%;
    height:80rpx;
    line-height:80rpx;
    background:#F4A500;
    font-size:40rpx;
    letter-spacing:10rpx;
  }

</style>
