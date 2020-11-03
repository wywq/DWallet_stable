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
      <view class="create-wallet-tips">
        密码不少于8位字符，建议混合大小写字母、数字、特殊符号
      </view>
      <!-- 重复密码 -->
      <input class="create-wallet-input" type="text" placeholder="重复密码" />
      <!-- 隐私条款 -->
      <view class="create-choose">
        <!-- 选中 -->
        <template v-if="isChosen">
          <image
            class="create-choose-icon"
            src="/static/images/choose_yes@2x.png"
            @tap="handleChoose"
          ></image>
        </template>
        <!-- 未选中 -->
        <template v-else>
          <image
            class="create-choose-icon"
            src="/static/images/choose_no@2x.png"
            @tap="handleChoose"
          ></image>
        </template>
        <view class="create-choose-tips">我已经仔细阅读并同意</view>
        <view class="create-choose-protocol">服务及隐私条款</view>
      </view>
      <!-- 创建 -->
      <view class="create-btn">创建钱包</view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      //隐私条款是否勾选
      isChosen: false,
    };
  },
  onLoad() {},
  methods: {
    // 切换选中
    handleChoose() {
      this.isChosen = !this.isChosen;
    },
  },
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
      border-bottom: 2rpx solid #eeeeee;
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
    .create-choose {
      @include flex(flex-start, center);
      margin-top: 20rpx;
      .create-choose-icon {
        margin-right: 16rpx;
        width: 32rpx;
        height: 32rpx;
      }
      .create-choose-tips {
        margin-right: 10rpx;
        font-size: 24rpx;
        font-family: PingFangSC-Regular, PingFang SC;
        font-weight: 400;
        color: #9b9b9b;
      }
      .create-choose-protocol {
        font-size: 24rpx;
        font-family: PingFangSC-Regular, PingFang SC;
        font-weight: 400;
        color: #2b80c2;
      }
    }
    .create-btn {
      @include button_theme_disabled();
      margin-top: 60rpx;
    }
  }
}
</style>
