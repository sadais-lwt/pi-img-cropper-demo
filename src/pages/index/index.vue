<template>
  <view class="content">
    <view>
      <text class="title">{{ title }}</text>
    </view>
    <view class="scroll">
      <pi-img-cropper
        :src="src"
        @cropped="handleCropped"
        @afterDraw="handleAfterDraw"
      />
      <image
        :style="[imgSize]"
        :src="cropImgPath"
        style="position: fixed; top: 0; left: 0"
      />
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
      src: 'https://img2.baidu.com/it/u=379288490,3520188610&fm=26&fmt=auto',
      cropImgPath: '',
      size: { width: 0, height: 0 }
    }
  },
  computed: {
    imgSize() {
      return {
        width: `${this.size.width}px`,
        height: `${this.size.height}px`
      }
    }
  },
  onLoad() {},
  methods: {
    handleCropped(result) {
      this.cropImgPath = result.img
      this.size = { width: result.width, height: result.height }
    },
    handleAfterDraw(draw) {
      draw.ctx.setFontSize(50)
      draw.ctx.setFillStyle('#ff0000')
      draw.ctx.fillText('PiUI', draw.width * 0.25, draw.height * 0.5)
    }
  }
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
