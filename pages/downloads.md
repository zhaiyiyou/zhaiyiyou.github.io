---
layout: default
title: 下载
keywords: 下载, 不虚系列, 信息课工具箱
description: 资源下载页面
permalink: /downloads/
---

<style>
.download-container {
  width: 100%;
  max-width: 1400px;
  margin: 0 auto;
  padding: 30px;
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.download-section {
  flex: 1;
  min-width: 300px;
  margin-bottom: 30px;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.05);
}

.download-section h3 {
  margin-top: 0;
  margin-bottom: 20px;
  font-size: 1.5rem;
  color: #333;
  padding-bottom: 10px;
  border-bottom: 1px solid #eee;
}

/* 缩放容器设置 */
.download-wrapper {
  width: 100%;
  overflow: hidden;
  border-radius: 6px;
  /* 为缩放留出空间 */
  padding: 10px;
  box-sizing: border-box;
}

.scaled-iframe-container {
  width: 100%;
  /* 控制缩放后的显示区域 */
  overflow: hidden;
  border: 1px solid #ddd;
  border-radius: 6px;
}

.download-iframe {
  width: 140%; /* 原始宽度比显示区域宽 */
  height: 140%; /* 原始高度比显示区域高 */
  border: none;
  /* 缩小比例（70%），保持内容完整 */
  transform: scale(0.7);
  transform-origin: top left; /* 从左上角开始缩放 */
  transition: all 0.3s ease;
}

.scaled-iframe-container:hover {
  border-color: #999;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

/* 响应式调整缩放比例 */
@media (max-width: 1024px) {
  .download-iframe {
    width: 130%;
    height: 130%;
    transform: scale(0.77);
  }
}

@media (max-width: 768px) {
  .download-container {
    padding: 15px;
    flex-direction: column;
  }
  
  .download-iframe {
    width: 120%;
    height: 120%;
    transform: scale(0.83);
  }
}

@media (max-width: 480px) {
  .download-iframe {
    width: 110%;
    height: 110%;
    transform: scale(0.91);
  }
}
</style>

<div class="download-container">
  <div class="download-section">
    <h3>不虚系列下载(密码1234)</h3>
    <div class="download-wrapper">
      <div class="scaled-iframe-container">
        <iframe src="https://wwpb.lanzouw.com/b00ya22x0d" 
                class="download-iframe"
                title="不虚系列下载" 
                frameborder="0" 
                scrolling="no"> <!-- 禁用滚动，内容已缩放完整显示 -->
        </iframe>
      </div>
    </div>
  </div>

  <div class="download-section">
    <h3>信息课工具箱下载(密码1234)</h3>
    <div class="download-wrapper">
      <div class="scaled-iframe-container">
        <iframe src="https://wwpb.lanzouw.com/b00ya6vgod" 
                class="download-iframe"
                title="信息课工具箱下载" 
                frameborder="0" 
                scrolling="no"> <!-- 禁用滚动，内容已缩放完整显示 -->
        </iframe>
      </div>
    </div>
  </div>
</div>
