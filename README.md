# � GPT Image 2 Skill — 图像生成提示词专家

<p align="center">
  <img src="assets/logo.svg" alt="JC-GPTImage2-Skill" width="120"/>
</p>

<p align="center">
  <strong>GPT Image 2 提示词图库 + Agent Skill + CLI</strong><br/>
  精选可复用提示词模板 + 一键调用 OpenAI 图像生成 API<br/>
  基于 <a href="https://github.com/wuyoscar/gpt_image_2_skill">wuyoscar/GPT-Image2-Skill</a>，增加美影厂动画技法、游戏风格路由、NewAPI 代理支持
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License: MIT"/></a>
  <img src="https://img.shields.io/badge/model-gpt--image--2-purple.svg" alt="Model: gpt-image-2"/>
  <img src="https://img.shields.io/badge/python-≥3.11-blue.svg" alt="Python ≥ 3.11"/>
</p>

---

## ✨ 这是什么

一个 **GPT Image 2 专用提示词图库 + Agent Skill + CLI 工具**。包含 30+ 品类的可复用提示词模板，覆盖动漫、游戏、摄影、排版、UI、数据可视化、科研图表等场景。Skill 模式下，Agent 会自动搜索匹配的图库模板、组装最优 prompt、调用 API 出图。

### 相比上游的新增内容

| 新增 | 说明 |
|------|------|
| 🎌 **美影厂动画技法**（8 种） | 工笔重彩、水墨动画、敦煌壁画、剪纸皮影、定格动画、折纸动画、漫画极简、水墨剪纸 — 上海美术电影制片厂经典技法全覆盖 |
| 🎮 **游戏风格路由**（7 种） | 原神、黑神话悟空、凡人修仙传、诡秘之主、宝可梦、星露谷、潜水员戴夫 — 一键生成对应风格的「游戏实况截图」 |
| 🔗 **NewAPI 代理支持** | CLI 支持 `OPENAI_BASE_URL` 自定义 API 地址，可走韭菜盒子 NewAPI 全渠道路由 |

---

## 📦 安装

### 韭菜盒子 Studio

```bash
git clone https://github.com/liuyunlong2021-wq/JC-GPTImage2-skill.git ~/.agents/skills/JC-GPTImage2-skill
```

在韭菜盒子的 Skill 管理面板中刷新即可看到 `gpt-image` skill。

### Claude Code

```text
/plugin marketplace add wuyoscar/gpt_image_2_skill
/plugin install gpt-image@wuyoscar-skills
```

### Codex

```text
$skill-installer
Install this skill from GitHub:
https://github.com/wuyoscar/gpt_image_2_skill/tree/main/skills/gpt-image
```

### CLI 命令行

```bash
# 直接运行（无需安装）
uvx --from git+https://github.com/wuyoscar/gpt_image_2_skill gpt-image -p "a cat astronaut"

# 安装到 PATH
uv tool install git+https://github.com/wuyoscar/gpt_image_2_skill
gpt-image -p "a cat astronaut"

# 使用 NewAPI 代理
OPENAI_BASE_URL=https://api.jiucaihezi.studio/v1 gpt-image -p "一只在太空漫步的猫"
```

---

## 🗂️ 图库分类（30+ 品类）

| 分类 | 条目数 | 说明 |
|------|:---:|------|
| 🎌 动漫 · 美影厂 | 20 | 日式动画 + 上海美影厂 8 种经典技法 |
| 🎮 游戏风格路由 | 7 风格 | 原神/黑神话/修仙/诡秘/宝可梦/星露谷/潜水员戴夫 |
| 🎬 影视 · 动画 | 5 | 电影级镜头、动画关键帧 |
| 👤 角色设计 | 3 | 含 Banana Pro 多面板参考图模板 |
| 📝 排版 · 海报 | 13 | 中英文排版、印刷海报、LOGO 设计 |
| 📷 摄影 | 4 | 含 360° 环景摄影模板 |
| 🎨 插画 · 水彩 | 4 | 多种插画风格 + 水墨 |
| 🕹️ 像素 · 等距 | 4 | 像素艺术、等距视图 |
| 📦 产品 · 食物 | 4 | 电商主图、美食摄影 |
| 🧩 品牌 VI | 3 | 品牌系统、视觉识别 |
| 📊 信息图 · 科研 | 29 | 数据可视化 + 科研论文图表 |
| 📱 UI/UX | 5 | 应用界面、仪表盘 Mockup |
| ⚙️ 技术插图 | 5 | 爆炸图、机械制图 |
| 🏛️ 建筑 · 室内 | 5 | 建筑渲染、室内设计 |
| 🔬 科学教育 | 7 | 科普图解、生物医学 |
| 👗 时尚 · 美妆 | 8 | 时装编辑、美妆摄影 |
| 🎨 纯艺绘画 | 5 | 油画、水粉、丙烯等 |
| 🎥 电影参考 | 6 | 经典电影镜头风格 |
| 🎟️ 活动 · 体验 | 2 | 展览、演出视觉 |
| 🖋️ 纹身设计 | 4 | 纹身手稿风格 |
| 🖥️ 屏幕摄影 | 2 | 带屏幕反光的摄影 |
| 🎬 故事板 · 道具 · 场景 | 6 | 分镜宫格 + 道具 + 场景主镜头 |

