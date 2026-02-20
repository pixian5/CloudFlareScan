# CloudFlareScan (ipv4&ipv6)  
CloudFlare 扫描器 （简称CFS)  适配 Win / macOS / Ubuntu

<img width="592" height="473" alt="f261513fd8ecf2" src="https://github.com/user-attachments/assets/5b64dee6-6911-4c29-8f57-b86a581a4586" />


软件演示视频：https://www.youtube.com/watch?v=x9NTDJqV2uk

🚀 高效扫描：自动从 CloudFlare 官方 IP 段生成 IP 地址

📊 双模式测速：完全测速 + 地区测速，满足不同需求

🌍 全球覆盖：内置全球大部分机场IATA代码映射，自动识别地区

⚡ 异步处理：支持高并发测试，快速获取结果

📋 一键复制：双击表格单元格即可复制内容

📈 实时统计：显示扫描进度、速度

---

## 📦 下载

每次向 `main` 分支提交代码后，GitHub Actions 会自动为三个平台编译并发布到 [Releases 页面](../../releases/latest)：

| 平台 | 文件 | 说明 |
|------|------|------|
| Windows 10/11 (x64) | `CloudFlareScan-Windows.exe` | 直接双击运行 |
| macOS Apple Silicon (M芯片, arm64) | `CloudFlareScan-macOS-arm64.zip` | 解压后运行 .app |
| Ubuntu / Linux (x86_64) | `CloudFlareScan-Ubuntu-x86_64.zip` | 解压后运行二进制文件 |

> **自动发布说明**：每次合并到 `main` 分支，CI 流水线（`.github/workflows/build-windows.yml`）自动并行编译三个平台版本，完成后覆盖更新 [Latest Release](../../releases/latest)。也可在 Actions 页面手动触发（`workflow_dispatch`）。

---

## 使用方法

**Windows**：下载 `CloudFlareScan-Windows.exe`，直接双击运行。

**macOS（M芯片）**：下载并解压 `CloudFlareScan-macOS-arm64.zip`，将 `.app` 拖入应用程序文件夹。  
首次运行前需在「系统设置 → 隐私与安全性」中允许运行，或在终端执行：

```bash
osascript -e 'do shell script "sudo spctl --master-disable" with administrator privileges'
```

**Ubuntu / Linux**：下载并解压 `CloudFlareScan-Ubuntu-x86_64.zip`，给文件加执行权限后运行：

```bash
chmod +x CloudFlareScan-Linux
./CloudFlareScan-Linux
```

