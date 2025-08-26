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
  display: flex; /* 启用Flex布局 */
  gap: 20px; /* 两个区块之间的间距 */
  flex-wrap: wrap; /* 响应式换行 */
}

.download-section {
  flex: 1; /* 平分容器宽度 */
  min-width: 300px; /* 最小宽度，避免过窄 */
  margin-bottom: 50px;
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

.download-iframe {
  width: 100%;
  height: 80vh;
  min-height: 600px;
  border: 1px solid #ddd;
  border-radius: 6px;
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
  
  .download-iframe {
    height: 70vh;
    min-height: 500px;
  }
}
</style>

<div class="download-container">
  <div class="download-section">
    <h3>不虚系列下载(密码1234)</h3>
    <iframe src="https://wwpb.lanzouw.com/b00ya22x0d" 
            class="download-iframe"
            title="不虚系列下载" 
            frameborder="0" 
            scrolling="auto">
    </iframe>
  </div>

  <div class="download-section">
    <h3>信息课工具箱下载(密码1234)</h3>
    <iframe src="https://wwpb.lanzouw.com/b00ya6vgod" 
            class="download-iframe"
            title="信息课工具箱下载" 
            frameborder="0" 
            scrolling="auto">
    </iframe>
  </div>
</div>
