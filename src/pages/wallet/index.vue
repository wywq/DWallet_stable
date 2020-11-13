<template>
  <view class="wallet">
    <!-- 钱包信息 -->
    <view class="wallet-msg">
      <!-- 钱包币种 -->
      <view class="wallet-msg-title">
        <view class="wallet-msg-title-fake"></view>
        <view class="wallet-msg-title-center">
          <view class="wallet-msg-title-center-fake"></view>
          <view class="wallet-msg-title-center-words">USDT</view>
          <image class="wallet-msg-title-center-icon" :src="arrow"></image>
        </view>
        <image
          class="wallet-msg-title-icon"
          src="/static/images/more_w@2x.png"
          @tap="handleSelectWallet"
        ></image>
      </view>
      <!-- 钱包头像 -->
      <image
        class="wallet-msg-avatar"
        src="/static/images/head_50@2x.png"
      ></image>
      <!-- 钱包名称 -->
      <view class="wallet-msg-name">ZXC</view>
      <!-- 钱包地址 -->
      <view class="wallet-msg-address">
        <view class="wallet-msg-address-value"
          >021543513211355F4GFG1FD1G2135</view
        >
        <image
          class="wallet-msg-address-icon"
          src="/static/images/erweima_mini@2x.png"
        >
        </image>
      </view>
      <!-- 添加新资产 -->
      <view class="wallet-msg-new">
        <image class="wallet-msg-new-icon" src="/static/images/add_20@2x.png">
        </image>
      </view>
    </view>
    <!-- 钱包信息 -->
    <!-- <view class="wallet"> </view> -->
    <select-wallet ref="walletDrawer"></select-wallet>
  </view>
</template>

<script>
import SelectWallet from "@/components/Custom/Drawer/SelectWallet/index.vue";
export default {
  components: { SelectWallet },
  data() {
    return {
      //显示选择币种
      showSelectCoin: false,
    };
  },
  computed: {
    //标题箭头
    arrow() {
      if (this.showSelectCoin) {
        return "/static/images/t_icon.png";
      } else {
        return "/static/images/b_icon.png";
      }
    },
  },
  onLoad() {},
  methods: {
    //选择钱包
    handleSelectWallet() {
      this.$refs.walletDrawer.openDrawer();
    },
  },
};
</script>

<style lang="scss" scoped>
.wallet {
  width: 100%;
  height: 100vh;
}
.wallet-msg {
  @include flex(flex-start, center);
  flex-direction: column;
  padding-right: 30rpx;
  padding-left: 30rpx;
  box-sizing: border-box;
  width: 100%;
  height: 450rpx;
  background: linear-gradient(225deg, #2d80c2 0%, #203975 100%);
}
/*  #ifdef  APP-PLUS  */
.wallet-msg {
  padding-top: var(--status-bar-height);
}
/*  #endif  */
/*  #ifdef  H5  */
.wallet-msg {
  padding-top: 25rpx;
}
/*  #endif  */
.wallet-msg-title {
  @include flex(space-between, center);
  margin-top: 30rpx;
  box-sizing: border-box;
  width: 100%;
}
.wallet-msg-title-fake,
.wallet-msg-title-icon {
  width: 32rpx;
  height: 26rpx;
}
.wallet-msg-title-center {
  @include flex(center, center);
}
.wallet-msg-title-center-fake,
.wallet-msg-title-center-icon {
  width: 16rpx;
  height: 16rpx;
}
.wallet-msg-title-center-fake {
  margin-right: 6rpx;
}
.wallet-msg-title-center-icon {
  margin-left: 6rpx;
}
.wallet-msg-title-center-words {
  font-size: 32rpx;
  font-family: PingFangSC-Medium, PingFang SC;
  font-weight: 500;
  color: #ffffff;
}
.wallet-msg-avatar {
  margin-top: 50rpx;
  width: 100rpx;
  height: 100rpx;
  border-radius: 50%;
  border: 2rpx solid #ffffff;
}
.wallet-msg-name {
  margin-top: 14rpx;
  font-size: 28rpx;
  font-family: PingFangSC-Regular, PingFang SC;
  font-weight: 400;
  color: #ffffff;
}
.wallet-msg-address {
  @include flex(center, center);
  margin-top: 20rpx;
}
.wallet-msg-address-value {
  font-size: 24rpx;
  font-family: PingFangSC-Regular, PingFang SC;
  font-weight: 400;
  color: #ffffff;
}
.wallet-msg-address-icon {
  margin-left: 14rpx;
  width: 24rpx;
  height: 24rpx;
}
.wallet-msg-new {
  @include flex(flex-end, center);
  margin-top: 12rpx;
  width: 100%;
}
.wallet-msg-new-icon {
  width: 40rpx;
  height: 40rpx;
}
</style>
