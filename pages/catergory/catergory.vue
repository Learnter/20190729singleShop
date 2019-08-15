<template>
	<view class="content">
     <view class="searchBox uni-flex">
       <uni-icon type="scan" size="25"></uni-icon>
       <view class="uni-flex-item inputBox uni-flex">
         <uni-icon type="search" size="25"></uni-icon>
         <input type="text" class="uni-flex-item" value="" placeholder="请输入您想收搜商品的关键字" placeholder-class="inputHolder">
       </view>
       <uni-icon type="chat" size="25"></uni-icon>
     </view>
     <view class="cate_main uni-flex">
       <scroll-view scroll-y class="left-aside">
       	<view v-for="item in 20" :key="item.id" class="f-item b-b" :class="{active: item.id === currentId}" @click="tabtap(item)">
       		<!-- {{item.name}} -->提示栏
       	</view>
       </scroll-view>
       <scroll-view scroll-with-animation scroll-y class="right-aside" :scroll-top="tabScrollTop"> <!--@scroll="asideScroll" -->
       <view class="look_more uni-flex">
         <text>提示框</text>
         <view class="moreBtn">
           <text>查看更多</text>
           <uni-icon type="arrowright" size="18"></uni-icon>
         </view>
       </view>
       <view class="big_picture">
         <image src="../../static/2019sc_5.png" mode=""></image>
       </view>
       	<view v-for="item in 20" :key="item.id" class="s-list" :id="'main-'+item.id">
          <view class="item-picture">
            <image src="../../static/2019sc_5.png"></image>
          </view>
          <text>连衣裙</text>
       	</view>
       </scroll-view>
     </view>
	</view>
</template>

<script>
  import uniIcon from "@/components/uni-icon/uni-icon.vue";
		export default {
		data() {
			return {
				sizeCalcState: false,
				tabScrollTop: 0,
				currentId: 1,
				flist: [],
				slist: [],
				tlist: [],
			}
		},
		onLoad(){
			// this.loadData();
		},
		methods: {
			async loadData(){
				let list = await this.$api.json('cateList');
				list.forEach(item=>{
					if(!item.pid){
						this.flist.push(item);  //pid为父级id, 没有pid或者pid=0是一级分类
					}else if(!item.picture){
						this.slist.push(item); //没有图的是2级分类
					}else{
						this.tlist.push(item); //3级分类
					}
				}) 
			},
			//一级分类点击
			tabtap(item){
				if(!this.sizeCalcState){
					this.calcSize();
				}
				
				this.currentId = item.id;
				let index = this.slist.findIndex(sitem=>sitem.pid === item.id);
				this.tabScrollTop = this.slist[index].top;
			},
			//右侧栏滚动
			asideScroll(e){
				if(!this.sizeCalcState){
					this.calcSize();
				}
				let scrollTop = e.detail.scrollTop;
				let tabs = this.slist.filter(item=>item.top <= scrollTop).reverse();
				if(tabs.length > 0){
					this.currentId = tabs[0].pid;
				}
			},
			//计算右侧栏每个tab的高度等信息
			calcSize(){
				let h = 0;
				this.slist.forEach(item=>{
					let view = uni.createSelectorQuery().select("#main-" + item.id);
					view.fields({
						size: true
					}, data => {
						item.top = h;
						h += data.height;
						item.bottom = h;
					}).exec();
				})
				this.sizeCalcState = true;
			},
			navToList(sid, tid){
				uni.navigateTo({
					url: `/pages/product/list?fid=${this.currentId}&sid=${sid}&tid=${tid}`
				})
			}
		},
    components:{
      uniIcon
    }
	}
</script>

<style lang="scss">
  page,
  .content {
  	height: 100%;
  	background-color: #f8f8f8;
    position:relative;
  }
  
  .searchBox{
    height:60rpx;
    padding:20rpx;
    align-items:center;
    .inputBox{
      align-items:center;
      height:60rpx;
      padding: 0 10rpx;
      margin: 0 20rpx;
      background:#F3F3F3;
      border-radius:10rpx;
      .inputHolder{
        letter-spacing:2rpx;
        font-size:28rpx;
        padding-left:10rpx;
      }
    }
  }
  
  .cate_main{
    position:absolute;
    left:0;
    top:100rpx;
    width:100%;
    bottom:0;
    border-top:1px solid  rgba(132,132,132,0.5);
  }
  
  .left-aside {
		flex-shrink: 0;
		width: 200rpx;
		height: 100%;
		background-color: #F8F8F8;
	}
	.f-item {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100rpx;
		font-size: 32rpx;
		position: relative;
		&.active{
			color:#FFA922;
			background: #fff;
			&:before{
				content: '';
				position: absolute;
				left: 0;
				top: 50%;
				transform: translateY(-50%);
				height: 36upx;
				width: 8upx;
				background-color: #FFA922;
				border-radius: 0 4px 4px 0;
				opacity: .8;
			}
		}
	}

	.right-aside{
		flex: 1;
		overflow: hidden;
		padding-right: 20upx;
    background:#fff;
    .look_more{
      height:100rpx;
      align-items:center;
      justify-content:space-between;
      .moreBtn{
        color:#999999;
        font-size:28rpx;
      }
    }
    .big_picture{
      width:100%;
      height:140rpx;
      margin-bottom:10rpx;
      border-radius:10rpx;
      overflow:hidden;
    }
	}
  
  .s-list{
    display:inline-block;
    width:33%;
    padding-bottom:10rpx;
    text-align:center;
    .item-picture{
      width:140rpx;
      height:140rpx;
      margin: 0 auto;
    }
  }
  
  
  
	.t-list{
		display: flex;
		flex-wrap: wrap;
		width: 100%;
		background: #fff;
		padding-top: 12upx;
		&:after{
			content: '';
			flex: 99;
			height: 0;
		}
	}
	.t-item{
		flex-shrink: 0;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		width: 176upx;
		font-size: 26upx;
		color: #666;
		padding-bottom: 20upx;
		image{
			width: 140upx;
			height: 140upx;
		}
	}
</style>