> 完整索引见 `JC-GPT-Image2-Skill/gpt-image/references/gallery.md`

---

## 🚀 快速开始

### Agent 模式下

在对话中直接说：

```
生成一张原神风格的桂林山水游戏截图
用美影厂水墨动画风格画一只猫
做一张带中文标题的科技海报
生成一张 360 度环景照：热带雨林
```

Agent 会自动搜索匹配的图库模板、组装 prompt、调用 API 出图。

### CLI 模式下

```bash
# 文生图
gpt-image -p "MAPPA-style anime action still, a cyberpunk samurai in rainy Tokyo"

# 参考图编辑
gpt-image -p "turn this into Studio Ghibli style" -i photo.jpg

# 指定尺寸和质量
gpt-image -p "a poster with Chinese text 韭菜盒子" --size portrait --quality high

# 使用 NewAPI 代理
OPENAI_BASE_URL=https://api.jiucaihezi.studio/v1 \
  gpt-image -p "ink-wash animation style, a lone boat on misty river"
```

---

## 📁 目录结构

```
JC-GPTImage2-skill/
├── README.md
├── LICENSE                    # MIT
├── CLAUDE.md                  # 开发笔记
├── assets/                    # logo 等
│   ├── logo.svg
│   └── guanfangweixin.jpg
├── JC-GPT-Image2-Skill/       # 主 Skill
│   ├── LICENSE                # 上游 MIT
│   ├── README.md              # 上游说明
│   └── gpt-image/
│       ├── SKILL.md           # Skill 定义 + Agent 操作手册
│       ├── agents/            # Agent 配置
│       ├── references/        # 30+ 分类图库（gallery-*.md）
│       │   ├── gallery.md                     # 图库索引（先读这个）
│       │   ├── gallery-anime-and-manga.md      # 🎌 动漫 · 美影厂
│       │   ├── gallery-game-style-routing.md   # 🎮 游戏风格路由
│       │   ├── craft.md                        # 提示词工艺手册
│       │   └── ...（30+ 品类）
│       └── scripts/
│           └── generate.py    # CLI 启动器
└── src/
    └── gpt_image_cli/         # Python CLI 源码
        ├── __init__.py
        └── cli.py
```

---

## 🔑 环境配置

CLI 按以下优先级读取配置：

1. 进程环境变量 `OPENAI_API_KEY`、`OPENAI_BASE_URL`
2. `~/.env` 文件
3. 项目 `.env` 文件

```bash
# ~/.env 示例
OPENAI_API_KEY=sk-your-key-here
OPENAI_BASE_URL=https://api.jiucaihezi.studio/v1   # 可选，使用 NewAPI 代理
```

---

## 📄 许可

本项目 MIT License。上游 [wuyoscar/GPT-Image2-Skill](https://github.com/wuyoscar/gpt_image_2_skill) 同样 MIT License。

图库中的 prompt 条目保留原始作者署名和来源标注。新增的美影厂系列、游戏风格路由等条目版权归本项目。

---

## 🙏 致谢

- [wuyoscar/GPT-Image2-Skill](https://github.com/wuyoscar/gpt_image_2_skill) — 上游项目，提供完整的图库框架和 CLI
- 上海美术电影制片厂 — 美影厂系列条目的风格来源
- 韭菜盒子 Studio — NewAPI 代理支持

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request。新增图库条目请：

1. 在对应的 `gallery-*.md` 中追加
2. 更新 `gallery.md` 索引
3. 保留原始作者署名（如有参考来源）
