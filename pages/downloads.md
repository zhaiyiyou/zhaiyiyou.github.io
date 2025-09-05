---
layout: default
title: 下载
keywords: 下载, 不虚系列, 信息课工具箱
description: 资源下载页面
permalink: /downloads/
---

<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>下载</title>
    <meta name="keywords" content="下载, 不虚系列, 信息课工具箱">
    <meta name="description" content="资源下载页面">
    <style>
        /* 免责声明弹窗样式 */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0, 0, 0, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        .modal-content {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            width: 80%;
            max-width: 600px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            max-height: 80vh;
            overflow-y: auto;
        }
        .highlight {
            font-weight: bold;
            color: #d9534f;
        }
        .countdown {
            text-align: center;
            font-size: 18px;
            margin: 20px 0;
            color: #666;
        }
        .confirm-btn {
            display: block;
            width: 200px;
            margin: 0 auto;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .confirm-btn:disabled {
            background-color: #cccccc;
            cursor: not-allowed;
        }

        /* 下载区域样式 */
        .download-container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 30px;
            display: none; /* 初始隐藏 */
            flex-direction: column;
            gap: 30px;
        }
        .download-section {
            width: 90%;
            margin: 0 auto;
            padding: 20px;
            background-color: #f9f9f9;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }
        .download-wrapper {
            width: 100%;
            border-radius: 6px;
            overflow: hidden;
            border: 1px solid #ddd;
            transition: all 0.3s ease;
        }
        .download-iframe {
            width: 100%;
            min-height: 360px;
            max-height: 450px;
            height: 45vh;
            border: none;
            overflow: auto;
        }
        
        /* 响应式调整 */
        @media (max-width: 1024px) {
            .download-iframe { height: 41.25vh; }
        }
        @media (max-width: 768px) {
            .download-container { padding: 15px; }
            .download-section { width: 95%; }
            .download-iframe { height: 52.5vh; min-height: 375px; }
        }
        @media (max-width: 480px) {
            .download-iframe { height: 48.75vh; min-height: 338px; }
        }
    </style>
</head>
<body>
    <!-- 免责声明弹窗 -->
    <div class="modal-overlay" id="disclaimerModal">
        <div class="modal-content">
            <h1>软件免责声明</h1>
            <div class="disclaimer-text">
                <p><span class="highlight">1.所有软件免费使用，如果你是买来的你就被骗了</span></p>
                <p><span class="highlight">2.你可以从QQ345405851索要软件激活码来激活未开放的功能</span></p>
                <p><span class="highlight">3.所有对电脑文件的删除，替换，修改均属用户自愿行为，作者没有教唆用户使用任何功能</span></p>
                <p><span class="highlight">4.如果因为使用软件造成学习成绩下降，被处分，被禁止使用电脑，本人不负任何责任</span></p>
                <p><span class="highlight">5.如果免责声明修改默认同意修改后的免责声明</span></p>
                <p><span class="highlight">6.最终解释权归开发者所有</span></p>
            </div>
            <div class="countdown" id="countdown">请仔细阅读免责声明，<span id="time">10</span>秒后可确认</div>
            <button class="confirm-btn" id="confirmBtn" disabled>我知道了</button>
        </div>
    </div>

    <!-- 下载区域 -->
    <div class="download-container" id="downloadContainer">
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

    <script>
        // 免责声明倒计时逻辑
        let timeLeft = 10;
        const countdownElement = document.getElementById('time');
        const confirmBtn = document.getElementById('confirmBtn');
        const disclaimerModal = document.getElementById('disclaimerModal');
        const downloadContainer = document.getElementById('downloadContainer');
        
        const timer = setInterval(() => {
            timeLeft--;
            countdownElement.textContent = timeLeft;
            
            if (timeLeft <= 0) {
                clearInterval(timer);
                confirmBtn.disabled = false;
                document.querySelector('.countdown').textContent = '您现在可以确认免责声明';
            }
        }, 1000);
        
        confirmBtn.addEventListener('click', () => {
            disclaimerModal.style.display = 'none';
            downloadContainer.style.display = 'flex';
            // 存储用户已同意的状态
            localStorage.setItem('disclaimerAgreed', 'true');
        });

        // 检查是否已经同意过免责声明
        if(localStorage.getItem('disclaimerAgreed') === 'true') {
            disclaimerModal.style.display = 'none';
            downloadContainer.style.display = 'flex';
        }
    </script>
</body>
</html>
