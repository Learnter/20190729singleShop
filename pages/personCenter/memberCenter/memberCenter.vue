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
     
     <!-- 必抢好货 -->
      <view class="goodShopBox">
       <text class="gsb_title">必抢.好货</text>
       <scroll-view class="scroll-view_H"   scroll-x="true" @scroll="scroll" scroll-left="0">
         <view class="gs_list" v-for="(item,index) in 6" :key="index">
           <view class="gsl_item uni-inline-item">
             <view class="gsli_img">
                <image src="/static/2019sc_5.png" mode=""></image>
             </view>
             <view class="gsi_content">
               <view class="gsic_title">[限时三折有货]</view>
               <view class="gsic_text">仅剩235件</view>   
               <view class="uni-inline-item gsic_text">
                 <view class="gsict_img">
                   <image src="/static/image/other/2019sc_102.png" mode=""></image>
                 </view>
                 <text>立即发货</text>
               </view>
               <view class="gsic_buy uni-inline-item">
                 <uni-tag class="tagStyle" :inverted="true" :circle="true" text="立即抢购" type="error" size="small" />
                 <view class="uni-inline-item">
                    <text class="gsicb_price">原价&nbsp;:&nbsp;598￥</text>
                    <text class="gsic_title uni-flex-item">180￥</text>
                 </view>
               </view>
             </view>
            </view> 
          </view>
       </scroll-view>
     </view>
     
     <!--好物推荐-->
     <view class="goodRecommendation">
       <text class="gr_title">好物推荐</text>
       <scroll-view class="scroll-view_H"   scroll-x="true" @scroll="scroll" scroll-left="0">
         <view class="gr_list" v-for="(item,index) in 6" :key="index">
           <view class="grl_img">
             <image src="/static/2019sc_5.png" mode=""></image>
           </view>
           <view class="grl_tips">限时特价</view>
           <view class="uni-inline-item grl_price">
              <text class="gsicb_price">原价&nbsp;:&nbsp;598￥</text>
              <text class="gsic_title uni-ellipsis">180￥</text>
           </view>
          </view>
       </scroll-view>
     </view>
     
     <!--广告图片-->
     <view class="advertising">
       <image src="/static/image/other/2019sc_106.png" mode=""></image>
     </view>
     
     
        <!-- 好物推荐 -->
    <view class="recommendBox">
       <view class="seckill_tips uni-flex">
        <text class="seckill_title">好物推荐</text>
        <navigator url="" class=" look_more uni-flex">
          更多 <uni-icon type="arrowright" size="18" color="#666666" />
        </navigator>
      </view>
       <view class="recommend_shops uni-flex">
         <view class="recommend_shops_item" v-for="(item,index) in 5" :key="index">
            <view class="recommend_shop_img">
               <image src="/static/2019sc_5.png" mode=""></image>
            </view>
            <view class="recommend_shop_content uni-flex ">
              <view class="recommend_shop_info uni-flex-item">
                 <text class="recommend_shop_title">修身性感包臀裙</text>
                 <view class="recommend_shop_price">
                   ￥69 <text class="payment_number">0人已付款</text>
                 </view>
              </view>
              <view class="shop_car">
                <image src="/static/2019sc_18.png" mode=""></image>
              </view>
            </view>
         </view>
       </view>
    </view>
     
	</view>
</template>

