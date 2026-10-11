# Novel Agent

Novel Agent 是一个面向长篇小说的 AI 辅助分析与编辑项目，目标是支持文档导入、故事信息整理、检索、模型接入和可审阅的文本编辑流程。

当前仓库提供 Python 包与模块骨架。章节分析、检索、模型调用、API 等业务能力仍在规划中，详见 [PLAN.md](PLAN.md)。

## 环境要求

- Python 3.11 或更高版本
- Git

## 安装

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -e ".[dev]"
```

按需安装文档格式或 OpenAI 兼容接口依赖：

```powershell
python -m pip install -e ".[documents]"
python -m pip install -e ".[openai]"
```

## 运行

安装后运行命令行入口：

```powershell
novel-agent
```

目前入口会提示项目骨架已就绪；尚未实现小说分析或编辑操作。

## 开发

```powershell
python -m pytest
ruff check .
```

应用代码位于 `src/novel_agent/`。测试目录按 `unit/`、`integration/` 和 `agent/` 分类，测试素材放在 `tests/fixtures/`。

## 安全与隐私

- 不要提交 API 密钥、Token、`.env` 文件、个人凭据或私有小说文稿。
- 本地小说数据建议放入被 Git 忽略的 `data/` 或 `novels/` 目录。
- 未来的文档修改能力应采用“提出补丁、审阅后应用”的流程，避免分析操作直接改写原文。
