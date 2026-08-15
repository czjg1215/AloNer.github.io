<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="陈张吉果 - 个人简历">
    <title>陈张吉果 - 个人简历</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }

        /* 页面主体：背景图 + 遮罩 */
        body {
            font-family: "PingFang SC", "Microsoft YaHei", "Helvetica Neue", Arial, sans-serif;
            min-height: 100vh;
            padding: 40px 20px;
            color: #fff;
            line-height: 1.6;
            position: relative;
            background: #1a1a2e;
        }

        /* 背景图层：模糊处理后的图片 */
        body::before {
            content: "";
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            background: url("bg.jpg") center/cover no-repeat;
            filter: blur(8px) brightness(0.6);
            transform: scale(1.1);
            z-index: -2;
        }

        /* 暗色遮罩层，增强文字可读性 */
        body::after {
            content: "";
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            background: rgba(10, 10, 30, 0.45);
            z-index: -1;
        }

        /* 简历主容器：玻璃拟态效果 */
        .resume-container {
            max-width: 900px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.12);
            backdrop-filter: blur(24px) saturate(1.4);
            -webkit-backdrop-filter: blur(24px) saturate(1.4);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.18);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3), inset 0 1px 0 rgba(255,255,255,0.1);
            overflow: hidden;
        }

        /* 顶部彩色装饰条 */
        .top-bar {
            height: 6px;
            background: linear-gradient(90deg, #667eea, #764ba2, #f093fb, #f5576c);
        }

        /* 头部区域：玻璃拟态 */
        .header {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            padding: 50px 60px 40px;
            display: flex;
            align-items: center;
            gap: 40px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        /* 头像 */
        .avatar {
            width: 130px;
            height: 130px;
            border-radius: 50%;
            flex-shrink: 0;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
            object-fit: cover;
            border: 3px solid rgba(255, 255, 255, 0.3);
        }

        .header-info { flex: 1; }
        .name {
            font-size: 36px;
            font-weight: 700;
            color: #fff;
            margin-bottom: 18px;
            letter-spacing: 2px;
            text-shadow: 0 2px 8px rgba(0,0,0,0.3);
        }
        .contact-list {
            display: flex;
            flex-wrap: wrap;
            gap: 16px 28px;
        }
        .contact-item {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 14px;
            color: rgba(255, 255, 255, 0.85);
        }
        .contact-item .icon {
            width: 22px;
            height: 22px;
            background: rgba(102, 126, 234, 0.7);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            font-size: 11px;
            flex-shrink: 0;
        }

        .main-content { padding: 40px 60px 50px; }
        .section { margin-bottom: 36px; }
        .section:last-child { margin-bottom: 0; }

        /* 区块标题 */
        .section-title {
            font-size: 20px;
            font-weight: 700;
            color: #fff;
            margin-bottom: 20px;
            padding-bottom: 12px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
            display: flex;
            align-items: center;
            gap: 12px;
            text-shadow: 0 1px 4px rgba(0,0,0,0.2);
        }
        .section-title .icon-box {
            width: 32px;
            height: 32px;
            background: rgba(102, 126, 234, 0.6);
            backdrop-filter: blur(8px);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            font-size: 15px;
            border: 1px solid rgba(255,255,255,0.15);
        }

        /* 教育背景：玻璃卡片 + 悬停浮起 + 点击链接 */
        .edu-item {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 16px;
            padding: 16px 20px;
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(12px);
            border-radius: 12px;
            border-left: 4px solid rgba(102, 126, 234, 0.8);
            border-top: 1px solid rgba(255,255,255,0.1);
            border-right: 1px solid rgba(255,255,255,0.05);
            border-bottom: 1px solid rgba(255,255,255,0.05);
            cursor: pointer;
            transition: transform 0.25s, box-shadow 0.25s, background 0.25s;
            text-decoration: none;
            color: inherit;
        }
        .edu-item:hover {
            transform: translateY(-4px);
            background: rgba(255, 255, 255, 0.16);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.25);
            border-color: rgba(255, 255, 255, 0.2);
        }
        .edu-main { flex: 1; }
        .edu-school {
            font-size: 17px;
            font-weight: 600;
            color: #fff;
            margin-bottom: 4px;
        }
        .edu-major {
            font-size: 14px;
            color: rgba(180, 190, 255, 0.9);
            font-weight: 500;
        }
        .edu-time {
            font-size: 13px;
            color: rgba(255, 255, 255, 0.6);
            white-space: nowrap;
            margin-left: 20px;
        }

        /* 技能标签 */
        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .skill-tag {
            padding: 8px 18px;
            background: rgba(102, 126, 234, 0.5);
            backdrop-filter: blur(8px);
            color: #fff;
            border-radius: 20px;
            font-size: 13px;
            font-weight: 500;
            border: 1px solid rgba(255,255,255,0.15);
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
        }
        .skill-tag.secondary {
            background: rgba(255, 255, 255, 0.1);
            color: rgba(255, 255, 255, 0.85);
            box-shadow: none;
        }

        /* 项目经历：玻璃卡片 */
        .project-item {
            margin-bottom: 22px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(12px);
            border-radius: 12px;
            border-left: 4px solid rgba(118, 75, 162, 0.8);
            border-top: 1px solid rgba(255,255,255,0.1);
            border-right: 1px solid rgba(255,255,255,0.05);
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }
        .project-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }
        .project-name {
            font-size: 17px;
            font-weight: 600;
            color: #fff;
        }
        .project-role {
            font-size: 13px;
            color: rgba(200, 180, 255, 0.95);
            font-weight: 500;
            background: rgba(118, 75, 162, 0.3);
            padding: 3px 12px;
            border-radius: 12px;
            border: 1px solid rgba(255,255,255,0.1);
        }
        .project-desc {
            font-size: 14px;
            color: rgba(255, 255, 255, 0.75);
            line-height: 1.8;
        }
        .project-desc ul {
            margin-left: 18px;
            margin-top: 6px;
        }
        .project-desc li {
            margin-bottom: 4px;
        }

        /* 兴趣爱好 */
        .hobby-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 14px;
        }
        .hobby-item, a.hobby-item {
            text-align: center;
            padding: 18px 10px;
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(12px);
            border-radius: 12px;
            transition: transform 0.2s, box-shadow 0.2s, background 0.2s;
            border: 1px solid rgba(255,255,255,0.1);
            text-decoration: none;
            color: inherit;
            display: block;
            cursor: pointer;
        }
        .hobby-item:hover {
            transform: translateY(-3px);
            background: rgba(255, 255, 255, 0.15);
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }
        .hobby-icon {
            font-size: 28px;
            margin-bottom: 8px;
            color: rgba(180, 190, 255, 0.9);
        }
        .hobby-name {
            font-size: 14px;
            color: rgba(255, 255, 255, 0.85);
            font-weight: 500;
        }

        /* 个人特色 */
        .feature-box {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(12px);
            border-radius: 12px;
            padding: 24px;
            border: 1px dashed rgba(102, 126, 234, 0.5);
        }
        .feature-text {
            font-size: 14px;
            color: rgba(255, 255, 255, 0.8);
            line-height: 2;
        }
        .feature-text p {
            margin-bottom: 6px;
        }

        /* 打印按钮 */
        .print-btn {
            position: fixed;
            bottom: 30px;
            right: 30px;
            padding: 14px 28px;
            background: rgba(102, 126, 234, 0.6);
            backdrop-filter: blur(12px);
            color: #fff;
            border: 1px solid rgba(255,255,255,0.2);
            border-radius: 30px;
            font-size: 15px;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
            transition: transform 0.2s, background 0.2s;
            z-index: 100;
        }
        .print-btn:hover {
            transform: scale(1.05);
            background: rgba(102, 126, 234, 0.8);
        }

        /* 响应式 */
        @media (max-width: 768px) {
            body { padding: 0; }
            .resume-container {
                border-radius: 0;
                border: none;
            }
            .header {
                flex-direction: column;
                text-align: center;
                padding: 30px 24px;
            }
            .contact-list { justify-content: center; }
            .main-content { padding: 24px; }
            .edu-item { flex-direction: column; }
            .edu-time {
                margin-left: 0;
                margin-top: 8px;
            }
            .project-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 6px;
            }
            .print-btn {
                bottom: 15px;
                right: 15px;
                padding: 10px 18px;
                font-size: 13px;
            }
        }

        /* 打印样式：去除玻璃效果，恢复白底 */
        @media print {
            body {
                background: #fff;
                padding: 0;
            }
            body::before, body::after {
                display: none;
            }
            .resume-container {
                box-shadow: none;
                border-radius: 0;
                background: #fff;
                border: none;
                color: #333;
                backdrop-filter: none;
            }
            .header {
                background: #f8f9fc;
                border-bottom: 1px solid #e8ecf4;
                backdrop-filter: none;
            }
            .name { color: #1a1a2e; text-shadow: none; }
            .contact-item { color: #555; }
            .section-title {
                color: #1a1a2e;
                border-bottom: 2px solid #667eea;
                text-shadow: none;
            }
            .section-title .icon-box {
                background: linear-gradient(135deg, #667eea, #764ba2);
                border: none;
            }
            .edu-item, .project-item, .hobby-item, .feature-box {
                background: #f8f9fc;
                border: none;
                border-left: 4px solid #667eea;
                backdrop-filter: none;
            }
            .project-item { border-left: 4px solid #764ba2; }
            .edu-school, .project-name { color: #1a1a2e; }
            .edu-major { color: #667eea; }
            .edu-time { color: #888; }
            .project-role {
                color: #764ba2;
                background: rgba(118, 75, 162, 0.1);
                border: none;
            }
            .project-desc { color: #555; }
            .hobby-icon { color: #667eea; }
            .hobby-name { color: #555; }
            .feature-text { color: #555; }
            .skill-tag {
                background: linear-gradient(135deg, #667eea, #764ba2);
                border: none;
                backdrop-filter: none;
            }
            .skill-tag.secondary {
                background: #f0f2f8;
                color: #555;
            }
            .print-btn { display: none; }
        }
    </style>
</head>
<body>
    <div class="resume-container">
        <div class="top-bar"></div>
        <header class="header">
            <img class="avatar" src="avatar.jpg" alt="头像">
            <div class="header-info">
                <h1 class="name">陈张吉果</h1>
                <div class="contact-list">
                    <div class="contact-item">
                        <span class="icon"><i class="fas fa-phone"></i></span>
                        <span>18457346533</span>
                    </div>
                    <div class="contact-item">
                        <span class="icon"><i class="fas fa-envelope"></i></span>
                        <span>czjg20071215@qq.com</span>
                    </div>
                    <div class="contact-item">
                        <span class="icon"><i class="fas fa-map-marker-alt"></i></span>
                        <span>浙江省杭州市</span>
                    </div>
                    <div class="contact-item">
                        <span class="icon"><i class="fas fa-graduation-cap"></i></span>
                        <span>杭州师范大学 / 国际商务</span>
                    </div>
                </div>
            </div>
        </header>

        <main class="main-content">
            <section class="section">
                <h2 class="section-title">
                    <span class="icon-box"><i class="fas fa-graduation-cap"></i></span>
                    教育背景
                </h2>
                <a href="https://abs.hznu.edu.cn/portal/" target="_blank" class="edu-item">
                    <div class="edu-main">
                        <div class="edu-school">杭州师范大学阿里巴巴商学院</div>
                        <div class="edu-major">国际商务 / 本科</div>
                    </div>
                    <div class="edu-time">2026.09 - 至今</div>
                </a>
            </section>

            <section class="section">
                <h2 class="section-title">
                    <span class="icon-box"><i class="fas fa-cogs"></i></span>
                    专业技能
                </h2>
                <div class="skill-tags">
                    <span class="skill-tag">Office办公软件</span>
                    <span class="skill-tag">数据分析</span>
                    <span class="skill-tag">商务英语</span>
                    <span class="skill-tag">熟练使用各类AI工具</span>
                    <span class="skill-tag secondary">国际贸易实务</span>
                    <span class="skill-tag secondary">市场营销</span>
                    <span class="skill-tag secondary">跨文化沟通</span>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">
                    <span class="icon-box"><i class="fas fa-laptop-code"></i></span>
                    项目经历 / 实践经历
                </h2>
                <article class="project-item">
                    <div class="project-header">
                        <span class="project-name">个人简历网站项目</span>
                        <span class="project-role">开发者</span>
                    </div>
                    <div class="project-desc">
                        <ul>
                            <li>利用AI工具完成个人简历的编辑与网页部署</li>
                            <li>制作网页小游戏等前端项目</li>
                        </ul>
                    </div>
                </article>
                <article class="project-item">
                    <div class="project-header">
                        <span class="project-name">社区图书馆志愿者实践活动</span>
                        <span class="project-role">志愿者</span>
                    </div>
                    <div class="project-desc">
                        <ul>
                            <li>参与社区图书馆的日常管理与读者服务工作</li>
                            <li>协助组织阅读推广活动，服务社区居民</li>
                        </ul>
                    </div>
                </article>
            </section>

            <section class="section">
                <h2 class="section-title">
                    <span class="icon-box"><i class="fas fa-star"></i></span>
                    兴趣爱好
                </h2>
                <div class="hobby-grid">
                    <div class="hobby-item">
                        <div class="hobby-icon"><i class="fas fa-book"></i></div>
                        <div class="hobby-name">阅读</div>
                    </div>
                    <a href="https://music.163.com/playlist?id=3200784717&uct2=U2FsdGVkX19vD8chuSGSNWIhPAiCyglB2LUKM9apRAk=" target="_blank" class="hobby-item">
                        <div class="hobby-icon"><i class="fas fa-music"></i></div>
                        <div class="hobby-name">音乐</div>
                    </a>
                    <div class="hobby-item">
                        <div class="hobby-icon"><i class="fas fa-camera"></i></div>
                        <div class="hobby-name">摄影</div>
                    </div>
                    <div class="hobby-item">
                        <div class="hobby-icon"><i class="fas fa-plane"></i></div>
                        <div class="hobby-name">旅行</div>
                    </div>
                    <a href="https://steamcommunity.com/profiles/76561199165981457/" target="_blank" class="hobby-item">
                        <div class="hobby-icon"><i class="fas fa-gamepad"></i></div>
                        <div class="hobby-name">游戏</div>
                    </a>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">
                    <span class="icon-box"><i class="fas fa-gem"></i></span>
                    个人特色
                </h2>
                <div class="feature-box">
                    <div class="feature-text">
                        <p><i class="fas fa-check" style="color:rgba(180,190,255,0.9);margin-right:8px;"></i>具有较强的学习能力和适应能力，能够快速掌握新知识和新技能</p>
                        <p><i class="fas fa-check" style="color:rgba(180,190,255,0.9);margin-right:8px;"></i>善于沟通协作，具备良好的团队合作精神</p>
                        <p><i class="fas fa-check" style="color:rgba(180,190,255,0.9);margin-right:8px;"></i>工作认真负责，注重细节，执行力强</p>
                        <p><i class="fas fa-check" style="color:rgba(180,190,255,0.9);margin-right:8px;"></i>积极乐观，抗压能力强，能够在压力下保持高效工作</p>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <button class="print-btn" onclick="window.print()">
        <i class="fas fa-print"></i> 打印 / 保存为PDF
    </button>
</body>
</html>
