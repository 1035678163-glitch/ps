# PS · 图像生成与修图 Skills

收录三个用于角色一致性、写实图像和重新打光的 skill，保留上游技能说明、脚本和参考资料。

| Skill | 用途 | 文件 |
|---|---|---|
| ComfyUI Character Gen | 角色身份保持、参考图生成、ComfyUI 工作流方案 | [SKILL.md](skills/comfyui-character-gen/SKILL.md) |
| Photoreal Image | 写实摄影提示词、构图与材质细节、生成结果评估 | [SKILL.md](skills/photoreal-image/SKILL.md) |
| RunComfy Relight | 改变现有图片的光线方向、色温和氛围 | [SKILL.md](skills/relight/SKILL.md) |

## 在 Codex 中使用

将 `skills/` 中的三个技能文件夹复制到个人技能目录 `~/.agents/skills/`。如果同名技能已经存在，请先比较版本，避免直接覆盖。

安装后可在下一轮对话中直接请求：

- “使用 comfyui-character-gen，为这张角色参考图设计保持身份一致的 ComfyUI 工作流。”
- “使用 photoreal-image，设计自然窗光的人像摄影提示词。”
- “使用 relight，把这张产品图改成左侧柔和窗光。”

Codex 会自动发现技能；若列表没有更新，可重启应用。安装位置参见 [OpenAI 官方技能文档](https://learn.chatgpt.com/docs/build-skills)。

## 运行条件

- **ComfyUI Character Gen**：技能提供工作流指导；实际生成需要可用的 ComfyUI、相应模型与自定义节点。
- **Photoreal Image**：自带生成脚本需要 Bash、curl、jq，以及所选服务的 API 密钥。Windows 可在配置好这些工具的 Bash 环境中运行。也可使用技能中的提示词设计方法。
- **RunComfy Relight**：实际运行需要 `@runcomfy/cli` 和 RunComfy 登录或令牌；服务调用可能收费。

此次收录仅安装技能文件，没有下载模型、配置密钥或发起付费生成。没有执行 Photoreal Image 附带的 `install-everywhere.sh`，因此未改动其他助手的全局规则。

## 来源与维护

来源、版本记录及许可证说明见 [SOURCES.md](SOURCES.md)。各技能保留各自的 `LICENSE`；上游模型、价格和兼容性说明可能变化，实际使用前应核对对应服务。

已知上游问题：ComfyUI 技能引用了缺失的 `references/research-log.md`；当前包中实际提供的是 `references/research-2025.md`。本仓库保留上游原文，不将二者视为同一份资料。
