<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes, viewport-fit=cover">
<title>量化系统迁移公告 · 安全声明</title>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        margin: 0;
        font-family: "PingFang SC", "Microsoft YaHei", "Inter", system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Arial, sans-serif;
        background: radial-gradient(circle at top, #0b1220, #050814);
        color: #e5e7eb;
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        overflow-x: hidden;
        padding: 1rem;
    }

    .container {
        width: 92%;
        max-width: 640px;
        background: rgba(10, 18, 34, 0.7);
        backdrop-filter: blur(12px);
        border: 1px solid rgba(56, 189, 248, 0.25);
        border-radius: 2rem;
        padding: 1.6rem 1.5rem 1.8rem;
        text-align: center;
        box-shadow: 0 25px 40px rgba(0, 0, 0, 0.5), 0 0 0 0.5px rgba(56, 189, 248, 0.15) inset;
        transition: all 0.2s ease;
        max-height: 95vh;
        overflow-y: auto;
        scrollbar-width: thin;
    }

    .container::-webkit-scrollbar {
        width: 4px;
        background: rgba(255,255,255,0.05);
    }
    .container::-webkit-scrollbar-thumb {
        background: #38bdf880;
        border-radius: 8px;
    }

    .tag {
        display: inline-block;
        padding: 4px 12px;
        background: rgba(56, 189, 248, 0.15);
        color: #7dd3fc;
        border-radius: 60px;
        font-size: 12px;
        font-weight: 500;
        letter-spacing: 0.5px;
        margin-bottom: 14px;
        backdrop-filter: blur(2px);
        border: 0.5px solid rgba(56, 189, 248, 0.3);
    }

    .title {
        font-size: 1.7rem;
        font-weight: 700;
        background: linear-gradient(135deg, #fff, #b0e0ff);
        background-clip: text;
        -webkit-background-clip: text;
        color: transparent;
        margin-bottom: 8px;
    }

    .desc {
        font-size: 0.85rem;
        line-height: 1.5;
        color: #cbd5f0;
        max-width: 95%;
        margin: 0 auto 6px auto;
    }

    /* 域名区域整体容器，内部元素居中 */
    .domain-section {
        margin: 16px 0 12px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
    }

    .site {
        width: 100%;
        font-size: 1.4rem;
        font-weight: 600;
        color: #38bdf8;
        background: rgba(0, 20, 40, 0.6);
        padding: 10px 12px;
        border-radius: 1.2rem;
        border: 1px dashed rgba(56, 189, 248, 0.6);
        word-break: break-all;
        user-select: all;
        font-family: 'SF Mono', 'Fira Code', monospace;
        letter-spacing: 0.3px;
        cursor: pointer;
        transition: 0.15s;
        margin-bottom: 12px;
        text-align: center;
    }

    .site:active {
        background: rgba(56, 189, 248, 0.15);
        transform: scale(0.99);
    }

    /* 复制按钮居中 */
    .btn-copy {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        gap: 6px;
        padding: 10px 26px;
        background: #38bdf8;
        color: #0b1220;
        border-radius: 40px;
        font-weight: bold;
        font-size: 0.85rem;
        cursor: pointer;
        user-select: none;
        transition: all 0.2s;
        border: none;
        box-shadow: 0 6px 12px rgba(56, 189, 248, 0.2);
        margin-bottom: 6px;
        /* 确保居中 */
        text-align: center;
    }

    .btn-copy:hover {
        background: #7ac9ff;
        transform: translateY(-2px);
    }

    .status {
        margin-top: 8px;
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 8px;
        background: rgba(34, 197, 94, 0.08);
        width: fit-content;
        margin-left: auto;
        margin-right: auto;
        padding: 4px 14px;
        border-radius: 60px;
        font-size: 0.7rem;
        font-weight: 500;
        color: #bbf0d1;
    }

    .dot {
        display: inline-block;
        width: 8px;
        height: 8px;
        background: #22c55e;
        border-radius: 50%;
        box-shadow: 0 0 6px #2ecc71;
        animation: pulse 1.2s infinite ease-in-out;
        vertical-align: middle;
    }

    @keyframes pulse {
        0% { transform: scale(0.95); opacity: 0.7; box-shadow: 0 0 0 0 rgba(46, 204, 113, 0.5);}
        50% { transform: scale(1.2); opacity: 1; box-shadow: 0 0 0 6px rgba(46, 204, 113, 0);}
        100% { transform: scale(0.95); opacity: 0.7; box-shadow: 0 0 0 0 rgba(46, 204, 113, 0);}
    }

    /* 安全声明卡片 – 置于底部 */
    .security-card {
        background: rgba(0, 20, 50, 0.65);
        border-radius: 1.3rem;
        padding: 1rem 1.2rem;
        margin-top: 20px;
        margin-bottom: 6px;
        text-align: left;
        border: 1px solid rgba(56, 189, 248, 0.3);
        backdrop-filter: blur(4px);
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
    }

    .security-title {
        font-weight: 700;
        font-size: 0.9rem;
        color: #7dd3fc;
        display: flex;
        align-items: center;
        gap: 8px;
        margin-bottom: 8px;
        border-left: 3px solid #38bdf8;
        padding-left: 10px;
    }

    .security-quote {
        font-size: 0.82rem;
        line-height: 1.45;
        color: #eef2ff;
        background: rgba(0, 0, 0, 0.35);
        padding: 8px 12px;
        border-radius: 1rem;
        margin-bottom: 8px;
        font-weight: 500;
    }

    .security-quote strong {
        color: #facc15;
        font-weight: 700;
    }

    .security-footer-text {
        font-size: 0.78rem;
        color: #bbd7fb;
        margin: 6px 0 0 4px;
        font-weight: 500;
        display: flex;
        align-items: center;
        gap: 6px;
        flex-wrap: wrap;
    }

    .badge-group {
        display: flex;
        flex-wrap: wrap;
        gap: 8px;
        margin-top: 10px;
    }

    .badge {
        background: rgba(56, 189, 248, 0.12);
        border-radius: 60px;
        padding: 3px 10px;
        font-size: 0.65rem;
        font-weight: 500;
        color: #9ac7ff;
        border: 0.5px solid rgba(56, 189, 248, 0.4);
    }

    .tip {
        margin-top: 8px;
        font-size: 0.65rem;
        color: #94a3b8;
        background: rgba(0, 0, 0, 0.3);
        display: inline-block;
        padding: 3px 12px;
        border-radius: 30px;
        text-align: center;
    }

    .toast {
        position: fixed;
        bottom: 30px;
        left: 50%;
        transform: translateX(-50%);
        background: rgba(0, 0, 0, 0.9);
        backdrop-filter: blur(12px);
        color: #fff;
        padding: 8px 18px;
        border-radius: 40px;
        font-size: 0.8rem;
        display: none;
        z-index: 1000;
        white-space: nowrap;
        border: 1px solid #38bdf8;
        align-items: center;
        gap: 8px;
    }

    .footer-note {
        font-size: 0.6rem;
        color: #6f8fbb;
        text-align: center;
        margin-top: 10px;
        padding-top: 6px;
        border-top: 1px solid rgba(56,189,248,0.15);
    }

    @media (max-width: 560px) {
        .container {
            padding: 1.2rem 1rem;
        }
        .title {
            font-size: 1.45rem;
        }
        .site {
            font-size: 1.1rem;
            padding: 8px 8px;
        }
        .security-quote {
            font-size: 0.75rem;
        }
        .btn-copy {
            padding: 8px 22px;
            font-size: 0.8rem;
        }
    }
</style>
</head>
<body>

<div class="container">
    <!-- 顶部标签 -->
    <div class="tag">⚡ SYSTEM MIGRATION · 安全托管声明</div>

    <!-- 主标题 -->
    <div class="title">量化交易系统迁移公告</div>

    <!-- 简要描述 -->
    <div class="desc">
        系统已完成升级与节点迁移，请复制下方新域名访问。
    </div>

    <!-- 新域名区域 + 居中复制按钮（域名下面直接是复制按钮，整体居中） -->
    <div class="domain-section">
        <div class="site" id="domainText">skjsuw.github.io/2.1</div>
        <div class="btn-copy" id="copyBtn">📋 一键复制域名</div>
        <div class="tip">💡 点击上方域名区域 或 按钮均可复制</div>
    </div>

    <!-- 系统状态指示器 -->
    <div class="status">
        <span class="dot"></span>
        系统状态：运行正常 · 已迁移完成
    </div>

    <!-- ★★★★★ 安全声明区块：放置在底部，确保一个屏幕可见全部内容 ★★★★★ -->
    <div class="security-card">
        <div class="security-title">
            🔒 【安全声明】
            <span style="font-size: 0.6rem; background: #38bdf820; padding: 2px 8px; border-radius: 30px;">公开 · 透明 · 非托管</span>
        </div>
        <div class="security-quote">
            本系统运行于OKX钱包去中心化环境，您的资金始终保留在<strong> 您自己创建的钱包地址</strong>内，系统无权触碰或转移。私钥由您独家掌管，资产安全由区块链底层技术保障。
        </div>
        <div class="security-footer-text">
            💎 稳定 · 透明 · 非托管 —— 您的资产，您全权掌控。
        </div>
        <div class="badge-group">
            <span class="badge">🔐 私钥自持 · 链上确权</span>
            <span class="badge">🛡️ 非托管机制</span>
            <span class="badge">📜 所有交易可查</span>
        </div>
    </div>

    <!-- 底部极简脚标 -->
    <div class="footer-note">
        ✅ 资金永远在您创建的钱包内运行 · 系统无权触碰
    </div>
</div>

<!-- 复制提示toast -->
<div class="toast" id="toast">✅ 复制成功，新域名已保存</div>

<script>
    (function() {
        const DOMAIN = "skjsuw.github.io/2.1";
        const domainElement = document.getElementById("domainText");
        const copyButton = document.getElementById("copyBtn");
        const toastEl = document.getElementById("toast");

        // 显示toast消息
        function showToastMessage(msg) {
            if (!toastEl) return;
            toastEl.innerHTML = msg || "✅ 复制成功，新域名已保存";
            toastEl.style.display = "flex";
            setTimeout(() => {
                toastEl.style.display = "none";
                // 恢复默认文案
                setTimeout(() => {
                    if (toastEl) toastEl.innerHTML = "✅ 复制成功，新域名已保存";
                }, 100);
            }, 1600);
        }

        // 核心复制函数
        function copyDomain() {
            // 现代 clipboard 优先
            if (navigator.clipboard && window.isSecureContext) {
                navigator.clipboard.writeText(DOMAIN).then(() => {
                    showToastMessage("📋 复制成功 · " + DOMAIN);
                }).catch(() => {
                    fallbackCopyMethod();
                });
            } else {
                fallbackCopyMethod();
            }
        }

        // 降级方案（兼容微信/旧浏览器）
        function fallbackCopyMethod() {
            const textarea = document.createElement("textarea");
            textarea.value = DOMAIN;
            textarea.style.position = "fixed";
            textarea.style.top = "-9999px";
            textarea.style.left = "-9999px";
            document.body.appendChild(textarea);
            textarea.select();
            textarea.setSelectionRange(0, DOMAIN.length);
            let success = false;
            try {
                success = document.execCommand("copy");
            } catch (err) {
                console.warn("execCommand error", err);
            }
            document.body.removeChild(textarea);
            if (success) {
                showToastMessage("📋 复制成功 · " + DOMAIN);
            } else {
                showToastMessage("⚠️ 请手动长按上方域名复制");
            }
        }

        // 绑定按钮复制事件
        if (copyButton) {
            copyButton.addEventListener("click", (e) => {
                e.preventDefault();
                copyDomain();
            });
        }

        // 域名区域点击同样支持复制，增强体验
        if (domainElement) {
            domainElement.style.cursor = "pointer";
            domainElement.addEventListener("click", (e) => {
                e.stopPropagation();
                copyDomain();
            });
            // 增加微交互反馈
            domainElement.addEventListener("mousedown", () => {
                domainElement.style.transform = "scale(0.98)";
            });
            domainElement.addEventListener("mouseup", () => {
                domainElement.style.transform = "";
            });
            domainElement.addEventListener("mouseleave", () => {
                domainElement.style.transform = "";
            });
        }

        // 确保控制台输出辅助信息
        console.log("[迁移公告] 新域名: " + DOMAIN + " | 安全声明已嵌入: 资金始终在您创建的钱包运行");
    })();
</script>
</body>
</html>
