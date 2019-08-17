<template>
	<view class="content">
		<!-- #ifdef APP-PLUS | H5-->
		 <uni-nav-bar left-icon="back" title="我的优惠卷" @click-left="back" />
		<!-- #endif -->
    <view class="navBox uni-flex">
      <view class="nav_item"  v-for="(item,nIndex) in navList" :key="nIndex" :class="tabCurrentIndex == nIndex ? 'active' : ''"  @click="toggleNav(nIndex)">{{item.name}}</view>
    </view>
    
    <swiper :current="tabCurrentIndex" class="swiper-box" duration="500" @change="changeTab">
    	<swiper-item class="tab-content" v-for="(tabItem,tabIndex) in navList" :key="tabIndex">
    		<scroll-view 
    			class="list-scroll-content" 
    			scroll-y
    			@scrolltolower="loadData"> <!--loadData为加载数据的方法 -->
    			<!-- 空白页 -->
    		 <!-- 	<empty v-if="tabItem.loaded === true && tabItem.orderList.length === 0"></empty> -->
    			
    			<!-- 订单列表 -->
    			<view v-for="(item,index) in 6" :key="index" class="order-item"> 
    				 <image src="/static/2019sc_90.png" v-if="tabCurrentIndex == 0"></image>
             <image src="/static/2019sc_95.png" v-else></image>
             <text class="cpi_amount">￥30</text>
             <text class="cpi_validity">有效期&nbsp;:&nbsp;2019.2.3-2019.2.18</text>
             <text class="cpi_useTime">满300时可使用</text>
             <text class="cpi_button">去使用</text>
    			</view>
    				
    				<!-- <scroll-view v-if="item.goodsList.length > 1" class="goods-box" scroll-x>
    					<view
    						v-for="(goodsItem, goodsIndex) in item.goodsList" :key="goodsIndex"
    						class="goods-item"
    					>
    						<image class="goods-img" :src="goodsItem.image" mode="aspectFill"></image>
    					</view>
    				</scroll-view>
    				<view 
    					v-if="item.goodsList.length === 1" 
    					class="goods-box-single"
    					v-for="(goodsItem, goodsIndex) in item.goodsList" :key="goodsIndex"
    				>
    					<image class="goods-img" :src="goodsItem.image" mode="aspectFill"></image>
    					<view class="right">
    						<text class="title clamp">{{goodsItem.title}}</text>
    						<text class="attr-box">{{goodsItem.attr}}  x {{goodsItem.number}}</text>
    						<text class="price">{{goodsItem.price}}</text>
    					</view>
    				</view>
    				
    				<view class="price-box">
    					共
    					<text class="num">7</text>
    					件商品 实付款
    					<text class="price">143.7</text>
    				</view>
    				<view class="action-box b-t" v-if="item.state != 9">
    					<button class="action-btn" @click="cancelOrder(item)">取消订单</button>
    					<button class="action-btn recom">立即支付</button>
    				</view>
    			</view> -->
    			 
    			<!-- <uni-load-more :status="tabItem.loadingType"></uni-load-more> -->
    			
    		</scroll-view>
    	</swiper-item>
    </swiper>
	</view>
</template>

<script>
  import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
  import uniIcon from '@/components/uni-icon/uni-icon.vue'
	export default {
		data() {
			return {
        tabCurrentIndex:0,
				navList:[{id:1,name:"未使用"},{id:2,name:"已使用"},{id:3,name:"已过期"}]
			};
		},
    methods:{
      changeTab(e){ //左右滑动轮播
        this.tabCurrentIndex = e.target.current;
      },
      loadData(){
        console.log("加载更多。。。");
      },
      toggleNav(val){
        this.tabCurrentIndex = val;
      }
    },
    components:{
      uniIcon,
      uniNavBar
    }
	}
</script>

<style lang="scss">
  
  page,.content{
  	height: 100%;
  }
  
  /* 导航栏的样式*/
 .navBox{
   padding: 0 20rpx;
   height:80rpx;
   justify-content:space-between;
   align-items:center;
   .nav_item{
     width:33%;
     text-align:center; 
     position:relative;
     &.active{
     	color:#F4A500;
      font-size:32rpx;
     	&:after{
     		content: '';
     		position: absolute;
     		left: 50%;
     		top:110%;
     		transform: translateX(-50%);
     		width:110rpx;
     		height:8rpx;
     		background:repeating-linear-gradient(120deg, green 10%,#F4A500 20%);
        border-radius:5rpx;
        
     	}
     }
   }
 }
 
 /*优惠卷明细样式*/
   /* #ifdef APP-PLUS |H5*/
      .swiper-box{
        height: calc(100% - 40px - 44px);
      }
   /* #endif */
   
   /* #ifdef MP */
     .swiper-box{
      height: calc(100% - 40px);
      }
   /* #endif */
 
 .list-scroll-content{
 	height: 100%;
 }
 
 .order-item{
   box-sizing:border-box;
   height:200rpx;
   padding:20rpx 20rpx 0;
   position:relative;
   .cpi_amount{
     position:absolute;
     left: 70rpx;
     top: 40rpx;
     font-size:50rpx;
     color: red;
   }
   .cpi_validity{
     position:absolute;
     left:60rpx;
     bottom:20rpx;
     font-size:24rpx;
   }
   .cpi_useTime{
     position:absolute;
     right:90rpx;
     top:50rpx;
     color:orangered;
   }
   .cpi_button{
     position:absolute;
     right:90rpx;
     bottom:20rpx;
     width:150rpx;
     height:44rpx;
     line-height:44rpx;
     text-align:center;
     border:1px solid #F4A500;
     border-radius:40rpx;
     color:#fff;
     background:#F4A500;
   }
 }
 
</style>
