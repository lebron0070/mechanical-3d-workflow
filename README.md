# Mechanical 3D Workflow

**通用机械 3D 建模与交互 Skill** — 用自然语言描述对象，让支持工具执行的 AI 智能体按统一流程制作可编辑机械模型与交互网页。

适用于机械蜘蛛、发动机、机械臂、车辆和原创机械机器人。默认使用 Blender + Three.js，支持总成拆解还原、部件聚焦、线框观察、机构运动，以及按需变形、音效和本地录制。

**这是 Skill，不是现成模型或一键建模软件。** 仓库仅包含工作流指令、参考规范与安装说明，不包含大黄蜂、蜘蛛模型、第三方模型或运行环境。生成质量取决于智能体能力、参考资料、工具和迭代，不承诺电影原模复刻或可直接制造。

## 下载与安装

### 方法一：下载后交给智能体安装

1. 打开 GitHub 仓库 **[lebron0070/mechanical-3d-workflow](https://github.com/lebron0070/mechanical-3d-workflow)**。
2. 点击绿色 **Code → Download ZIP**，然后解压。
3. 找到 `skills/mechanical-3d-workflow/` 文件夹。保留里面的 `SKILL.md`、`references/` 和 `agents/`，不要只复制一个 Markdown 文件。
4. 打开支持 Skill 和本地文件操作的智能体（例如 Codex），把解压目录交给它，发送：

> 请检查这个目录中的 skills/mechanical-3d-workflow，并安装为可用的本地 Skill。保留 references 和 agents 子目录。如果已有同名 Skill，请先告诉我，不要直接覆盖。安装后确认能找到 mechanical-3d-workflow。

5. 安装后新开一轮对话并选择该 Skill；若未出现，重启客户端。不同智能体的安装入口和支持格式不同，不保证所有聊天应用都能直接导入。

### 方法二：Codex 从 GitHub 安装

在 Codex 中发送：

```text
使用 $skill-installer 安装 GitHub 仓库 lebron0070/mechanical-3d-workflow
中的 skills/mechanical-3d-workflow。
如果已经安装同名 Skill，请先询问我是否更新。
```

也可以手动把完整 Skill 文件夹放到项目的 `.agents/skills/mechanical-3d-workflow/`。安装路径与发现机制见 [Codex 官方 Skills 文档](https://developers.openai.com/codex/skills/)。本仓库发布的是独立 Skill，不是插件商店条目。

## 示例提问

### 机械蜘蛛

```text
使用 $mechanical-3d-workflow，生成一个原创八足机械蜘蛛。
采用白色装甲、深色机械骨架和金属关节。
支持行走、调速、按总成拆解还原；拆开后仍可运动。
点选组件可以放大，其余组件用线框保留空间关系。
使用默认实验室布局，交付 Blender 源文件、GLB 和本地交互网页。
先检查工具环境，不要部署到公网。
```

### 发动机科普

```text
使用 $mechanical-3d-workflow，制作涡扇发动机科普模型。
按风扇、压气机、燃烧室、涡轮、轴系和机匣划分总成。
支持启动、演示转速、拆解还原、部件聚焦与作用说明。
风扇叶片保留整组，不逐片散开；拆开后转子仍可运转。
使用默认实验室布局，标明原理示意与未经验证的部分。
```

### 六轴机械臂

```text
使用 $mechanical-3d-workflow，生成六轴工业机械臂展示。
右侧滑块控制关节与夹爪，设置明确的关节限位。
底部控制总成拆解与还原，舞台支持整体视角、聚焦和重置。
只需要单一形态，不添加声音、录制或变形。
```

其他智能体不支持 `$skill-name` 语法时，使用它自己的 Skill 选择方式，或明确要求读取并遵循这个 Skill。

## 默认界面

| 操作分区 | 默认内容 |
|---|---|
| 顶部项目栏 | 名称、适用时的形态切换、源模型下载 |
| 左侧三维舞台 | 模型、视角、重置、状态与操作提示 |
| 底部结构控制 | 拆解百分比、还原；多形态时增加变形时间轴 |
| 右侧控制台 | 动作、速度/关节、部件选择、说明与聚焦 |

固定操作分区，不固定角色或动作数量。声音、录制、双形态只在需要时加入。完整规则见 [界面规范](skills/mechanical-3d-workflow/references/interface-layout.md)。

## 环境与边界

- 需要能读写项目文件、运行代码与检查浏览器的智能体；普通纯聊天窗口不足以直接交付可运行模型。
- 通常需要 Blender、Python、现代 WebGL 浏览器；使用网页工具链时可能需要 Node.js。先让智能体检查，不要求关闭安全限制。
- Skill 不捆绑依赖，不自动安装软件、付费调用 API 或上传文件；额外操作仍需相应授权。
- 本地网页地址不是公网链接。不要将参考资料、私有模型或客户数据未经许可公开。
- “工业机械感”不等于工程认证；3D 打印还需独立验证尺寸、流形、壁厚、公差、碰撞与切片。
- 参考照片、角色形象、外部模型与音频各有自己的权利边界；本仓库许可证不授予第三方素材使用权。

## 仓库内容

```text
skills/mechanical-3d-workflow/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── assets.md
    ├── interaction.md
    ├── interface-layout.md
    └── media-qa.md
```

发布校验：Skill 格式、相对引用、文件清单与隐私路径扫描。本仓库不含可直接运行的演示应用；安装 Skill 不代表已生成模型。

## 许可证

[MIT](LICENSE)。欢迎复用、修改和提交改进；分发时保留许可证和版权声明。
