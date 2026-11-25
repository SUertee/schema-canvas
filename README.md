# Schema Canvas

**将数据库 Schema 转换成适合探索、审查和交接的交互式 HTML 数据库地图。**

Schema Canvas 是一个 Codex Skill。它读取数据库 Schema、迁移文件或 ORM 定义，生成可离线打开的单文件 HTML ERD，帮助你理解数据表、关系、字段约束和产品页面背后的数据流。

## 能做什么

- 按业务数据域组织复杂 Schema
- 搜索表名与字段
- 聚焦直接关联的表和关系路径
- 区分真实外键、逻辑关系与结构缺口
- 查看字段、类型、约束、默认值和索引
- 按产品页面、迁移前后或数据流重组画布
- 生成便于评审和 Agent 交接的数据库地图

## 安装

```bash
git clone https://github.com/SUertee/schema-canvas.git \
  "$HOME/.codex/skills/schema-canvas"
```

私有仓库需要先在目标设备配置 GitHub 登录或 SSH 凭据。

安装后开启一个新的 Codex 任务，并要求使用 `schema-canvas`：

```text
使用 schema-canvas，根据当前数据库 Schema 生成一份交互式 HTML ERD。
```

## 更新

```bash
cd "$HOME/.codex/skills/schema-canvas"
git pull
```

## 输出原则

生成结果是一个自包含的 `.html` 文件，CSS、JavaScript 和 Schema 数据均内嵌，不依赖构建流程，并且可以离线浏览。Schema Canvas 只根据结构证据生成图表，不应写入数据库记录、凭据或个人数据。

## License

[MIT](LICENSE)
