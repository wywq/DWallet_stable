<template>
  <uni-drawer
    ref="drawer"
    mode="right"
    :width="240"
    @change="onStatusChange($event)"
  >
    <view class="drawer">
      <!-- 抽屉封面 -->
      <view class="drawer-cover">
        <image
          class="drawer-cover-avatar"
          src="/static/images/logo_lb@2x.png"
        ></image>
        <view class="drawer-cover-title">Wallet</view>
      </view>
      <!-- 抽屉列表 -->
      <view class="drawer-list">
        <block v-for="(w, i) in walletList" :key="i">
          <view class="drawer-list-item">
            <image class="item-avatar" :src="w.avatar"></image>
            <view class="item-name">{{ w.name }}</view>
          </view>
        </block>
      </view>
      <!-- 创建钱包 -->
      <view class="drawer-confirm">创建钱包</view>
    </view>
  </uni-drawer>
</template>

<script>
import uniDrawer from "@/components/UniUI/uni-drawer/uni-drawer.vue";
export default {
  components: {
    uniDrawer,
  },
  data() {
    return {
      walletList: [
        { avatar: "/static/images/head_50@2x.png", name: "ZXX" },
        { avatar: "/static/images/head_50@2x.png", name: "DKSANGKDSI" },
        { avatar: "/static/images/head_50@2x.png", name: "DSAKFJIA" },
        { avatar: "/static/images/head_50@2x.png", name: "ZXX" },
        { avatar: "/static/images/head_50@2x.png", name: "DKSANGKDSI" },
        { avatar: "/static/images/head_50@2x.png", name: "DSAKFJIA" },
        { avatar: "/static/images/head_50@2x.png", name: "ZXX" },
        { avatar: "/static/images/head_50@2x.png", name: "DKSANGKDSI" },
        { avatar: "/static/images/head_50@2x.png", name: "DSAKFJIA" },
        { avatar: "/static/images/head_50@2x.png", name: "ZXX" },
        { avatar: "/static/images/head_50@2x.png", name: "DKSANGKDSI" },
        { avatar: "/static/images/head_50@2x.png", name: "DSAKFJIA" },
        { avatar: "/static/images/head_50@2x.png", name: "ZXX" },
        { avatar: "/static/images/head_50@2x.png", name: "DKSANGKDSI" },
        { avatar: "/static/images/head_50@2x.png", name: "DSAKFJIA" },
        { avatar: "/static/images/head_50@2x.png", name: "ZXX" },
        { avatar: "/static/images/head_50@2x.png", name: "DKSANGKDSI" },
        { avatar: "/static/images/head_50@2x.png", name: "DSAKFJIA" },
      ],
    };
  },
  onLoad() {},
  methods: {
    //开启抽屉
    openDrawer() {
      this.$refs.drawer.open();
    },
    //开启抽屉
    closeDrawer() {
      this.$refs.drawer.close();
    },
    //监测抽屉开启关闭
    onStatusChange(e) {
      if (e) {
        uni.hideTabBar();
      } else {
        uni.showTabBar();
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.drawer {
  @include flex(flex-start, center);
  flex-direction: column;
  padding: 80rpx 30rpx;
  box-sizing: border-box;
  width: 100%;
  height: 100vh;
}
.drawer-cover {
  @include flex(flex-start, center);
  width: 100%;
  height: 164rpx;
  background: linear-gradient(225deg, #2d80c2 0%, #203975 100%);
  border-radius: 10rpx;
}
.drawer-cover-avatar {
  margin: 0 30rpx 0 40rpx;
  width: 80rpx;
  height: 80rpx;
  border-radius: 50%;
}
.drawer-cover-title {
  font-size: 28rpx;
  font-family: PingFangSC-Regular, PingFang SC;
  font-weight: 400;
  color: #ffffff;
}
.drawer-list {
  @include flex(flex-start, center);
  flex-direction: column;
  flex-grow: 1;
  margin: 60rpx 0;
  width: 100%;
  height: 50%;
  overflow-y: scroll;
}
.drawer-list-item {
  @include flex(flex-start, center);
  padding: 30rpx 0;
  box-sizing: border-box;
  width: 100%;
  border-bottom: 1rpx solid #eee;
}
.drawer-list-item:last-child {
  border-bottom: none;
}
.item-avatar {
  margin-right: 40rpx;
  width: 100rpx;
  height: 100rpx;
  border-radius: 50%;
}
.item-name {
  font-size: 28rpx;
  font-family: PingFangSC-Regular, PingFang SC;
  font-weight: 400;
  color: #333333;
}
.drawer-confirm {
  width: 100%;
  height: 88rpx;
  line-height: 88rpx;
  background: #2b80c2;
  border-radius: 6rpx;
  text-align: center;
  font-size: 32rpx;
  font-family: PingFangSC-Regular, PingFang SC;
  font-weight: 400;
  color: #ffffff;
}
</style>
