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
  /* 新增：给 iframe 父容器加定位，配合 iframe 缩放 */
  position: relative;
  height: 60vh; /* 与 iframe 高度保持一致，避免缩放错位 */
}

.download-wrapper:hover {
  border-color: #999;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.download-iframe {
  width: 100%; 
  min-height: 480px; 
  max-height: 600px; 
  height: 60vh; 
  border: none;
  overflow: auto; 
  /* 关键修改：强制内容缩放适配子窗口 */
  transform-origin: top left; /* 从左上角开始缩放 */
  width: 120%; /* 先放大内容宽度（根据实际溢出情况调整，如110%/120%） */
  transform: scale(0.83); /* 再整体缩小（1/1.2≈0.83，与width成反比） */
  height: 120%; /* 高度同步放大，保证缩放后内容完整 */
}

/* 响应式调整：不同屏幕适配不同缩放比例 */
@media (max-width: 1024px) {
  .download-wrapper { height: 55vh; }
  .download-iframe {
    height: 55vh;
    width: 115%;
    transform: scale(0.87); /* 1/1.15≈0.87 */
  }
}

@media (max-width: 768px) {
  .download-container {
    padding: 15px;
    flex-direction: column;
  }
  .download-wrapper { height: 70vh; }
  .download-iframe {
    height: 70vh;
    width: 110%;
    transform: scale(0.91); /* 1/1.1≈0.91 */
    min-height: 500px;
  }
}

@media (max-width: 480px) {
  .download-wrapper { height: 65vh; }
  .download-iframe {
    height: 65vh;
    width: 105%;
    transform: scale(0.95); /* 1/1.05≈0.95 */
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
