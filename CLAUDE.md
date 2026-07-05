# CLAUDE.md — JC-GPTImage2-skill

## 这是什么

GPT Image 2 图像生成提示词专家 + 360° 环景图生成工具。基于 [wuyoscar/GPT-Image2-Skill](https://github.com/wuyoscar/GPT-Image2-Skill) 构建，增加了美影厂动画技法图库、游戏风格路由、NewAPI 代理支持等。

## 目录结构

```
JC-GPTImage2-skill/
├── JC-GPT-Image2-Skill/       # GPT Image 2 提示词专家（主 Skill）
│   ├── gpt-image/             #   核心内容
│   │   ├── SKILL.md           #   Skill 定义
│   │   ├── references/        #   30+ 分类图库（gallery-*.md）
│   │   ├── agents/            #   Agent 配置
│   │   └── scripts/           #   执行脚本
│   └── src/                   #   Python CLI（gpt_image_cli）
│
├── JC-360huanjing/            # 360° 环景图生成（原名 JC-360huangjing）
│   ├── SKILL.md
│   └── scripts/               #   环景图生成脚本
│
├── assets/                    # logo.svg + guanfangweixin.jpg
├── README.md
├── LICENSE                    # CC BY-NC 4.0
└── CLAUDE.md                  # 本文件
```

## 图库分类（30+ 品类）

`JC-GPT-Image2-Skill/gpt-image/references/gallery-*.md`

| 文件 | 内容 |
|---|---|
| `gallery-anime-and-manga.md` | 🎌 动漫（含 8 种美影厂技法：工笔重彩/水墨动画/敦煌壁画/剪纸皮影/定格动画/折纸动画/漫画极简/水墨剪纸） |
| `gallery-game-style-routing.md` | 🎮 游戏风格路由（原神/黑神话/凡人修仙传/诡秘之主/宝可梦/星露谷/潜水员戴夫） |
| `gallery-character-design.md` | 👤 角色设计（含 Banana Pro 多面板参考图） |
| `gallery-storyboard.md` | 🎬 故事板宫格 |
| `gallery-prop-design.md` | 🔧 道具设计 |
| `gallery-scene-design.md` | 🏠 场景主镜头 |
| ... | 还有 25+ 品类，见 `gallery.md` 索引 |

## 图库条目格式

每个 gallery 文件：
```markdown
# 🎌 Anime & Manga
Range: No. 1–20 · Count: 20

### No. 1 · 标题
- Image: `docs/anime-manga/xxx.png`
- Metadata: 分类 · `尺寸` · `作者` · Source: [链接]

```text
prompt 模板
```
```

## 与上游的关系

- **基于** `wuyoscar/GPT-Image2-Skill` v0.2.0
- **新增**：美影厂系列、游戏风格路由、Banana Pro 管线模板
- **改动**：CLI 支持 `OPENAI_BASE_URL`、SKILL.md 加 Step 0 密钥检查
- **不改动**：原始 gallery 条目保留原作者和来源标注

## 开发规则

1. **新增图库条目**：在对应 `gallery-*.md` 追加，更新 `gallery.md` 索引和 README
2. **修改上游内容**：标注改动原因，保留原始作者署名
3. **Skill 改名**：`JC-360huangjing` → `JC-360huanjing`
4. **许可证**：本项目 CC BY-NC 4.0，原始 GPT-Image2-Skill 版权归 wuyoscar 所有
5. **Python CLI**：`src/gpt_image_cli/` 目录，基于 OpenAI SDK，支持 NewAPI 代理
