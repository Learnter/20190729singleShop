<template>
	<view class="ornament">
    <view class="sortBoxs">
      <view class="sb_left uni-flex">
        <view class="sbls_all" @click="allSort">综合</view>
        <view class="uni-inline-item sbls_sort"  @click="saleSort">
          <text>销量</text>
          <view class="sbls_picture">
            <image src="/static/image/other/2019sc_117.png" ></image>
          </view>
         </view>
         <view class="uni-inline-item sbls_sort" @click="priceSort">
           <text>价格</text>
           <view class="sbls_picture">
             <image src="/static/image/other/2019sc_117.png" mode=""></image>
           </view>
         </view> 
       </view>
       <view class="sb_right uni-flex">
           <view class="sbr_picture" @click="styleSrot">
              <image src="/static/image/other/2019sc_109.png" mode=""></image>
           </view>
           <view class="sbr_line">
             
           </view>
           <view class="uni-inline-item" @click="otherSort">
             <text>刷选</text>
             <view class="sbr_picture">
               <image src="/static/image/other/2019sc_107.png" mode=""></image>
             </view>
           </view>
       </view> 
    </view>
    <view class="shopBoxs">
        <view class="sh_item uni-inline-item" v-for="(item,index) in 10" :key="index">
           <view class="shi_img">
             <image src="/static/2019sc_5.png" mode=""></image>
           </view>
           <view class="shi_content uni-flex-item">
             <text class="shic_title">修身性感包臀裙修身性xss包臀裙胜多负少的大城修身性感包臀裙</text>
             <text class="shic_sum">0人已付款</text>
             <text class="shic_money">￥69.9</text>
              <view class="shic_car">
                <image src="/static/2019sc_18.png" mode=""></image>
              </view>
           </view>
        </view>
    </view>
		
	</view>
</template>

<script>
	export default {
    name:"ornament",
		data() {
			return {
				
			};
		},
    methods:{
      allSort(){
        console.log("综合排序");
      },
      saleSort(){
        console.log("销量排序");
      },
      priceSort(){
        console.log("价格排序");
      },
      styleSrot(){
        console.log("样式排序");
      },
      otherSort(){
        console.log("刷选排序");
      }
    }
	}
</script>

<style lang="scss">
  
    .sortBoxs{
      height:80rpx;
      padding: 0 20rpx;
      background:#F2F2F2;
      display:flex;
      align-items:center;
      justify-content:space-between;
      line-height:1.2;
      .sb_left{
        align-items:center;
        .sbls_all{
          margin-right:80rpx;
        }
        .sbls_sort{
          margin-right:40rpx;
        }
        .sbls_picture{
          width:20rpx;
          height:25rpx;
          line-height:1;
          margin-left:6rpx;
        }
      }
      .sb_right{
        align-items:center;
        .sbr_line{
          width:4rpx;
          height:30rpx;
          background:#999999;
          margin: 0 20rpx;
        }
        .sbr_picture{
          width:24rpx;
          height:24rpx;
          line-height:1;
          margin-left:6rpx;
        }
      }
    }
  
    .shopBoxs{
      padding:20rpx 20rpx 0;
      .sh_item{
        height:180rpx;
        margin-bottom:20rpx;
        .shi_img{
          width:180rpx;
          height:180rpx;
          margin-right:20rpx;
        }
        .shi_content{
          height:100%;
          display:flex;
          flex-direction:column;
          justify-content:space-between;
          position:relative;
          overflow:hidden;
          line-height:1.2;
          .shic_title{
            font-weight:bold;
            line-height:1.4;
            overflow:hidden; 
            text-overflow:ellipsis;
            display:-webkit-box; 
            -webkit-box-orient:vertical;
            -webkit-line-clamp:2; 
              }
          .shic_sum{
            color:#999999;
            font-size:24rpx;
          }
          .shic_money{
            color:#FF0000;
            font-size:28rpx;
          }
          .shic_car{
            position:absolute;
            right:0;
            bottom:0;
            width:50rpx;
            height:50rpx;
          }
        }
      }
    }
</style>
