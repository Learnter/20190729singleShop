<template>
	<view class="main">
      <!-- 轮播图-->
       <uni-swiper-dot class="bannerBox" :info="swiperInfo" :current="current" :mode="mode" :dots-styles="dotsStyles">
         <swiper class="swiper-box" @change="toggleSwiper" :autoplay="autoplay" circular="true">
           <swiper-item v-for="(item ,index) in 4" :key="index">
             <view class="swiper-item" style="width:100%;height:100%;">
               <image src="/static/2019sc_5.png"  mode="scaleToFill"/>
             </view>
           </swiper-item>
         </swiper>
       </uni-swiper-dot>
       
       <view class="noticeBox">
         <!-- 公告栏 -->
         <view class="uni-swiper-msg">
         	<view class="uni-swiper-msg-icon">
         		<image src="/static/2019sc_6.png"></image>
         	</view>
         	<swiper vertical="true" autoplay="true" circular="true" interval="3000">
         		<swiper-item v-for="(item, index) in msg" :key="index">
         			<navigator>{{item}}</navigator>
         		</swiper-item>
         	</swiper>
         </view>
       </view> 
         <!-- 图片列表 -->
       <view class="pictureBox">
         <view class="big_pictures uni-flex">
           <view class="big_item">
             <image src="../../static/2019sc_5.png" mode=""></image>
           </view>
           <view class="big_item">
             <image src="../../static/2019sc_5.png" mode=""></image>
           </view>
         </view>
         <scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="0">
           <view class="small_item" v-for="(item,index) in 6" :key="index">
             <image src="../../static/2019sc_5.png" mode=""></image>
           </view>
         </scroll-view>
       </view>
       
       <!-- 限时秒杀 -->
       <view class="seckillBox">
         <view class="seckill_tips uni-flex">
           <text class="seckill_title">限时秒杀</text>
           <navigator url="" class=" look_more uni-flex">
             更多 <uni-icon type="arrowright" size="18" color="#666666" />
           </navigator>
         </view>
         <view class="seckill_shops">
           <view class="seckill_shop_item uni-flex" v-for="(item,index) in 3" :key="index">
             <view class="seckill_shop_img">
                <image src="../../static/2019sc_5.png" mode=""></image>
             </view>
             <view class="seckill_shop_content uni-flex uni-flex-item">
               <view class="seckill_shop_info uni-flex-item">
                 <text>ZGH高音入耳式耳机免费送</text>
                 <view class="uni-flex shop_price ">
                   ￥44.5 
                   <view class="shop_original_price">
                     原价<text>100</text>￥
                   </view>
                 </view>
                 <text class="time_remaining">剩余时间 23:00:00</text>
               </view>
               <view class="seckill_shop_btn">
                 立即秒杀
               </view>
             </view>
           </view>
         </view>
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
                  <image src="../../static/2019sc_5.png" mode=""></image>
               </view>
               <view class="recommend_shop_content uni-flex ">
                 <view class="recommend_shop_info uni-flex-item">
                    <text class="recommend_shop_title">修身性感包臀裙</text>
                    <view class="recommend_shop_price">
                      ￥69 <text class="payment_number">0人已付款</text>
                    </view>
                 </view>
                 <view class="shop_car">
                   <image src="../../static/2019sc_18.png" mode=""></image>
                 </view>
               </view>
            </view>
          </view>
       </view>     		
	</view>
</template>

