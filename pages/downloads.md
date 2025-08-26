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
  width: 100%; /* 使用正常宽度比例 */
  min-height: 480px; /* 基础高度 */
  max-height: 600px; /* 最大高度限制 */
  height: 60vh; /* 相对视口高度 */
  border: none;
  overflow: auto; /* 必要时显示滚动条 */
}

/* 响应式调整 */
@media (max-width: 1024px) {
  .download-iframe {
    height: 55vh;
  }
}

@media (max-width: 768px) {
  .download-container {
    padding: 15px;
    flex-direction: column;
  }
  
  .download-iframe {
    height: 70vh;
    min-height: 500px;
  }
}

@media (max-width: 480px) {
  .download-iframe {
    height: 65vh;
    min-height: 450px;
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
