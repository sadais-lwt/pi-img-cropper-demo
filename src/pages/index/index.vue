<template>
  <view class="content">
    <view>
      <text class="title">{{ title }}</text>
    </view>
    <view class="scroll">
      <pi-img-cropper :src="src" />
    </view>
  </view>
</template>

<script>
import PiImgCropper from '@/components/pi-img-cropper'
export default {
  components: {
    PiImgCropper
  },
  data() {
    return {
      title: 'Hello',
      // src: 'https://img1.baidu.com/it/u=395380977,272417941&fm=26&fmt=auto'
      src: 'https://img2.baidu.com/it/u=379288490,3520188610&fm=26&fmt=auto'
    }
  },
  onLoad() {},
  methods: {}
}
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: calc(100vh - var(--window-bottom));
}

.scroll {
  width: 100%;
  flex: 1;
}
.logo {
  height: 200rpx;
  width: 200rpx;
  margin: 200rpx auto 50rpx auto;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
