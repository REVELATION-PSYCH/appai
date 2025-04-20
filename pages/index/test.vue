<template>
  <view class="page">
    <view class="title">AI生理检测</view>

    <!-- Upload buttons -->
    <button @click="chooseVideo('album')" class="btn">从相册选择视频</button>
    <button @click="chooseVideo('camera')" class="btn">拍摄新视频</button>
    
    <!-- Video preview OR placeholder -->
    <view class="video-preview">
      <video v-if="videoPath" :src="videoPath" controls class="video-player" />
      <view v-else class="placeholder-text">请上传或拍摄视频</view>
    </view>
    
    <!-- Start detection button -->
    <button type="default" class="start-btn">开始检测</button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      videoPath: ''
    }
  },
  methods: {
    chooseVideo(source) {
      uni.chooseVideo({
        sourceType: source === 'camera' ? ['camera'] : ['album'],
        success: (res) => {
          this.videoPath = res.tempFilePath
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
  
  .btn {
    width: 100%;
   
	  background: #4c00ff;
	  color: #fff;
    border-radius: 8rpx;
    font-size: 28rpx;
    padding: 12rpx 0;
    margin-bottom: 20rpx;
  }
  
  .video-preview {
    width: 100%;
    height: 300rpx;
    background: #f5f5f5;
    border: 2rpx dashed #ccc;
    border-radius: 12rpx;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 30rpx;
  }
  
  .video-player {
    width: 100%;
    height: 100%;
    border-radius: 12rpx;
  }
  
  .placeholder-text {
    color: #999;
    font-size: 28rpx;
  }
  
  .start-btn {
    width: 100%;
    background-color: #28a745;
    color: white;
    border-radius: 8rpx;
    font-size: 30rpx;
    padding: 14rpx 0;
  }


</style>