<script>
  import uniIcon from "@/components/uni-icon/uni-icon.vue";
  import uniSwiperDot from "@/components/uni-swiper-dot/uni-swiper-dot.vue";
	export default {
    name:"fistPage",
		data() {
			return {
				 indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				modeIndex: -1,
				styleIndex: -1,
				current: 0,
				mode: 'long',
				dotsStyles: {
				  backgroundColor: 'rgba(83, 200, 249,0.3)',
				  border: '1px rgba(83, 200, 249,0.3) solid',
				  color: '#fff',
				  selectedBackgroundColor: 'rgba(83, 200, 249,0.9)',
				  selectedBorder: '1px rgba(83, 200, 249,0.9) solid',
				  width: 10,
				  height: 2
				},
				swiperInfo:[], //轮播数据
				msg : [
					'uni-app行业峰会频频亮相，开发者反响热烈的文章是您好吗',
					'DCloud完成B2轮融资，uni-app震撼发布',
					'36氪热文榜推荐、CSDN公号推荐 DCloud CEO文章'
				]
			};
		},
    methods:{
      toggleSwiper(e) {
        this.current = e.detail.current
      },
      scroll(){
        
      },
      changeTab(){
        
      },
      loadData(){
        
      }
    },
    components:{
      uniIcon,
      uniSwiperDot
    }
	}
</script>

<style lang="scss">
  .swiper-box {
      margin:5px auto;
      height:280rpx;
      overflow:hidden;
    }
    
     /* 公告栏样式 */
    .noticeBox {
      margin-bottom: 10rpx;
      .uni-swiper-msg{
         padding:12rpx;
         box-sizing:border-box;
         .uni-swiper-msg-icon{
           width:175rpx;
           height:50rpx;
         }
      }
    }
    
    /* 图片列表样式*/
    .pictureBox{
        .big_pictures{
          justify-content:space-between;
          .big_item{
            width:49.5%;
            height:180rpx;
          }
        }
        .scroll-view_H{
          	white-space: nowrap;
          	width: 100%; 
          .small_item{
            display:inline-block;
            width:25.30%;
            height:180rpx;
            padding-right:1%;
            padding-top:1%;
            box-sizing:border-box;
            &:last-child{
              padding-right:0;
            }
          }
        }
    }
    
    /* 限时秒杀样式*/
    .seckillBox{
      padding:20rpx;
      .seckill_tips{
        justify-content:space-between;
        height:40rpx;
        line-height:40rpx;
        position:relative;
          &::before{
            position:absolute;
            top:50%;
            transform:translateY(-50%);
            content:"";
            width:10rpx;
            height:100%;
            background:$uni-text-color-yellow;
            border-radius:0 50% 50% 0;
          }
          .seckill_title{
            font-weight:700;
            letter-spacing:1px;
            font-size:30rpx;
            margin-left:16rpx;
            align-content:center; 
            position:relative;
          }
        .look_more{
          align-items:center;
        }
      } 
      .seckill_shops{
        .seckill_shop_item{
         height:200rpx;
         margin-top:20rpx;
         .seckill_shop_img{
           width:200rpx;
           height:100%;
           margin-right:20rpx;
         } 
         .seckill_shop_content{
           align-items:flex-end;
           .seckill_shop_info{
            height:100%;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            .shop_price{
              color:#FF2C2C;
              font-size:30rpx;
              align-items:flex-end;
              .shop_original_price{
                padding-left:16rpx;
                font-size:24rpx;
                color:#DADADA;
                text-align: end;
              }
            }
            .time_remaining{
              color:#FBA51B;
            }
           }
           .seckill_shop_btn{
             width:160rpx;
             height:50rpx;
             line-height:50rpx;
             text-align:center;
             background:#FBA51B;
             border-radius:10rpx;
             color:#ffffff;
            }
          }
        }
      }
    }
    
    /*好物推荐样式*/
    .recommendBox{
      padding:20rpx;
       .seckill_tips{
        height:40rpx;
        line-height:40rpx;
        justify-content:space-between;
        position:relative;
          &::before{
            position:absolute;
            top:50%;
            transform:translateY(-50%);
            content:"";
            width:10rpx;
            height:100%;
            background:$uni-text-color-yellow;
            border-radius:0 50% 50% 0;
          }
          .seckill_title{
            font-weight:700;
            letter-spacing:1px;
            font-size:30rpx;
            align-content:center; 
            margin-left:16rpx;
            position:relative;
          }
        .look_more{
          align-items:center;
        }
      } 
      .recommend_shops{
        flex-wrap:wrap;
        justify-content:space-between;
        .recommend_shops_item{
          width:49%;
          margin-top:20rpx;
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
