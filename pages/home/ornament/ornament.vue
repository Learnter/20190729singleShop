<template>
	<view class="ornament">
    <uni-popup :show="true" :h5Top="true" position="bottom" class="on_popup">
    	<view class="mask_content">
    	  <view>
           <view class="mac_title">折扣与服务</view> 
             <scroll-view scroll-x class="macx_scroll">
                <text class="mac_tag" v-for="(item,index) in 5" :key="index">八折</text>
             </scroll-view>
             <scroll-view scroll-x class="macx_scroll">
                <text class="mac_tag">包邮</text>
                <text class="mac_tag">不包邮</text>
             </scroll-view>
        </view>
    	  <view>
          <view class="mac_title">价格区间</view> 
          <view class="uni-inline-item mac_inputs">
            <input type="number" value="" placeholder="最低价" class="mac_input"/>
            <view class="mac_line"></view>
            <input type="number" value=""  placeholder="最高价" class="mac_input"/>
          </view>
        </view>
    	  <view>
          <view class="mac_title">发货地</view> 
          <view class="uni-inline-item">
            <view class="mac_position uni-inline-item">
              <uni-icon type="location" size="20" color="#FBA51B"></uni-icon>
              <text>东莞</text>
            </view>
            <view class="uni-inline-item mac_location">
              <text style="margin-right:10rpx">定位</text>
              <uni-icon type="loop" size="15" color="#333333"></uni-icon>
            </view>
          </view>
        </view>
        <view class="uni-inline-item mac_btton">
          <button type="primary" class="macb_reset">重置</button>
          <button type="primary" class="macb_confirm">确认</button>
        </view>
    	</view>
    </uni-popup>
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
           <view class="sbr_line"></view>
           <view class="uni-inline-item" @click="otherSort">
             <text>刷选</text>
             <view class="sbr_picture">
               <image src="/static/image/other/2019sc_107.png" mode=""></image>
             </view>
           </view>
       </view> 
    </view>
      
    
    <view class="shopBoxsV" v-if="arrangeVertical">
        <view class="sh_item" v-for="(item,index) in 10" :key="index">
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
    <view class="shopBoxsH" v-else>
      <view class="sh_item" v-for="(item,index) in 10" :key="index">
         <view class="shi_img">
           <image src="/static/2019sc_5.png" mode=""></image>
         </view>
           <view class="shi_content uni-flex-item" >
             <view class="shic_left">
               <text class="uni-ellipsis">修身性感包臀裙</text>
               <text class="uni-ellipsis shic_money">￥89.9 <text class="shic_sum">500人已付款</text></text>
             </view>
             <view class="shic_car">
               <image src="/static/2019sc_18.png" mode=""></image>
             </view>
           </view>
        </view>
      </view>  
    </view>
      
	</view>
</template>

<script>
  import uniPopup from '@/components/uni-popup/uni-popup.vue';
  import uniTag from '@/components/uni-tag/uni-tag.vue';
  import uniIcon from '@/components/uni-icon/uni-icon.vue';
	export default {
    name:"ornament",
		data() {
			return {
				arrangeVertical:false //排列样式
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
    },
    components:{
      uniPopup,
      uniTag,
      uniIcon
    }
	}
</script>

<style lang="scss" scoped>
  
    .ornament{
      position:fixed;
      left:0;
      right:0;
      top:0;
      bottom:0;
    }
  
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
    
  /*横排商品列表样式*/  
  .shopBoxsH{
   position:absolute;
   top:80rpx;
   left:0;
   right:0;
   bottom:0;
   overflow-y:scroll;
   padding:20rpx 20rpx 0;
   display:flex;
   flex-wrap:wrap;
   justify-content:space-between;
    .sh_item{
      width:49%;
      margin-bottom:10rpx;
      .shi_img{
        width:100%;
        height:300rpx;
      }
      .shi_content{
        box-sizing:border-box;
        height:100rpx;
        display:flex;
        align-items:flex-end;
        justify-content:space-between;
        padding:10rpx 20rpx;
        .shic_left{
          flex:1;
          height:100%;
          line-height:1.5;
          margin-right:10rpx;
          overflow:hidden;
          color:#454545;
          display:flex;
          flex-direction:column;
          justify-content:space-between;
          .shic_sum{
            color:#999999;
            font-size:20rpx;
            margin-left:10rpx;
           }
          .shic_money{
            color:#FF0000;
            font-size:26rpx;
          }
        }
        .shic_car{
          width:50rpx;
          height:50rpx;
        }
      }
    }
  }  
    
    
  
    /* 竖排商品列表样式*/
    .shopBoxsV{
      position:absolute;
      top:80rpx;
      left:0;
      right:0;
      bottom:0;
      overflow-y:scroll;
      padding:20rpx 20rpx 0;
      .sh_item{
        height:180rpx;
        margin-bottom:20rpx;
           display: flex;
           flex-direction: row;
           align-items:center;
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
            color:#454545;
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
            font-size:20rpx;
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
    
     /deep/.uni-popup-bottom{
       padding:20rpx;
       box-sizing:border-box;
    } 
 
      /deep/.uni-input-wrapper{
       box-sizing:border-box;
       padding:10rpx 20rpx;
    }
    /deep/.uni-input-placeholder{
      text-align:center;
    }
  .mask_content{
    width:100%;
    text-align:left;
    .mac_title{
      font-size:32rpx;
      color:#454545;
      font-weight:700;
      margin-bottom:10rpx;
    }
    .macx_scroll{
      height:60rpx;
      line-height:60rpx;
      white-space:nowrap;
      margin-bottom:10rpx;
    }
    
    .mac_inputs{
      justify-content:space-between;
      margin-bottom:16rpx;
      .mac_line{
        flex:1;
        margin:0 20rpx;
        height:4rpx;
        background:#999999;
        border-radius:4rpx;
      }
    }
    .mac_input{
      width:250rpx;
      height:50rpx;
      background:#F1F1F1;
      border-radius:10rpx;
    }
    .mac_tag{
      width:150rpx;
      height:50rpx;
      line-height:50rpx;
      color:#666666;
      background:#F1F1F1;
      display:inline-block;
      text-align:center;
      border-radius:40rpx;
      margin-right:10rpx;
    }
    
    .mac_position{
      width:140rpx;
      height:50rpx;
      line-height:50rpx;
      overflow:hidden;
      background: #F1F1F1;
      text-align:center;
      border-radius:10rpx;
      margin-right:40rpx;
    }
    .mac_location{
      width:120rpx;
      height:50rpx;
     justify-content:center;
     background: #F1F1F1;
     border-radius:10rpx;
    }
    .mac_btton{
      justify-content:flex-end;
      margin:10rpx 0;
      .macb_reset{
        width:150rpx;
        height:80rpx;
        line-height:80rpx;
        background:#F6D0D5;
        margin:0;
        border-radius:0;
        margin-right:20rpx;
      }
      .macb_confirm{
        width:150rpx;
        height:80rpx;
        line-height:80rpx;
        background: #FBA51B;
        margin:0;
        border-radius:0;
      }
    }
  }  
</style>
