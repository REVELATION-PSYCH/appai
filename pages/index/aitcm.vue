<template>
  <view class="page">
    <view class="title">AI中医检测</view>

<view class="image-box">
  <view class="img-item" v-for="(item, index) in images" :key="index">
    <!-- Placeholder if no image -->
    <view v-if="!item.url" class="placeholder-text">
      {{ item.label }}
    </view>

    <!-- Actual image if uploaded -->
    <image :src="item.url" mode="aspectFit" v-if="item.url" class="preview-img" />

    <!-- Upload button -->
    <button @click="chooseImage(index)">
      选择{{ item.label }}
    </button>
  </view>
</view>


    <radio-group @change="onSourceChange" class="source-options">
      <label>
        <radio :checked="source === 'album'" value="album" /> 从相册选择
      </label>
      <label>
        <radio :checked="source === 'camera'" value="camera" /> 使用相机拍摄
      </label>
    </radio-group>

    <button type="default" class="start-btn">开始检测</button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      source: 'album',
      images: [
        { url: '', label: '选择|拍面照' },
        { url: '', label: '选择|拍舌上照' },
        { url: '', label: '选择|拍舌下照' },
      ]
    }
  },
  methods: {
    onSourceChange(e) {
      this.source = e.detail.value
    },
    chooseImage(index) {
      uni.chooseImage({
        count: 1,
        sourceType: this.source === 'camera' ? ['camera'] : ['album'],
        success: (res) => {
          this.images[index].url = res.tempFilePaths[0]
        }
      })
    }
  }
}
</script>

<style scoped>
.page {
  padding: 20rpx;
}
.title {
  font-size: 40rpx;
  font-weight: bold;
  margin-bottom: 30rpx;
}
.image-box {
  display: flex;
  justify-content: space-between;
  margin-bottom: 30rpx;
}
.img-item {
  width: 30%;
  text-align: center;
}
.img-item image {
  width: 100%;
  height: 200rpx;
  background: #eee;
  margin-bottom: 10rpx;
}
.source-options {
  display: flex;
  justify-content: space-around;
  margin: 20rpx 0;
}
.start-btn {
  width: 100%;
  background-color: #ccc;
}


	.upload-placeholder {
	  width: 100%;
	  height: 200rpx;
	  background: #f5f5f5;
	  border: 2rpx dashed #ccc;
	  display: flex;
	  align-items: center;
	  justify-content: center;
	  border-radius: 12rpx;
	  margin-bottom: 20rpx;
	}
	

.upload-placeholder {
  width: 100%;
  height: 200rpx;
  background: #f5f5f5;
  border: 2rpx dashed #ccc;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 12rpx;
  margin-bottom: 20rpx;
}




.image-box {
  padding: 20rpx;
}

.img-item {
  margin-bottom: 30rpx;
}

.placeholder-text {
  width: 100%;
  height: 400rpx;
  background: #f5f5f5;
  border: 2rpx dashed #ccc;
  border-radius: 12rpx;
  color: #999;
  font-size: 28rpx;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 10rpx;
}

.preview-img {
  width: 100%;
  height: 200rpx;
  border-radius: 12rpx;
  object-fit: contain;
  margin-bottom: 10rpx;
}

button {
  width: 100%;
 
  background: #4c00ff;
  color: #fff;
  border-radius: 8rpx;
  font-size: 24rpx;
  padding: 12rpx 0;
}

</style>
