# 通讯调试助手 NetDebugAssistant

> 免费 · 绿色单文件 · 无广告 · 面向自动化与嵌入式工程师的一站式网络调试工具

[产品主页](https://haoeastspeed.github.io/NetDebugAssistant-Download/) · [最新版本下载](https://github.com/haoeastspeed/NetDebugAssistant-Download/releases/latest)

## 简介
覆盖从物理串口到工业以太网的现场调试全流程：串口、TCP/UDP、Modbus、MQTT、PLC 协议、实时趋势、报文抓包、网络诊断、脚本自动化，开箱即用。

## 下载
| 版本 | 体积 | 说明 | 下载 |
| --- | --- | --- | --- |
| 轻量版 v1.6.4 | 4.6 MB | 原生 Canvas 趋势，体积最小 | [CommDebugAssistant-1.6.4.exe](https://github.com/haoeastspeed/NetDebugAssistant-Download/releases/download/v1.6.4/CommDebugAssistant-1.6.4.exe) |
| 图表版 v1.6.4 | 17.2 MB | 内置 ScottPlot 图表引擎 | [CommDebugAssistant-1.6.4-charts.exe](https://github.com/haoeastspeed/NetDebugAssistant-Download/releases/download/v1.6.4/CommDebugAssistant-1.6.4-charts.exe) |

**运行环境**：Windows 10/11 x64，需安装 [.NET 8 桌面运行时](https://dotnet.microsoft.com/download/dotnet/8.0)。

## v1.6.4 更新
- **物理掉线自动重连**：TCP 客户端、串口（USB 转串口拔出）、MQTT 掉线后自动检测，并按指数退避（0.5s 起、上限 10s、带随机抖动）自动重连；网络或设备恢复后自动恢复通信，无需手动重连
- **连接状态四态可视化**：连接按钮与状态栏实时反映“连接中 / 已连接 / 重连中 / 已断开”，配合灰 / 蓝 / 绿 / 橙状态圆点；重连中按钮保持可点（点击即终止重连并断开）；物理永久断开时醒目弹框提醒一次
- **多主题切换**：新增浅色 / 深色 / 跟随系统三种主题，运行时即时切换并自动记忆；自绘实时趋势、HMI 仪表与全部标准控件均完成深色适配
- 加固事件容错：连接状态与对端上下线事件改为逐个订阅者隔离，单个界面回调异常不再影响其它订阅者或通信主循环；打开前即挂接状态事件、失败兜底释放，杜绝串口句柄与订阅泄漏
- 235 项单元测试（新增连接状态机、指数退避、主题解析、TCP 真实环回掉线-自动重连、串口无设备、MQTT 掉线重连）、双版本双主题离屏全功能冒烟全部通过

## 功能特性
- 串口通信：RS-232/485、引脚状态、非标准波特率、HEX 显示
- TCP/UDP：客户端/服务端、多会话并行、IPv4/IPv6 双栈
- Modbus：RTU / ASCII / TCP 主从仿真，9 种数据类型、寄存器网格写回
- MQTT 3.1.1：QoS 0/1/2、保活、掉线检测与自动重连
- PLC 协议：S7comm、EtherNet/IP 主动主站
- 实时趋势：多通道曲线，原生 / ScottPlot 双引擎，支持浅色 / 深色主题
- 报文抓包：pktmon 抓包、pcapng 解析、工业协议识别
- 网络诊断：Ping、子网设备扫描、端口探测
- 脚本自动化：JavaScript 规则应答与批量下发
- 会话录制回放、轻量 HMI 与阈值告警、通信统计与故障注入

## 自动更新
软件内置**自研轻量自动更新**：启动时静默检查（也可手动检查）→ 流式下载并经 SHA256 完整性校验 → 原地自替换并重启，失败自动回退跳板脚本。

## 说明
本仓库为**公开发布渠道**，仅提供成品软件与更新清单；**源代码保持私有，不公开**。
