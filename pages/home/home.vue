<template>
	<view>
    <uni-nav-bar :fixed="false" color="#333333" background-color="#FFFFFF" left-icon="scan" right-icon="chat" @click-left="scan" @click-right="message">
    	<view class="input-view">
    		<uni-icon type="search" size="22" color="#666666" />
    		<input confirm-type="search" class="input" type="text" placeholder="输入搜索关键词" @confirm="confirm" />
    	</view>
    </uni-nav-bar>
    
    <wuc-tab :tab-list="tabList" :tabCur.sync="TabCur" @change="tabChange" selectClass="selectNav"></wuc-tab>
    
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
        <scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
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
  import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue";
  import uniIcon from "@/components/uni-icon/uni-icon.vue";
  import WucTab from '@/components/wuc-tab/wuc-tab.vue';
  import uniSwiperDot from "@/components/uni-swiper-dot/uni-swiper-dot.vue";
	export default {
		data() {
			return {
				 TabCur:0,
         tabList: [{ name: '精选' }, { name: '订阅' },{ name: '精选' }, { name: '订阅' },{ name: '精选' }, { name: '订阅' },{ name: '精选' }, { name: '订阅' },{ name: '精选' }, { name: '订阅' },{ name: '精选' }, { name: '订阅' }],
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
     tabChange(index) {
            this.TabCur = index;
        },
      scan(){
        
      },
      message(){
        
      },
      toggleSwiper(e) {
        this.current = e.detail.current
      },
      scroll(){
        
      }
    },
    components: {uniNavBar,uniIcon,WucTab,uniSwiperDot}
	}
</script>

<style lang="scss" scoped>
  // page {
  // 	display: flex;
  // 	flex-direction: column;
  // 	box-sizing: border-box;
  // 	background-color: #fff
  // }
  // 
  /deep/.uni-navbar__header{
    padding:0 16rpx;
    box-sizing:border-box;
  }
  /deep/.uni-navbar__header-btns{
    width:auto;
  }
  .input-view {
  	display: flex;
  	background-color: #e7e7e7;
  	height:60rpx;
  	border-radius: 30rpx;
  	padding: 0 4%;
  	flex-wrap: nowrap;
  	margin: 14rpx 0;
  	line-height: 60rpx;
  }
  
  .input-view .uni-icon {
  	line-height: 60rpx !important;
  }
  
  .input-view .input {
  	height: 60rpx;
  	line-height: 60rpx;
  	width: 94%;
  	padding: 0 3%;
  }
  
  /deep/.selectNav{
    font-weight:700;
    font-size:32rpx;
    color:#FBA51B;
    transition:all 0.8s ease;
  }
  
  /deep/.wuc-tab-item{
     height:80rpx;
     line-height:80rpx;
  }
  
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
          .seckill_title{
            font-weight:700;
            letter-spacing:1px;
            font-size:30rpx;
            align-content:center; 
            position:relative;
            // ::before{
            //   position:absolute;
            //   width:6rpx;
            //   height:100%;
            //   content:"";
            //   background:#FBA51B;
            // }
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
        justify-content:space-between;
          .seckill_title{
            font-weight:700;
            letter-spacing:1px;
            font-size:30rpx;
            align-content:center; 
            position:relative;
            // ::before{
            //   position:absolute;
            //   width:6rpx;
            //   height:100%;
            //   content:"";
            //   background:#FBA51B;
            // }
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
