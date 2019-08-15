<template>
	<view>
    <uni-nav-bar left-icon="back" title="个人信息" @click-left="back" />
    <form @submit="formSubmit">
        <view class="uni-form-item uni-flex">
            <text class="title">账号</text>
            <view class="input_field ">
                <input type="text" v-model="ownerInfo.account" />
            </view>
        </view>
        <view class="uni-form-item uni-flex">
            <text class="title">昵称</text>
            <view class="input_field">
                <input type="text" v-model="ownerInfo.name" />
            </view>
        </view>
        <view class="uni-form-item uni-flex">
            <text class="title">会员等级</text>
            <view class="input_field">
                <input type="text" v-model="ownerInfo.level"  disabled/>
            </view>
        </view>
        <view class="uni-form-item">
          <button type="primary" formType="submit" class="submitBtn" >提交</button>
        </view>
    </form>
		
	</view>
</template>

<script>
  import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue'
  import uniIcon from '@/components/uni-icon/uni-icon.vue'
	export default {
		data() {
			return {
				ownerInfo:{
          account:123465,
          name:"李师师",
          level:"高级会员"
        }
			};
		},
    methods:{
      formSubmit(){ //提交表单
        console.log("点击提交表单");
      },
      back(){ //返回上一层
         console.log("返回上一层");
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
      width:160rpx;
      text-align:justify;
      text-align-last: justify;  
      font-size:36rpx;
    }
    .submitBtn{
      width: 100%;
      height:80rpx;
      line-height:80rpx;
      margin-top: 40rpx;
      background:#FBA51B;
      border-radius:40rpx;
      letter-spacing:10rpx;
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
  /deep/.uni-navbar--shadow{
    box-shadow: none;
  }
</style>
