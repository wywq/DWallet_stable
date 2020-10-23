<template>
  <view class="create">
    <!-- 顶部提示 -->
    <view class="create-tips">
      <view class="create-tips-text"
        >· 密码用于保护私钥和交易授权，强度非常重要</view
      >
      <view class="create-tips-text"
        >· lbtoken 不存储密码，也无法帮您找回，请务必牢记</view
      >
    </view>
    <!-- 创建钱包 -->
    <view class="create-wallet">
      <!-- 钱包名称 -->
      <input class="create-wallet-input" type="text" placeholder="钱包名称" />
      <!-- 密码 -->
      <input class="create-wallet-input" type="text" placeholder="密码" />
      <!-- 密码提示 -->
      <div class="create-wallet-tips">
        密码不少于8位字符，建议混合大小写字母、数字、特殊符号
      </div>
      <!-- 重复密码 -->
      <input class="create-wallet-input" type="text" placeholder="重复密码" />
      <!-- 隐私条款 -->
      <div class="create-choose">
        image
      </div>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {};
  },
  onLoad() {},
  methods: {},
};
</script>

<style lang="scss" scoped>
.create {
  width: 100%;
  height: 100vh;
  .create-tips {
    @include flex(center, flex-start);
    flex-direction: column;
    padding: 0 30rpx;
    box-sizing: border-box;
    width: 100%;
    height: 122rpx;
    background: #e3eaf7;
    .create-tips-text {
      font-size: 24rpx;
      font-family: PingFangSC-Regular, PingFang SC;
      font-weight: 400;
      color: #2b80c2;
    }
    .create-tips-text:last-child {
      margin-top: 10rpx;
    }
  }
  .create-wallet {
    padding: 4rpx 30rpx 0;
    box-sizing: border-box;
    width: 100%;
    .create-wallet-input {
      margin-top: 42rpx;
      padding-bottom: 20rpx;
      width: 100%;
      box-sizing: border-box;
      border-bottom: 1rpx solid #eeeeee;
      font-family: PingFangSC-Regular, PingFang SC;
      font-weight: 400;
      color: #222222;
    }
    .create-wallet-tips {
      margin-top: 10rpx;
      width: 100%;
      font-size: 24rpx;
      font-family: PingFangSC-Regular, PingFang SC;
      font-weight: 400;
      color: #eb2650;
      text-align: right;
      line-height: 34rpx;
    }
  }
}
</style>
