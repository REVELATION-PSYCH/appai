<template>
  <view class="page">
    <view class="title">生理检测报告</view>

    <view class="card">
      <text class="card-title">基本信息</text>
      <text>年龄: {{ info.age }}</text>
      <text>性别: {{ info.gender }}</text>
    </view>

    <view class="card">
      <text class="card-title">生理指标</text>
      <text>心率: {{ info.heartRate }}</text>
      <text>血氧: {{ info.oxygen }}</text>
      <text>血压: {{ info.bloodPressure }}</text>
      <text>呼吸率: {{ info.breathing }}</text>
      <text>血糖: {{ info.bloodSugar }}</text>
      <text>心率变异性: {{ info.hrv }}</text>
    </view>

    <view class="card">
      <text class="card-title">情绪指标</text>
      <text>情绪状态: {{ info.emotion }}</text>
      <text>紧张值: {{ info.stress }}</text>
      <text>放松值: {{ info.relax }}</text>
      <text>紧张级别: {{ info.stressLevel }}</text>
      <text>精神状态: {{ info.mental }}</text>
      <text>平静: {{ info.calm }}</text>
      <text>焦虑: {{ info.anxiety }}</text>
      <text>警觉: {{ info.alertness }}</text>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      info: {
        age: '',
        gender: '',
        heartRate: '',
        oxygen: '',
        bloodPressure: '',
        breathing: '',
        bloodSugar: '',
        hrv: '',
        emotion: '',
        stress: '',
        relax: '',
        stressLevel: '',
        mental: '',
        calm: '',
        anxiety: '',
        alertness: ''
      }
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
.card {
  background: #fff;
  border-radius: 20rpx;
  padding: 20rpx;
  margin-bottom: 20rpx;
  box-shadow: 0 4rpx 8rpx rgba(0, 0, 0, 0.1);
}
.card-title {
  font-size: 32rpx;
  font-weight: bold;
  margin-bottom: 10rpx;
}
.card text {
  display: block;
  margin-bottom: 10rpx;
}
</style>
