# 现场笔记 · 机器人运维知识库

移动机器人（AGV / AMR）现场实施与运行故障排查的个人知识库。纯静态站点，无构建步骤、无第三方依赖，克隆后用浏览器打开即可查看。

- 线上地址：https://37ln30asn2rfopf3ej8.traesite.cn
- 文档环境：CentOS 7.8，RCS 以 3.x 和 4.x 为主；硬件以潜伏叉车为主
- 覆盖方向：实施部署、通信与接口、地图与定位、配置与工具、硬件与外设、排障方法（共 26 篇，含 21 篇手册整理笔记）

## 目录结构

```text
.
├── index.html                          首页：检索、分类、文档列表、排障速查
├── assets/
│   └── style.css                       全站样式
├── posts/
│   ├── troubleshooting-layers.html     通用分层排查法
│   ├── deployment-checklist.html       现场实施交付清单
│   ├── ros2-comm-timeout.html          ROS 2 通信超时与丢包
│   ├── amr-localization-drift.html     AMR 定位漂移
│   ├── device-node-changed.html        串口设备命名治理
│   └── vendor/                         厂商手册整理笔记（21 篇 + data 源数据，已并入主库分类）
├── docs/
│   └── CONVERSATION.md                 需求演进、部署记录与决策
└── .nojekyll                           跳过 GitHub Pages 的 Jekyll 处理
```

## 本地预览

直接双击 `index.html` 即可；如需更接近线上的访问方式：

```bash
python -m http.server 8000
# 打开 http://localhost:8000
```

## 新增一篇文档

1. 复制 `posts/` 下任意文件并重命名，修改标题、描述与正文。
2. 同步修改该页左侧目录与右侧本页目录的链接。
3. 在 `index.html` 的「全部文档」列表中新增一条 `.note-row`，填写 `href`、`data-cat`、`data-text`（搜索关键词）。
4. 若新增分类，还需在分类卡片与筛选按钮中补充对应项。

## 部署

| 通道 | 方式 | 说明 |
|-|-|-|
| 主站 | Trae 部署工具 | 站点 ID `37ln30asn2rfopf3ej8`，所有人可见 |
| 镜像 | GitHub Pages | 推送 `main` 后自动发布：https://beisheng2333.github.io/robot-kb/ |

GitHub Pages 直接从 `main` 分支根目录发布，无需构建。`.nojekyll` 用于跳过 Jekyll 处理，保证静态文件原样输出。

## 约定

- 不引入框架与构建工具，保持可直接静态托管。
- 不加载第三方脚本，检索与目录高亮均为原生 JS。
- 文档中的命令与结论均需在真机验证后再合并。
- 厂商手册只做原创提炼，不复制原文、不搬运 PDF；手册原件经脱敏后仅存放于私有归档站，不进入本仓库。
