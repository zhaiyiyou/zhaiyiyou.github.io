layout: default
title: 发个东西
keywords: 发个东西
description: 局域网聊天室。
permalink: /fgdx/
---

<style>
/* 1. 外层容器：控制圆角、过渡背景、内边距缓冲 */
.external-site-container {
  width: 100%;
  max-width: 1200px; 
  margin: 0 auto; 
  padding: 30px; /* 增加内边距，让白色网站与窗口有呼吸感 */
  /* 关键：外层容器设置圆角（避免 iframe 圆角溢出）+ 白色背景（与网站底色融合） */
  border-radius: 12px; /* 圆角大小，可根据需求调整（如8px/16px） */
  background-color: #ffffff; /* 与网站白色背景一致，消除割裂感 */
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05); /* 可选：加轻微阴影，增强层次感 */
}

/* 2. 过渡容器：解决 iframe 黑色背景与白色的过渡 */
.iframe-wrapper {
  width: 100%;
  height: 80vh;
  min-height: 600px;
  border-radius: 8px; /* 内层圆角，比外层小1-2px更协调 */
  /* 关键：渐变过渡层（白色→浅灰→透明），覆盖 iframe 黑色边缘 */
  background: linear-gradient(to bottom, rgba(255,255,255,0.8) 0%, rgba(255,255,255,0.2) 10%, transparent 20%);
  overflow: hidden; /* 确保 iframe 不会超出圆角范围 */
}

/* 3. iframe 样式：保持自适应，移除多余边框 */
.external-iframe {
  width: 100%;
  height: 100%; /* 继承外层过渡容器高度，避免尺寸错位 */
  border: none; /* 彻底移除边框（替代 frameborder="0"） */
  scrolling: auto;
}

/* 4. 标题样式：与窗口对齐，增强整体感 */
.external-site-container h3 {
  margin: 0 0 15px 0; /* 与 iframe 保持间距 */
  color: #333333; /* 深色标题，避免与白色背景冲突 */
  font-size: 18px;
}
</style>

<div class="external-site-container">
  <h3>发个东西 - 局域网聊天室</h3>
  <!-- 新增过渡容器：包裹 iframe 实现背景过渡和圆角 -->
  <div class="iframe-wrapper">
    <iframe src="https://fagedongxi.com" 
            class="external-iframe"
            title="fagedongxi.com" 
            scrolling="auto">
    </iframe>
  </div>
</div>
