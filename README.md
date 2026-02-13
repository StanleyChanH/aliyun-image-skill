# 阿里云百炼图像生成与编辑 Skill

[![Version](https://img.shields.io/badge/version-1.0.4-blue.svg)](https://clawhub.com)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![ClawHub](https://img.shields.io/badge/ClawHub-Synced-green.svg)](https://clawhub.com/skill/aliyun-image)

阿里云百炼平台提供的图像生成与编辑能力，包含千问-文生图(Qwen-Image)和千问-图像编辑(Qwen-Image-Edit)两个模型系列。

## 🔄 同步更新

本项目在 **GitHub** 和 **ClawHub** 同步发布更新：

- **GitHub 仓库**: https://github.com/StanleyChanH/aliyun-image-skill
- **ClawHub 页面**: https://clawhub.com/skill/aliyun-image
- **GitHub Actions**: 自动同步 ✅

### 自动同步机制
- ✅ 使用 GitHub Actions 自动同步到 ClawHub
- ✅ 每次推送到 `main` 分支自动触发
- ✅ 版本号和更新日志保持一致
- ✅ GitHub Release 自动创建

### 配置自动同步
查看 [.github/SETUP.md](.github/SETUP.md) 了解如何配置 GitHub Actions 自动同步。

## 更新日志

### v1.0.4 (2026-02-13)
- 修复 GitHub Actions 权限问题
- 添加 `permissions: contents: write` 以支持自动创建 Release
- 完整测试自动同步流程

### v1.0.3 (2026-02-13)
- 测试 GitHub Actions 自动同步到 ClawHub
- 验证自动发布流程

### v1.0.2 (2026-02-13)
- 作者改为 StanleyChanH
- 添加 GitHub Actions 自动同步到 ClawHub
- 更新文档说明 GitHub 和 ClawHub 同步更新机制
- 添加配置文档 .github/SETUP.md

### v1.0.1 (2026-02-13)
- 更新 API 文档和示例代码
- 优化技能说明和触发词
- 完善参考文档结构

## 功能特性

### 🎨 文生图 (Qwen-Image)
- 根据文本描述生成图像
- 支持复杂文字渲染
- 多种分辨率选择
- 智能提示词改写

### ✏️ 图像编辑 (Qwen-Image-Edit)
- 单图编辑：修改文字、增删物体、改变动作
- 多图融合：人物换装、姿势迁移
- 风格迁移：艺术风格转换
- 细节增强：图像质量提升

## 支持的模型

### 文生图模型
- `qwen-image-max` - 高质量，真实感强
- `qwen-image-plus` - 性价比高，多样化风格
- `qwen-image` - 基础版

### 图像编辑模型
- `qwen-image-edit-max` - 高质量编辑
- `qwen-image-edit-plus` - 性价比高
- `qwen-image-edit` - 基础版

## 安装要求

### 环境变量
```bash
export DASHSCOPE_API_KEY="your_api_key_here"
```

### 获取 API Key
1. 访问 [阿里云百炼控制台](https://bailian.console.aliyun.com/)
2. 创建并获取 API Key
3. 配置到环境变量

### 依赖安装（可选）
```bash
pip install dashscope
```

## 使用示例

### 文生图
```python
import requests

response = requests.post(
    "https://dashscope.aliyuncs.com/api/v1/services/aigc/multimodal-generation/generation",
    headers={
        "Authorization": f"Bearer {DASHSCOPE_API_KEY}"
    },
    json={
        "model": "qwen-image-plus",
        "input": {
            "messages": [{
                "role": "user",
                "content": [{"text": "一只可爱的橘猫"}]
            }]
        },
        "parameters": {
            "size": "1024*1024"
        }
    }
)
```

### 图像编辑
```python
response = requests.post(
    "...",
    json={
        "model": "qwen-image-edit-plus",
        "input": {
            "messages": [{
                "role": "user",
                "content": [
                    {"image": "https://example.com/input.jpg"},
                    {"text": "把背景改成星空"}
                ]
            }]
        }
    }
)
```

## 特点

✅ 国内网络友好（阿里云服务）
✅ 支持中文提示词
✅ 多种分辨率选择
✅ 智能提示词优化
✅ 24小时图像存储

## 适用场景

- 小红书封面生成
- 产品宣传图制作
- 社交媒体内容创作
- 艺术风格迁移
- 图像修复与增强

## 许可证

MIT

## 作者

StanleyChanH

## 同步更新

本项目在 **GitHub** 和 **ClawHub** 同步发布更新：

- **GitHub**: https://github.com/StanleyChanH/aliyun-image-skill
- **ClawHub**: https://clawhub.com/skill/aliyun-image

每次发布新版本时，会同时推送到两个平台，确保用户可以从任一渠道获取最新版本。

### 版本同步策略
- 所有版本更新优先发布到 GitHub
- 通过自动化流程同步到 ClawHub
- 两个平台保持版本号一致

---

**注意**：使用本 skill 需要 [阿里云百炼](https://bailian.console.aliyun.com/) 账号和 API Key。
