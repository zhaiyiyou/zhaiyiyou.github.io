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
}

.download-section {
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

.update-btn {
  margin-top: 15px;
  padding: 8px 16px;
  background-color: #4285f4;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
  transition: background-color 0.3s;
}

.update-btn:hover {
  background-color: #3367d6;
}

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
    <iframe id="frame1" src="https://wwpb.lanzouw.com/b00ya22x0d" 
            class="download-iframe"
            title="不虚系列下载" 
            frameborder="0" 
            scrolling="auto">
    </iframe>
    <button class="update-btn" onclick="updateFrame('frame1', 'https://wwpb.lanzouw.com/b00ya22x0d')">更新子窗口内容</button>
  </div>

  <div class="download-section">
    <h3>信息课工具箱下载(密码1234)</h3>
    <iframe id="frame2" src="https://wwpb.lanzouw.com/b00ya6vgod" 
            class="download-iframe"
            title="信息课工具箱下载" 
            frameborder="0" 
            scrolling="auto">
    </iframe>
    <button class="update-btn" onclick="updateFrame('frame2', 'https://wwpb.lanzouw.com/b00ya6vgod')">更新子窗口内容</button>
  </div>
</div>

<script>
// 同源情况下更新子窗口的函数
function updateFrame(frameId, newUrl) {
  const iframe = document.getElementById(frameId);
  
  if (iframe) {
    try {
      // 尝试获取子窗口文档（仅同源可用）
      const childDoc = iframe.contentDocument || iframe.contentWindow.document;
      
      // 1. 直接更新子窗口标题（同源示例）
      childDoc.title = "已更新 - " + (frameId === 'frame1' ? "不虚系列下载" : "信息课工具箱下载");
      
      // 2. 跳转到新URL（同源/跨域均可）
      iframe.src = newUrl;
      
      console.log(`子窗口 ${frameId} 已更新`);
    } catch (e) {
      // 跨域时会抛出异常，此时仅能更新src
      iframe.src = newUrl;
      console.log(`子窗口 ${frameId} 已通过URL更新（跨域限制）`);
    }
  }
}

// 页面加载完成后初始化示例（同源操作）
window.onload = function() {
  // 对第一个iframe进行示例操作（仅同源有效）
  const frame1 = document.getElementById('frame1');
  try {
    if (frame1) {
      const childWin = frame1.contentWindow;
      // 可以调用子窗口的函数（如果子窗口定义了的话）
      if (typeof childWin.init === 'function') {
        childWin.init();
      }
    }
  } catch (e) {
    console.log("跨域限制：无法执行子窗口函数");
  }
};
</script>





