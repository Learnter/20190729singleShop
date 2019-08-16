<template>
	<view>
		 <!-- #ifdef APP-PLUS | H5-->
		  <uni-nav-bar left-icon="back" title="配送地址" @click-left="back" @click-right="add" right-icon="plus-filled"/>
		<!-- #endif -->
    <view class="addressBox">
       <view class="ad_item uni-flex" v-for="(item,index) in 4" :key="index">
         <view class="ad_icon">
           <image src="/static/image/address/2019sc_96.png" mode=""></image>
         </view>
         <view class="ad_content">
           <view class="uni-flex adc_info">
             <text class="adci_name">收货人:****</text>
             <text>13718545474</text>
           </view>
           <view class="adc_address uni-flex">
             <text class="uni-ellipsis uni-flex-item">收货地址:广东省东莞市虎门镇怀德区东方商业大厦A栋1609室众冠网络有限公司</text>
             <uni-icon type="forward" size="23"></uni-icon>
           </view>
           <view class="adc_edit">
             <text>默认地址</text>
             <text>编辑</text>
             <text>删除</text>
           </view>
         </view>
       </view>
    </view>
	</view>
</template>

<script>
  import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
  import uniIcon from '@/components/uni-icon/uni-icon.vue'
	export default {
    name:"dispatch",
		data() {
			return {
				
			};
		},
    components:{
      uniNavBar,
      uniIcon
    }
	}
</script>

<style lang="scss">
  .addressBox{
    padding: 20rpx 20rpx 0;
    .ad_item{
      align-items:center;
      height:160rpx;
      margin-bottom:20rpx;
      border-bottom:1px solid rgba(0,0,0,0.2);
      padding-bottom:20rpx;
      .ad_icon{
        width:60rpx;
        height:70rpx;
        padding:0 30rpx;
      }
      .ad_content{
        flex:1;
        overflow:hidden;
        .adc_info{
          justify-content:space-between;
          .adci_name{
            font-size:32rpx;
            font-weight:700;
          }
        }
        .adc_address{
          overflow: hidden;
          justify-content:space-between;
          color:#C6C6C6;
        }
        .adc_edit{
          color:#F4A500;
          text{
            margin-right:40rpx;
          }
        }
      }
    }
  }
  

</style>
