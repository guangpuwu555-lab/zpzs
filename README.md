# 招聘助手 Codex 插件

这是一个用于 BOSS 直聘候选人筛选、标记与复盘记录的 Codex 个人插件。插件会先读取本地的候选人筛选执行器配置，再指导 Codex 锁定 BOSS 直聘桌面应用完成候选人卡片识别、详情页评分、打招呼标记和筛选结果记录。

## 功能

- 按当前筛选执行器配置读取目标岗位、打招呼数量、学校规则、AI深度筛选和筛选建议。
- 在 BOSS 直聘桌面应用中执行候选人筛选，不把浏览器页面当作候选人操作入口。
- 根据岗位要求、稳定性、空窗、项目成果和风险信号评分。
- 对超过阈值的候选人点击可见的“打招呼”作为合适标记。
- 将每位处理过的候选人写回工具的“筛选结果”。

## 安装

1. 下载或克隆这个仓库。
2. 把整个 `zhaopin-zhushou` 插件目录放到 Codex 的个人插件目录，或在 Codex 里让它安装这个本地插件。
3. 重启或刷新 Codex。
4. 在对话里使用 `@zhaopin-zhushou`，或说“使用招聘助手，按当前工具配置执行 BOSS 直聘筛选”。

## 目录结构

```text
zhaopin-zhushou/
  .codex-plugin/
    plugin.json
  skills/
    zhaopin-zhushou/
      SKILL.md
      agents/
        openai.yaml
      references/
        boss-screening-rules.md
```

## 默认工具位置

插件会优先检查这些位置：

- `%USERPROFILE%\Desktop\outputs\recruiting-screening-tool.html`
- `%USERPROFILE%\Documents\招聘助手\recruiting-screening-tool.html`
- `http://127.0.0.1:17338/`

如果你的筛选执行器在其他位置，直接在对话里提供具体文件路径即可。

## 维护

筛选逻辑主要维护在：

- `skills/zhaopin-zhushou/SKILL.md`
- `skills/zhaopin-zhushou/references/boss-screening-rules.md`

当用户纠正判断逻辑时，把新的规则同步进这两个文件，保持学校规则为选填，并继续强调候选人操作发生在 BOSS 直聘桌面应用中。
