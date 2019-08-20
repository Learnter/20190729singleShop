<template>
	<view class="content">
    
    <search-bar></search-bar> 
      
    <wuc-tab :tab-list="tabList" :tabCur.sync="TabCur" @change="tabChange" selectClass="selectNav"></wuc-tab>  
    
    
    <swiper :current="TabCur" class="swiper-box" duration="500" @change="changeTab">
    	<swiper-item class="tab-content" v-for="(tabItem,tabIndex) in 10" :key="tabIndex">
    		<scroll-view  class="list-scroll-content" scroll-y	@scrolltolower="loadData"> <!--loadData为加载数据的方法 -->
           <!-- <first-page></first-page> -->
           <ornament></ornament>
    		</scroll-view>
    	</swiper-item>
    </swiper>
	</view>
</template>

<script>
  import uniIcon from "@/components/uni-icon/uni-icon.vue";
  import WucTab from '@/components/wuc-tab/wuc-tab.vue';
  import uniSwiperDot from "@/components/uni-swiper-dot/uni-swiper-dot.vue";
  import searchBar from "@/components/search-bar.vue";
  import firstPage from "@/pages/home/firstPage/firstPage.vue";
  import ornament from "@/pages/home/ornament/ornament.vue"
	export default {
		data() {
			return {
				 TabCur:0,
         tabList: [{ name: '首页' }, { name: '饰品' },{ name: '百货' }, { name: '女装' },{ name: '美妆' }, { name: '生鲜' },{ name: '食品' }, { name: '订阅' },{ name: '精选' }, { name: '订阅' },{ name: '精选' }, { name: '订阅' }],
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
      changeTab(e){
       console.log(e);
       this.TabCur = e.detail.current;
      }
    },
    components: {uniIcon,WucTab,uniSwiperDot,searchBar,firstPage,ornament}
	}
</script>

<style lang="scss" scoped>
  page {
  	display: flex;
  	flex-direction: column;
  	box-sizing: border-box;
  	background-color: #fff;
    height:100%;
  }
  .content{
    width:100%;
    height:100%;
  }
  
  .content>.swiper-box{
    width:100%;
    height: calc(100% - 180rpx);
    margin:10rpx 0 0;
    .tab-content{
      overflow-y:scroll;
    }
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
    transition:font-size 0.5s ease;
  }
  
  /deep/.wuc-tab-item{
     height:80rpx;
     line-height:80rpx;
     
  }
  /deep/.wuc-tab-item.cur{
    border:none;
    position:relative;
    &::after{
      position: absolute;
      right:23%;
      top:85%;
      content:"";
      width:50%;
      height:8rpx;
      background:#FBA51B;
      border-radius:50% 50% 0 0;
    }
  }
  
  
</style>
