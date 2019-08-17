<template>
	<view>
		 <!-- #ifdef APP-PLUS | H5-->
		  <uni-nav-bar left-icon="back" title="全部订单" @click-left="back" />
		 <!-- #endif -->
		 <wuc-tab :tab-list="tabList" :tabCur.sync="TabCur" @change="tabChange" selectClass="selectNav"></wuc-tab> 
		 <view class="ordersBox">
		 	<view class="od_item" v-for="(item,index) in 6" :key="index">
				<view class="uni-flex">
					<view class="od_pictrue">
						<image src="/static/2019sc_5.png"></image>
					</view>
					<view class="od_content">
						<view class="uni-inline-item odc_title">
							<text class="odct_left uni-ellipsis">小清新陶瓷梅花碗+木勺一套装</text>
							<text class="odct_right">待付款</text>
						</view>
						<view class="uni-inline-item odc_descript">
							<text class="odcd_left uni-ellipsis">白色碎花瓷+木勺</text>
							<text class="odcd_right">￥12.8</text>
						</view>
						<view class="odc_total uni-inline-item">
							<text class="odct_left">共一件商品</text>
							<text class="odct_right">合计&nbsp;:&nbsp;12.8￥</text>
						</view>	
					</view>
				</view>
				<view class="odc_button">
					<button class="mini-btn" type="default" size="mini" plain>确认付款</button>
				</view>
		 	</view>
		 </view>
	</view>
</template>

<script>
	import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
	import uniIcon from '@/components/uni-icon/uni-icon.vue'
	import WucTab from '@/components/wuc-tab/wuc-tab.vue';
	export default {
		data() {
			return {
				  tabList: [{ name: '全部订单' }, { name: '待付款' },{ name: '待发货' },{name:"待收货"},{name:"待评价"}],
				  TabCur:0
			};
		},
		methods:{
			tabChange(index) {
			       this.TabCur = index;
			   },
		},
		components:{
			uniIcon,
			uniNavBar,
			WucTab
		}
	}
</script>

<style lang="scss">

 .ordersBox{
	 padding:20rpx 20rpx;
	 .od_item{
	   height:220rpx;
	   padding-bottom:20rpx;
	   margin-bottom:20rpx;
	   border-bottom:1px solid rgba(0,0,0,0.2);
	   .od_pictrue{
		   width:160rpx;
		   height:160rpx;
		   margin-right:20rpx;
	   }
	   .odc_title{
		   justify-content:space-between;
		   .odct_left{
			   flex:1;
			   font-weight:700;
			   font-size:30rpx;
			   overflow:hidden;
		   }
		   .odct_right{
			   color:#F4A500;
		   }
	   }
	   .odc_descript{
		   justify-content:space-between;
		   overflow:hidden;
		   .odcd_right{
			 font-weight:700;  
		   }
	   }
	   .odc_total{
		   justify-content:space-between;
		   overflow:hidden;
	   }
	   .odc_button{
		   height:44rpx;
		   margin:10rpx 0;
		   text-align:end;
		   .mini-btn{
			   border-radius:40rpx;
			   width:150rpx;
			   height:44rpx;
         font-size:28rpx;
			   line-height:44rpx;
			   border:1px solid #F4A500;
			   color:#F4A500;
			   padding:0 16rpx;
			   text-align:center;
		   }
	   }
	 }
 }
 
	
 /deep/.selectNav{
  font-weight:700;
  font-size:30rpx;
  color:#FBA51B;
  transition:font-size 0.5s linear , font-weight 0.5s ease;
}

</style>
