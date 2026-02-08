# Online Jupyter Notebook on Binder

> 面向：GitHub + Binder 部署工程师 / Python 依赖打包 / Jupyter Notebook 发布

本仓库提供一套**可复制、可执行、一步到位**的 Binder 在线 JupyterLab 方案：
- 点击下方 Badge 即可启动 JupyterLab
- 自动打开指定 Notebook：`notebooks/demo.ipynb`
- 提供两套依赖方案：
  - **A. 默认推荐（更稳更快）**：`environment.yml`
  - **B. 扩展版（更重更慢）**：`environment-full.yml`

## 🚀 一键启动

> 使用前：请将下方链接中的 `YOUR_GITHUB_USERNAME/REPO_NAME` 替换为你的真实仓库路径。

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/YOUR_GITHUB_USERNAME/REPO_NAME/HEAD?labpath=notebooks%2Fdemo.ipynb)

**直达链接格式：**
```
https://mybinder.org/v2/gh/<USER>/<REPO>/HEAD?labpath=notebooks%2Fdemo.ipynb
```

## 依赖方案说明

### A. 默认推荐（`environment.yml`）
- 目标：**构建快、成功率高、最小可用**
- 包含：`python=3.10`、`numpy`、`pandas`、`torch (CPU)`、`transformers`、`accelerate`
- 适合：基础数据处理 + 张量计算 + 轻量 NLP 演示

> 如果 Binder 构建失败（常见于 `torch` 安装），可临时注释 `environment.yml` 中的 `torch` 相关行后重试。详见下方排查清单。

### B. 扩展版（`environment-full.yml`）
- 目标：**更完整的大模型推理依赖**（构建慢、失败风险高）
- 额外包含：`sentencepiece`、`tokenizers`、`datasets` 等

## 使用说明（本地或 Binder 内）

```bash
# 进入仓库后（Binder 启动即在仓库根目录）
# JupyterLab 中打开 notebooks/demo.ipynb 并依次运行
```

## 切换到扩展版依赖（可选）

Binder 默认只识别 `environment.yml`。若要使用扩展版：
1. 将 `environment-full.yml` 重命名为 `environment.yml`
2. 推送到 GitHub
3. 重新打开 Binder 链接

---

如果你需要将该方案直接部署到自己的仓库，请参考 `notebooks/demo.ipynb` 中的示例代码与 README 的发布步骤。
