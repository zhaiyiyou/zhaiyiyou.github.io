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
  flex-direction: column; /* 垂直排列，确保一行一个子窗口 */
  gap: 30px; /* 子窗口之间的垂直间距 */
}

.download-section {
  width: 90%; /* 宽度占网页宽度的90% */
  margin: 0 auto; /* 水平居中 */
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

.download-wrapper {
  width: 100%;
  border-radius: 6px;
  overflow: hidden;
  border: 1px solid #ddd;
  transition: all 0.3s ease;
}

.download-wrapper:hover {
  border-color: #999;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.download-iframe {
  width: 100%;
  /* 高度改为原来的75% */
  min-height: 360px; /* 原480px × 0.75 */
  max-height: 450px; /* 原600px × 0.75 */
  height: 45vh; /* 原60vh × 0.75 */
  border: none;
  overflow: auto;
}

/* 响应式调整 */
@media (max-width: 1024px) {
  .download-iframe {
    height: 41.25vh; /* 原55vh × 0.75 */
  }
}

@media (max-width: 768px) {
  .download-container {
    padding: 15px;
  }
  
  .download-section {
    width: 95%; /* 移动端宽度稍宽 */
  }
  
  .download-iframe {
    height: 52.5vh; /* 原70vh × 0.75 */
    min-height: 375px; /* 原500px × 0.75 */
  }
}

@media (max-width: 480px) {
  .download-iframe {
    height: 48.75vh; /* 原65vh × 0.75 */
    min-height: 338px; /* 原450px × 0.75，四舍五入 */
  }
}
</style>

<div class="download-container">
  <div class="download-section">
    <h3>不虚系列下载(密码1234)</h3>
    <div class="download-wrapper">
      <iframe src="https://wwpb.lanzouw.com/b00ya22x0d" 
              class="download-iframe"
              title="不虚系列下载" 
              frameborder="0">
      </iframe>
    </div>
  </div>

  <div class="download-section">
    <h3>信息课工具箱下载(密码1234)</h3>
    <div class="download-wrapper">
      <iframe src="https://wwpb.lanzouw.com/b00ya6vgod" 
              class="download-iframe"
              title="信息课工具箱下载" 
              frameborder="0">
      </iframe>
    </div>
  </div>
</div>
