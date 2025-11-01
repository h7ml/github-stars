---
project: cursor-free-vip
stars: 39765
description: [Support 0.49.x]（Reset Cursor AI MachineID & Bypass Higher Token Limit） Cursor Ai ，自动重置机器ID ， 免费升级使用Pro功能: You've reached your trial request limit. / Too many free trial accounts used on this machine. Please upgrade to pro. We have this limit in place to prevent abuse. Please let us know if you believe this is a mistake.
url: https://github.com/yeongpin/cursor-free-vip
---

Special thanks to:  
  

### Warp, built for coding with multiple agents.

Available for MacOS, Linux, & Windows  

* * *

➤ Cursor Free VIP
=================

  

#### Support Latest 0.49.x Version | 支持最新 0.49.x 版本

This tool is for educational purposes, currently the repo does not violate any laws. Please support the original project. This tool will not generate any fake email accounts and OAuth access.

Supports Windows, macOS and Linux.

For optimal performance, run with privileges and always stay up to date.

這是一款用於學習和研究的工具，目前 repo 沒有違反任何法律。請支持原作者。 這款工具不會生成任何假的電子郵件帳戶和 OAuth 訪問。

支持 Windows、macOS 和 Linux。

對於最佳性能，請以管理員身份運行並始終保持最新。

  

🔄 Change Log | 更新日志
--------------------

Watch Change Log | 查看更新日志

✨ Features | 功能特點
-----------------

-   Support Windows macOS and Linux systems  
    支持 Windows、macOS 和 Linux 系統  
    
-   Reset Cursor's configuration  
    重置 Cursor 的配置  
    
-   Multi-language support (English, 简体中文, 繁體中文, Vietnamese)  
    多語言支持（英文、简体中文、繁體中文、越南語）  
    

💻 System Support | 系統支持
------------------------

Operating System

Architecture

Supported

Windows

x64, x86

✅

macOS

Intel, Apple Silicon

✅

Linux

x64, x86, ARM64

✅

👀 How to use | 如何使用
--------------------

**⭐ Auto Run Script | 腳本自動化運行**

### **Linux/macOS**

curl -fsSL https://raw.githubusercontent.com/yeongpin/cursor-free-vip/main/scripts/install.sh -o install.sh && chmod +x install.sh && ./install.sh

### **Archlinux**

Install via AUR

yay -S cursor-free-vip-git

### **Windows**

irm https://raw.githubusercontent.com/yeongpin/cursor\-free\-vip/main/scripts/install.ps1 | iex

If you want to stop the script, please press Ctrl+C  
要停止腳本，請按 Ctrl+C

❗ Note | 注意事項
-------------

📝 Config | 文件配置 `Win / Macos / Linux Path | 路徑 [Documents/.cursor-free-vip/config.ini]`

**⭐ Config | 文件配置**

