<template>
	<view>
   <!-- #ifdef APP-PLUS|H5 -->
      <uni-nav-bar left-icon="back" title="消息" @click-left="back" />
    <!-- #endif -->
    <view class="noticeBox">
      <view class="notice_item uni-flex">
        <view class="notice_picture">
           <image src="/static/image/notice/2019sc_77.png"></image>
        </view>
        <view class="notice_content uni-flex">
          <view class="notice_left">
              <view class="uni-ellipsis notice_title">交易物流通知</view>
              <view class="uni-ellipsis">你购买的潮州车厘子48/斤已近寄送到您的家里</view>
          </view>
          <view class="notice_right">
             <view>17:28</view>
             <uni-badge text="1" type="error" size="small" />
          </view>
        </view>
      </view>
      <view class="notice_item uni-flex">
        <view class="notice_picture">
           <image src="/static/image/notice/2019sc_78.png"></image>
        </view>
        <view class="notice_content uni-flex">
          <view class="notice_left">
              <view class="uni-ellipsis notice_title">交易物流通知</view>
              <view class="uni-ellipsis">你购买的潮州车厘子48/斤已近寄送到您的家里</view>
          </view>
          <view class="notice_right">
             <view>17:28</view>
             <uni-badge text="1" type="error" size="small" />
          </view>
        </view>
      </view>
      <view class="notice_item uni-flex">
        <view class="notice_picture">
           <image src="/static/image/notice/2019sc_79.png"></image>
        </view>
        <view class="notice_content uni-flex">
          <view class="notice_left">
              <view class="uni-ellipsis notice_title">交易物流通知</view>
              <view class="uni-ellipsis">你购买的潮州车厘子48/斤已近寄送到您的家里</view>
          </view>
          <view class="notice_right">
             <view>17:28</view>
             <uni-badge text="1" type="error" size="small" />
          </view>
        </view>
      </view>
      <view class="notice_item uni-flex">
        <view class="notice_picture">
           <image src="/static/image/notice/2019sc_80.png"></image>
        </view>
        <view class="notice_content uni-flex">
          <view class="notice_left">
              <view class="uni-ellipsis notice_title">交易物流通知</view>
              <view class="uni-ellipsis">你购买的潮州车厘子48/斤已近寄送到您的家里</view>
          </view>
          <view class="notice_right">
             <view>17:28</view>
             <uni-badge text="1" type="error" size="small" />
          </view>
        </view>
      </view>
      <view class="notice_item uni-flex">
        <view class="notice_picture">
           <image src="/static/image/notice/2019sc_81.png"></image>
        </view>
        <view class="notice_content uni-flex">
          <view class="notice_left">
              <view class="uni-ellipsis notice_title">交易物流通知</view>
              <view class="uni-ellipsis">你购买的潮州车厘子48/斤已近寄送到您的家里</view>
          </view>
          <view class="notice_right">
             <view>17:28</view>
             <uni-badge text="1" type="error" size="small" />
          </view>
        </view>
      </view>
    </view>
	</view>
</template>

<script>
 import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
 import uniBadge from '@/components/uni-badge/uni-badge.vue'
	export default {
		data() {
			return {
				
			};
		},
    onPullDownRefresh() { //监听用户下拉刷新
      
    },
    components:{
      uniNavBar,
      uniBadge
    }
	}
</script>

<style lang="scss">
  .noticeBox{
    padding:0 20rpx;
    .notice_item{
      align-items:center;
      width:100%;
      height:120rpx;
      padding: 20rpx 0;
      border-bottom:1px solid rgba(92,92,92,0.2);
      overflow:hidden;
      .notice_picture{
        width:100rpx;
        height:100rpx;  
      }
      .notice_content{
        flex:1;
        padding-left:20rpx;
        overflow:hidden;
        color:#999;
        .notice_left{
          overflow:hidden;
          .notice_title{
            font-size:32rpx;
            font-weight:700;
            color:#000000;
          }
         }
        .notice_right{
          width:20%;
          text-align:end;
        }
      } 
    }
  }
  
   /deep/.uni-navbar--shadow{
    box-shadow: none;
  }

</style>
