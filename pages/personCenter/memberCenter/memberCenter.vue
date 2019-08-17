<template>
	<view class="content">
    
		 <!-- #ifdef APP-PLUS | H5-->
		   <uni-nav-bar left-icon="back" title="会员中心" @click-left="back" />
		 <!-- #endif -->
     
     <!--会员信息-->
     <view class="member_info uni-flex"> 
       <view class="mbi_picture">
         <image src="/static/2019sc_44.png" mode=""></image>
       </view>
       <view class="mbi_content uni-flex-item">
          <view class="mbic_top ">
           <view class="mbic_name">昵&nbsp;&nbsp;&nbsp;&nbsp;称&nbsp;:&nbsp;<text>一叶知秋</text></view>
           <view class="uni-flex mbic_level">
             <view class="uni-flex uni-flex-item">
               会员等级&nbsp;:&nbsp;<text class="mbicl_text">高级会员</text>    
             </view>
             <uni-tag class="tagStyle" :inverted="true" :circle="true" text="立即升级" type="success" size="small" />
           </view>
          </view>
          <view class="mbic_bottom uni-flex">
             <view class="mbicb_itme">
                <text>0</text>
                <text>余额</text>
             </view>
             <view class="mbicb_itme">
                <text>0</text>
                <text>余额</text>
             </view>
             <view class="mbicb_itme">
                <text>0.00</text>
                <text>余额</text>
             </view>
          </view>
       </view>
     </view>
     
     <!-- 图片列表 -->
      <view class="pictureBox">
       <scroll-view class="scroll-view_H"   scroll-x="true" @scroll="scroll" scroll-left="0">
         <view class="big_item" v-for="(item,index) in 6" :key="index">
           <image src="/static/2019sc_5.png" mode=""></image>
         </view>
       </scroll-view>
     </view>
     
	</view>
</template>

<script>
  import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue';
  import uniTag from '@/components/uni-tag/uni-tag.vue'
	export default {
		data() {
			return {
				
			};
		},
    methods:{
       scroll(){
        
      }
    },
    components:{
      uniNavBar,
      uniTag
    }
	}
</script>

<style lang="scss">
  page,content{
    height:100%;
  }
  .member_info{
    box-sizing:border-box;
    height:295rpx;
    background:url("~@/static/image/center/2019sc_100.png") no-repeat;
    background-size:100% 100%;
    margin:20rpx 20rpx;
    padding:20rpx;
  }
  
  .mbi_picture{
    width:160rpx;
    height:160rpx;
    padding:10rpx;
    box-sizing:border-box;
    background:#fff;
    border-radius:50%;
    overflow:hidden;
  }
  
  .mbi_content{
    padding:20rpx 20rpx 0;
    display:flex;
    flex-direction:column;
    justify-content:space-between;
    color:#fff;
  }
  
  
  .mbic_level{
    margin-top:10rpx;
    align-items:center;
    justify-content:space-between;
    .mbicl_text{
      color:$uni-text-color-yellow;
    }
  }
  
   
  .mbic_bottom{
    margin-top:20rpx;
    height:120rpx;
    justify-content:space-between;
    .mbicb_itme{
      display:flex;
      flex-direction:column; 
      align-items:center;
    }
  }
  
   /* 图片列表样式*/
  .pictureBox{
      // .big_pictures{
      //   justify-content:space-between;
      //   .big_item{
      //     width:49.5%;
      //     height:180rpx;
      //   }
      // }
      .scroll-view_H{
          box-sizing:border-box;
          padding: 0 20rpx;
        	white-space: nowrap;
          overflow:hidden;
          justify-content:space-between;
          line-height:1;
           .big_item{
            display:inline-block;
            width:49.5%;
            height:180rpx;
            margin-right:10rpx;
          }
      }
  }

</style>
