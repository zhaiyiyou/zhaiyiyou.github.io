---
layout: default
title: 发个东西
keywords: 发个东西
description: 局域网聊天室。
permalink: /fgdx/
---

<style>
.external-site-container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  box-sizing: border-box; /* 确保padding不影响整体宽度 */
}

.external-iframe {
  width: 100%;
  min-height: 600px;
  height: calc(100vh - 180px); /* 动态计算高度（视口高度减去头部和底部空间） */
  border: 1px solid #eee; /* 增加边框区分内容区域 */
  border-radius: 4px; /* 圆角边框更美观 */
  box-shadow: 0 2px 4px rgba(0,0,0,0.05); /* 轻微阴影提升层次感 */
  transition: 全部 0.3s ease; /* 过渡动画 */
}

/* 加载状态样式 */
.iframe-loading {
  position: relative;
}

.iframe-loading::after {
  content: "加载中...";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: #666;
  background: rgba(255,255,255,0.8);
  padding: 8px 16px;
  border-radius: 4px;
  z-index: 1;
}

/* 响应式调整 */
@media (max-width: 768px) {
  .external-site-container {
    padding: 10px;
  }
  .external-iframe {
    height: calc(100vh - 140px); /* 移动端减少上下空间占用 */
    min-height: 400px;
  }
}

/* 错误提示样式 */
.iframe-error {
  color: #dc3545;
  text-align: center;
  padding: 20px;
  background: #f8d7da;
  border-radius: 4px;
}
</style>

<div class="external-site-container">
  <h3>发个东西 - 局域网聊天室</h3>
  <!-- 增加加载状态和错误处理 -->
  <div id="iframe-container" class="iframe-loading">
    <iframe id="external-frame" 
            class="external-iframe"
            src="https://fagedongxi.com" 
            title="fagedongxi.com" 
            frameborder="0" 
            scrolling="auto"
            onload="this.parentNode.classList.remove('iframe-loading')"
            onerror="handleIframeError()">
    </iframe>
  </div>
</div>

<script>
// 处理iframe加载错误
function handleIframeError() {
  const container = document.getElementById('iframe-container');
  container.innerHTML = '<div class="iframe-error">聊天室加载失败，请稍后重试</div>';
}

// 监听窗口大小变化，优化iframe高度
window.addEventListener('resize', () => {
  const iframe = document.getElementById('external-frame');
  if (iframe) {
    const container = document.querySelector('.external-site-container');
    const containerRect = container.getBoundingClientRect();
    // 根据容器宽度动态调整最小高度
    iframe.style.minHeight = containerRect.width < 768 ? '400px' : '600px';
  }
});
</script>