```
[Chrome]
# Default Google Chrome Path | 默認Google Chrome 遊覽器路徑
chromepath = C:\Program Files\Google/Chrome/Application/chrome.exe

[Turnstile]
# Handle Turnstile Wait Time | 等待人機驗證時間
handle_turnstile_time = 2
# Handle Turnstile Wait Random Time (must merge 1-3 or 1,3) | 等待人機驗證隨機時間（必須是 1-3 或者 1,3 這樣的組合）
handle_turnstile_random_time = 1-3

[OSPaths]
# Storage Path | 存儲路徑
storage_path = /Users/username/Library/Application Support/Cursor/User/globalStorage/storage.json
# SQLite Path | SQLite路徑
sqlite_path = /Users/username/Library/Application Support/Cursor/User/globalStorage/state.vscdb
# Machine ID Path | 機器ID路徑
machine_id_path = /Users/username/Library/Application Support/Cursor/machineId
# For Linux users: ~/.config/cursor/machineid

[Timing]
# Min Random Time | 最小隨機時間
min_random_time = 0.1
# Max Random Time | 最大隨機時間
max_random_time = 0.8
# Page Load Wait | 頁面加載等待時間
page_load_wait = 0.1-0.8
# Input Wait | 輸入等待時間
input_wait = 0.3-0.8
# Submit Wait | 提交等待時間
submit_wait = 0.5-1.5
# Verification Code Input | 驗證碼輸入等待時間
verification_code_input = 0.1-0.3
# Verification Success Wait | 驗證成功等待時間
verification_success_wait = 2-3
# Verification Retry Wait | 驗證重試等待時間
verification_retry_wait = 2-3
# Email Check Initial Wait | 郵件檢查初始等待時間
email_check_initial_wait = 4-6
# Email Refresh Wait | 郵件刷新等待時間
email_refresh_wait = 2-4
# Settings Page Load Wait | 設置頁面加載等待時間
settings_page_load_wait = 1-2
# Failed Retry Time | 失敗重試時間
failed_retry_time = 0.5-1
# Retry Interval | 重試間隔
retry_interval = 8-12
# Max Timeout | 最大超時時間
max_timeout = 160

[Utils]
# Check Update | 檢查更新
check_update = True
# Show Account Info | 顯示賬號信息
show_account_info = True

[TempMailPlus]
# Enable TempMailPlus | 啓用 TempMailPlus（任何轉發到TempMailPlus的郵件都支持獲取驗證碼，例如cloudflare郵件Catch-all）
enabled = false
# TempMailPlus Email | TempMailPlus 電子郵件
email = xxxxx@mailto.plus
# TempMailPlus pin | TempMailPlus pin碼
epin = 

[WindowsPaths]
storage_path = C:\Users\yeongpin\AppData\Roaming\Cursor\User\globalStorage\storage.json
sqlite_path = C:\Users\yeongpin\AppData\Roaming\Cursor\User\globalStorage\state.vscdb
machine_id_path = C:\Users\yeongpin\AppData\Roaming\Cursor\machineId
cursor_path = C:\Users\yeongpin\AppData\Local\Programs\Cursor\resources\app
updater_path = C:\Users\yeongpin\AppData\Local\cursor-updater
update_yml_path = C:\Users\yeongpin\AppData\Local\Programs\Cursor\resources\app-update.yml
product_json_path = C:\Users\yeongpin\AppData\Local\Programs\Cursor\resources\app\product.json

[Browser]
default_browser = opera
chrome_path = C:\Program Files\Google\Chrome\Application\chrome.exe
edge_path = C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe
firefox_path = C:\Program Files\Mozilla Firefox\firefox.exe
brave_path = C:\Program Files\BraveSoftware/Brave-Browser/Application/brave.exe
chrome_driver_path = D:\VisualCode\cursor-free-vip-new\drivers\chromedriver.exe
edge_driver_path = D:\VisualCode\cursor-free-vip-new\drivers\msedgedriver.exe
firefox_driver_path = D:\VisualCode\cursor-free-vip-new\drivers\geckodriver.exe
brave_driver_path = D:\VisualCode\cursor-free-vip-new\drivers\chromedriver.exe
opera_path = C:\Users\yeongpin\AppData\Local\Programs\Opera\opera.exe
opera_driver_path = D:\VisualCode\cursor-free-vip-new\drivers\chromedriver.exe

[OAuth]
show_selection_alert = False
timeout = 120
max_attempts = 3
```

-   Use administrator privileges to run the script  
    請使用管理員身份運行腳本
    
-   Confirm that Cursor is closed before running the script  
    請確保在運行腳本前已經關閉 Cursor  
    
-   This tool is only for learning and research purposes  
    此工具僅供學習和研究使用  
    
-   Please comply with the relevant software usage terms when using this tool  
    使用本工具時請遵守相關軟件使用條款
    

🚨 Common Issues | 常見問題
-----------------------

如果遇到權限問題，請確保：

此腳本以管理員身份運行

If you encounter permission issues, please ensure:

This script is run with administrator privileges

Error 'User is not authorized'

This means your account was banned for using temporary (disposal) mail. Ensure using a non-temporary mail service

🤩 Contribution | 貢獻
--------------------

歡迎提交 Issue 和 Pull Request！

  
  

📩 Disclaimer | 免責聲明
--------------------

本工具僅供學習和研究使用，使用本工具所產生的任何後果由使用者自行承擔。  

This tool is only for learning and research purposes, and any consequences arising from the use of this tool are borne by the user.

💰 Buy Me a Coffee | 請我喝杯咖啡
---------------------------

  

  

⭐ Star History | 星星數
--------------------

📝 License | 授權
---------------

本項目採用 CC BY-NC-ND 4.0 授權。 Please refer to the LICENSE file for details.
