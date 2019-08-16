<template>
	<view>
     <!-- #ifdef APP-PLUS | H5-->
      <uni-nav-bar left-icon="back" title="添加地址" @click-left="back" />
    <!-- #endif -->
		<form @submit="formSubmit">
		    <view class="uni-form-item uni-flex">
		        <text class="title">收货人</text>
		        <view class="input_field ">
		            <input type="text" v-model="addressInfo.name" placeholder="收货人姓名" placeholder-class="holderStyle"/>
		        </view>
		    </view>
		    <view class="uni-form-item uni-flex">
		        <text class="title">联系方式</text>
		        <view class="input_field">
		            <input type="text" v-model="addressInfo.tel"  placeholder="收货人电话"  placeholder-class="holderStyle"/>
		        </view>
		    </view>
		    <view class="uni-form-item uni-flex">
		        <text class="title">省/市/区</text>
		        <view class="input_field">
		            <input type="text" v-model="addressInfo.address" placeholder="省-市-区" placeholder-class="holderStyle"/>
		        </view>
		    </view>
        <view class=" editAddress uni-flex">
           <text class="title">详细地址</text>
           <view class="textarea" >
                <textarea auto-height style="width:100%;font-size:24rpx" v-model="addressInfo.detailAddress" placeholder="详细地址...."/>
            </view>
        </view>
        <view class="uni-flex default-row">
          	<text class="title">设为默认</text>
          	<switch :checked="addressInfo.checked"  color="#fa436a" @change="switchChange" />
        </view>
		    <!-- <view class="formBtn"> -->
		     <button type="primary" formType="submit" class="submitBtn" >保存</button>
		    <!-- </view> -->
		</form>
	</view>
</template>

<script>
  import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
  import uniIcon from '@/components/uni-icon/uni-icon.vue'
	export default {
    name:"insertAddress",
		data() {
			return {
				addressInfo:{
          name:"",
          tel:"",
          address:"",
          detailAddress:"",
          checked:false
        }
			};
		},
    methods:{
      formSubmit(){
        console.log(this.addressInfo);
      },
      switchChange(e){ //点击默认地址
        this.addressInfo.checked = e.target.value;
      }
    },
    components:{
      uniNavBar,
      uniIcon
          }
	}
</script>

<style lang="scss">
  .uni-form-item{
    box-sizing:border-box;
    padding: 20rpx 20rpx 0;
    height:100rpx;
    .title{
      width:140rpx;
      line-height:100rpx;
      text-align:justify;
      text-align-last: justify;  
      font-size:32rpx;
      flex-shrink:0;
    }
  }
  
  .editAddress{
    padding:0 20rpx;
    margin-top:40rpx;
    box-sizing:border-box;
    .title{
      width:140rpx;
      padding:10rpx 24rpx;
      text-align:justify;
      text-align-last: justify;  
      font-size:32rpx;
      flex-shrink:0;
    }
    .textarea{
      flex:1;
      border:1px solid rgba(75,75,75,0.2);
      height:150rpx;
      padding:10rpx;
      overflow:hidden; 
      font-size:28rpx;
    }
  }
  
  
  .input_field{
    flex:1;
    border-bottom:1px solid rgba(0,0,0,0.2);
    letter-spacing:4rpx;
    padding-left:16rpx;
    display:flex;
    flex-direction:column;
    justify-content:flex-end;
  }
  
  .default-row{
    padding:20rpx 20rpx;
    justify-content: space-between;
		.title{
		  width:140rpx;
		  padding:10rpx 24rpx;
		  text-align:justify;
		  text-align-last: justify;  
		  font-size:32rpx;
		  flex-shrink:0;
		}
		switch{
			transform: translateX(16rpx) scale(.7);
		}
	}
  
  .submitBtn{
    margin:20rpx 20rpx;
    height:80rpx;
    line-height:80rpx;
    margin-top: 40rpx;
    background:#FBA51B;
    border-radius:40rpx;
    letter-spacing:10rpx;
  }
  
  .holderStyle{
    font-size:24rpx ;
  }
  
  /deep/.uni-navbar--shadow{
    box-shadow: none;
  }
</style>
