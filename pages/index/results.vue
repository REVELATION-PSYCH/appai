<template>
  <view class="container">
    <text class="title-text">{{topText}}</text>
    <textarea class="text-area" placeholder="Type your message..."></textarea>
    <view v-for="(item, index) in messages" :key="index" class="text-item">
          <text>{{ item }}</text>
        </view>
  </view>
</template>

<script>
export default {
  name: "results",
  data() {
      return {
		  topText: '基本信息',
        messages: [
          "欢迎使用感染检测应用！",
          "请填写您的症状信息。",
          "请确保数据填写正确。",
          "填写完成后点击提交按钮。"
        ]
      };
    }
}
</script>

<style>
.container {
  display: flex;
  justify-content: flex-start;
  flex-direction: column;
  align-items: flex-start; 
  padding: 20px;
  height: 100vh;
  background-color: #f5f5f5;
  font-size: 20px;
}

.title-text {
  margin-bottom: 10px;
}

.text-area {
  height: 100px;
  width: 90%;
  color: black;
  background-color: floralwhite;
  border: 1px solid black;
  border-radius: 8px;
  padding: 10px;
  font-size: 16px;
  margin-bottom: 20px;
}
</style>
