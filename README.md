# CloudFlareScan (ipv4&ipv6)  
CloudFlare 扫描器 （简称CFS)  适配 Win / macOS / Ubuntu

<img width="592" height="473" alt="f261513fd8ecf2" src="https://github.com/user-attachments/assets/5b64dee6-6911-4c29-8f57-b86a581a4586" />


软件演示视频：https://www.youtube.com/watch?v=x9NTDJqV2uk

---

## ✨ 功能介绍

### 🔍 IP 扫描
- **IPv4 扫描**：自动从 CloudFlare 官方 IPv4 IP 段（CIDR 列表）中随机生成 IP 地址，并发发起 HTTPS 连接测试，快速筛选出可访问的 IP。
- **IPv6 扫描**：同样支持 CloudFlare 官方 IPv6 段，自动生成并测试 IPv6 地址的可达性。
- **端口选择**：支持多种扫描端口（443、2053、2083、2087、2096、8443），可按需切换，满足不同网络环境下的连通性测试。

### 📊 双模式测速
- **地区测速**：扫描完成后，按 IATA 机场代码识别 IP 所属地区，可选择指定地区进行测速，精准找出最优节点。
- **完全测速**：对所有扫描到的可用 IP 进行全量下载速度测试，获取每个 IP 的真实下载速率（MB/s）和延迟（ms）。
- **测速结果表格**：结果以表格形式展示，含 IP 地址、下载速度、所属地区（中文名）、延迟及端口，支持双击单元格一键复制。

### 🌍 全球地区识别
- 内置全球主要机场 IATA 代码与中文地区名的映射表，覆盖亚洲、欧洲、美洲、大洋洲等 200+ 地区，自动将 IP 归属地显示为中文名称。

### ⚡ 高性能异步处理
- 基于 `asyncio` + `aiohttp` 实现全异步并发扫描，单次可同时测试大量 IP，扫描速度快、资源占用低。

### 📈 实时进度显示
- 进度条实时反映扫描/测速进度。
- 进度条下方同步显示当前状态（就绪 / 扫描中 / 测速中）和实时扫描速度（IP/秒）。
- 右侧日志面板滚动输出详细的扫描和测速日志，方便追踪每一步操作。

### 📋 结果导出
- 支持将测速结果一键导出为 CSV 文件，便于后续分析和使用。

### 🖥️ 跨平台 GUI
- 基于 PySide6（Qt6）构建，界面简洁美观，原生支持 Windows、macOS（Apple Silicon & Intel）、Ubuntu/Linux。

---

## 📦 下载

每次向 `main` 分支提交代码后，GitHub Actions 会自动为三个平台编译并发布到 [Releases 页面](../../releases/latest)：

| 平台 | 文件 | 说明 |
|------|------|------|
| Windows 10/11 (x64) | `CloudFlareScan-Windows.exe` | 直接双击运行 |
| macOS Apple Silicon (M芯片, arm64) | `CloudFlareScan-macOS-arm64.zip` | 解压后运行 .app |
| macOS Intel (x86_64) | `CloudFlareScan-macOS-x86_64.zip` | 解压后运行 .app |
| Ubuntu / Linux (x86_64) | `CloudFlareScan-Linux` | 给文件加执行权限后运行 |

> **自动发布说明**：每次合并到 `main` 分支，CI 流水线（`.github/workflows/build-windows.yml`）自动并行编译三个平台版本，完成后覆盖更新 [Latest Release](../../releases/latest)。也可在 Actions 页面手动触发（`workflow_dispatch`）。

---

## 使用方法

**Windows**：下载 `CloudFlareScan-Windows.exe`，直接双击运行。

**macOS（M芯片）**：下载并解压 `CloudFlareScan-macOS-arm64.zip`，将 `.app` 拖入应用程序文件夹。  
首次运行前需在「系统设置 → 隐私与安全性」中允许运行，或在终端执行：

```bash
osascript -e 'do shell script "sudo spctl --master-disable" with administrator privileges'
```

**macOS（Intel）**：下载并解压 `CloudFlareScan-macOS-x86_64.zip`，同上操作。

**Ubuntu / Linux**：下载 `CloudFlareScan-Linux`，给文件加执行权限后运行：

```bash
chmod +x CloudFlareScan-Linux
./CloudFlareScan-Linux
```

