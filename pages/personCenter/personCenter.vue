<template>
	<view class="personCenter">
		<view class="personBox">
      <view class="person_info uni-flex">
        <view class="person_img">
          <image src="/static/2019sc_44.png"></image>
        </view>
        <view class="person_account">
           <text>账号&nbsp;:&nbsp;123456789</text>
           <view class="person_edit">
             昵称&nbsp;:&nbsp;一叶知秋
            <image src="/static/image/center/2019sc_45.png" class="editIcon"></image>
           </view>
        </view>
        <view class="setup">
          <image src="/static/image/center/2019sc_46.png"></image>
        </view>
        <view class="message">
          <image src="/static/image/center/2019sc_47.png" ></image>
          <uni-badge text="1" type="error" size="small" class="ms_badge" />
        </view>
      </view> 
      <view class="vip_card">
        <image src="/static/2019sc_48_1.png"></image>
        <view class="vip_level uni-flex">
           <image src="/static/image/center/2019sc_49.png" class="level_icon"></image>
           <text>高级会员</text>
        </view>
        <view class="b-btn">
        	立即开通
        </view>
      </view>
		</view>
    
    <view class="personContent">  
      <view class="personAsset uni-flex">  
         <view class="pa_item">
           <view>0.00</view>
           <view>余额</view>
         </view>
        <view class="pa_item">
          <view>0</view>
          <view>积分</view>
        </view>
        <view class="pa_item">
          <view>1</view>
          <view>优惠卷</view>
        </view>
      </view>
      
      <view class="order-section">
      	<view class="order-item" @click="navTo('/pages/order/order?state=0')" hover-class="common-hover"  :hover-stay-time="50">
          <view class="order-item-icon">
            <image src="/static/image/center/2019sc_50.png" class="icon_size"></image>
            <uni-badge text="1" type="error" size="small" class="or_badge" />
          </view>
      		<text>待付款</text>
      	</view>
      	<view class="order-item" @click="navTo('/pages/order/order?state=1')"  hover-class="common-hover" :hover-stay-time="50">
      		 <view class="order-item-icon">
      		  <image src="/static/image/center/2019sc_51.png" class="icon_size"></image>
      		  <uni-badge text="123" type="error" size="small" class="or_badge" />
      		</view>
      		<text>待发货</text>
      	</view>
      	<view class="order-item" @click="navTo('/pages/order/order?state=2')" hover-class="common-hover"  :hover-stay-time="50">
      		 <view class="order-item-icon">
      		  <image src="/static/image/center/2019sc_52.png" class="icon_size"></image>
      		  <uni-badge text="1" type="error" size="small" class="or_badge" />
      		</view>
      		<text>待收货</text>
      	</view>
      	<view class="order-item" @click="navTo('/pages/order/order?state=4')" hover-class="common-hover"  :hover-stay-time="50">
      	 <view class="order-item-icon">
      	  <image src="/static/image/center/2019sc_53.png" class="icon_size"></image>
      	  <uni-badge text="1" type="error" size="small" class="or_badge" />
      	</view>
      		<text>待评价</text>
      	</view>
      </view>
      </view>
      <view class="settingBox">
        <uni-list>
        	<uni-list-item title="我的优惠卷" thumb="/static/image/center/2019sc_54.png" />
          <uni-list-item title="我的收货地址" thumb="/static/image/center/2019sc_55.png" />
          <uni-list-item title="设置" thumb="/static/image/center/2019sc_56.png" />
          <uni-list-item title="通知" thumb="/static/image/center/2019sc_57.png" />
          <uni-list-item title="充值中心" thumb="/static/image/center/2019sc_58.png" />
          <uni-list-item title="版本更新" thumb="/static/image/center/2019sc_59.png" />
        </uni-list>
    </view>
	</view>
</template>

<script>
  import uniList from '@/components/uni-list/uni-list.vue';
  import uniListItem from '@/components/uni-list-item/uni-list-item.vue';
  import uniBadge from '@/components/uni-badge/uni-badge.vue'
	export default {
    name:"personCenter",
		data() {
			return {
				
			};
		},
    components: {
    	uniList,
    	uniListItem,
      uniBadge
    }
	}
</script>

<style lang="scss" scoped>
  
  .icon_size{
    width:50rpx;
    height:50rpx;
  }
  
  %flex-center {
   display:flex;
   flex-direction: column;
   justify-content: center;
   align-items: center;
  }
  
  %section {
    display:flex;
    justify-content: space-around;
    align-content: center;
    background: #fff;
    border-radius: 10upx;
  }
  
  .personBox{
    width: 100%;
    height:360rpx;
    box-sizing: border-box;
    padding: 50rpx 20rpx 0;
    text-align:center;
    position:relative;
    background:url("~@/static/2019sc_121.png");
    background-size:100% 100%;
    background-repeat: no-repeat;
    .person_info{
      height:160rpx;
      padding:20rpx 0;
      position:relative;
      .setup{
        position:absolute;
        right:0;
        top:0;
        width:44rpx;
        height:44rpx;
      }
      .message{
        position:absolute;
        right:0;
        top:104rpx;
        width:44rpx;
        height:44rpx;
        .ms_badge{
          position:absolute;
          right:-6rpx;
          bottom:50%;
        }
      }
      .person_img{
        width:140rpx;
        height:140rpx;
        border-radius:50%;
        padding:10rpx;
        background:whitesmoke;
      }
      .person_account{
        flex:1;
        display:flex;
        flex-direction:column;
        justify-content: space-between;
        align-items:flex-start;
        padding:20rpx;
        font-size:32rpx;
        color:#ffffff;
        letter-spacing:2rpx;
        .person_edit{
          position:relative;
          font-size:32rpx;
          .editIcon{
            width:36rpx;
            height:36rpx;
            margin-left:20rpx;
            vertical-align:middle;
          }
        }
      }
    }
    .vip_card{
      margin-top:44rpx;
      height:84rpx;
      position:relative;
      .vip_level{
        position: absolute;
        left:20rpx;
        top: 16rpx;
        height: 40rpx;
        line-height:40rpx;
        color:#ffd465;
        align-items:center;
        .level_icon{
          width:40rpx;
          height:40rpx;
          margin-right:20rpx;
        }
      }
       .b-btn{
       	position: absolute;
       	right: 20upx;
       	top: 16upx;
       	width: 132upx;
       	height: 40upx;
       	text-align: center;
       	line-height: 40upx;
       	font-size: 22upx;
       	color: #36343c;
       	border-radius: 20px;
       	background: linear-gradient(left, #f9e6af, #ffd465);
       	z-index: 1;
       }
     }
  }
  .personContent{
    padding: 0 20rpx;
    text-align:center;
    .personAsset{
      padding:20rpx 0;
      height:120rpx;
      border:1px solid #EBEBED;
      border-radius:10rpx;
      justify-content:space-around;
      align-items:center;
    }
    .order-section{
    	@extend %section;
    	padding: 28rpx 0;
    	margin-top: 20rpx;
      background:#F9F9F9;
    	.order-item{
    		@extend %flex-center;
    		width: 120rpx;
    		height: 120rpx;
    		border-radius: 10rpx;
        .order-item-icon{
          position:relative;
          .or_badge{
            position:absolute;
            right:-40%;
            top:-20rpx;
          }
        }
    	}
    }
  }

  .settingBox{
    padding:20rpx;
    .uni-list{
    &::before,&::after{
      display:none;
    }
  }
 }
</style>