<script>
  import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue';
  import uniTag from '@/components/uni-tag/uni-tag.vue';
  import uniIcon from "@/components/uni-icon/uni-icon.vue";
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
      uniTag,
      uniIcon
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
       // margin-bottom:20rpx;
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
  
  /* 好货.必抢*/
  .goodShopBox{
    padding:0 20rpx;
    overflow:hidden;
    .gsb_title{
      font-size:32rpx;
      font-weight:600;
      line-height:1;
      padding:16rpx 0;
      display:inline-block;
    }
      .scroll-view_H{
          box-sizing:border-box;
        	white-space: nowrap;
          overflow:hidden;
          justify-content:space-between;
          line-height:1;
           .gs_list{
            display:inline-block;
            width:100%;
            height:200rpx;
            .gsl_item{
              padding: 0 30rpx;
              .gsli_img{
                width:160rpx;
                height:160rpx;
                margin-right:30rpx;
              }
              .gsi_content{
                 flex:1;
                 .gsic_title{
                   color:#A01B27;
                   font-weight:600;
                 }
                 .gsic_text{
                   font-size:24rpx;
                   color:#B1B1B1;
                 }
                 .gsict_img{
                   width:30rpx;
                   height:30rpx;
                   overflow:hidden;
                   line-height:1;
                 }
                 .gsic_buy{
                   justify-content:space-between;
                   .gsicb_price{
                     color:#B1B1B1;
                     margin-right:10rpx;
                     position:relative;
                     &::before{
                       content:"";
                       width:100%;
                       border-bottom:1px solid #B1B1B1;
                       position:absolute;
                       top:50%;
                     }
                   }
                 }
               }
             }
          }
      }
  }
  
  /*好物推荐*/
  .goodRecommendation{
      padding:0 20rpx;
      overflow:hidden;
     .gr_title{
       font-size:32rpx;
       font-weight:600;
       line-height:1;
       padding:16rpx 0;
       display:inline-block;
     }
     .scroll-view_H{
          box-sizing:border-box;
        	white-space: nowrap;
          overflow:hidden;
          justify-content:space-between;
          line-height:1;
        .gr_list{
          display:inline-block;
          width:220rpx;
          height:250rpx;
          margin-right:16rpx;
          font-size:24rpx;
          .grl_img{
            width:220rpx;
            height:160rpx;
          }
          
          .gsic_title{
            color:#A01B27;
            font-weight:500;
          }
          
          .grl_tips{
            font-weight:600;
            line-height:1.5;
          }
          
          .grl_price{
            overflow:hidden; 
            font-size:24rpx;
          }
          
          .gsicb_price{
            color:#B1B1B1;
            margin-right:10rpx;
            position:relative;
            &::before{
              content:"";
              width:100%;
              border-bottom:2rpx solid #B1B1B1;
              position:absolute;
              top:50%;
            }
          }
        }
     }
  }
  
  /* 广告背景图样式*/
  .advertising{
    margin: 16rpx 20rpx;
    height:120rpx;
    overflow:hidden;
  }
  
  
  /*好物推荐样式*/
  .recommendBox{
    margin:0 20rpx;
     .seckill_tips{
      justify-content:space-between;
      line-height:1;
      padding:16rpx 0;
      position:relative;
      &::before{
        position:absolute;
        content:"";
        width:10rpx;
        background:$uni-text-color-yellow;
        height:50%;
        border-radius:0 50% 50% 0;
      }
        .seckill_title{
          font-weight:700;
          letter-spacing:1px;
          font-size:32rpx;
          margin-left:16rpx;
          align-content:center; 
         
        }
      .look_more{
        align-items:center;
        color:#B1B1B1;
      }
    } 
    .recommend_shops{
      flex-wrap:wrap;
      justify-content:space-between;
      .recommend_shops_item{
        width:49%;
        margin-bottom:20rpx;
        .recommend_shop_img{
          height:360rpx;
        } 
        .recommend_shop_content{
          align-items:flex-end;
          justify-content:space-between;
          padding: 0 16rpx;
          .recommend_shop_title{
            font-weight:700;
            letter-spacing:1px;
          }
          .recommend_shop_price{
            color:#FF2C2C; 
            line-height:1.2;
            .payment_number{
              font-size:20rpx;
              padding-left:16rpx;
              color:#000000;
            }  
          }
          .shop_car{
            width:50rpx;
            height:50rpx;
          }
        }
      }
    }
  }
  
  
    
    

</style>
