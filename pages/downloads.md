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

/* 等比缩小设置 */
.download-wrapper {
  position: relative;
  width: 100%;
  padding-top: 75%; /* 4:3 比例 (高度=宽度×0.75) */
  overflow: hidden;
  border-radius: 6px;
}

.download-iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 1px solid #ddd;
  transition: border-color 0.3s;
}

.download-iframe:hover {
  border-color: #999;
}

/* 响应式调整 */
@media (max-width: 768px) {
  .download-container {
    padding: 15px;
  }
  
  .download-wrapper {
    padding-top: 100%; /* 移动端使用1:1比例 */
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
              frameborder="0" 
              scrolling="auto">
      </iframe>
    </div>
  </div>

  <div class="download-section">
    <h3>信息课工具箱下载(密码1234)</h3>
    <div class="download-wrapper">
      <iframe src="https://wwpb.lanzouw.com/b00ya6vgod" 
              class="download-iframe"
              title="信息课工具箱下载" 
              frameborder="0" 
              scrolling="auto">
      </iframe>
    </div>
  </div>
</div>
