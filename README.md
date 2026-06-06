# igocan-marketingpitch-generator

> 作者 igocan，更多 skill 欢迎访问我的 GitHub，好用欢迎给星星 [igocan-AI](https://github.com/igocan-AI)

[![Stars](https://img.shields.io/github/stars/igocan-AI/igocan-marketingpitch-generator?style=social)](https://github.com/igocan-AI/igocan-marketingpitch-generator/stargazers)
[![Forks](https://img.shields.io/github/forks/igocan-AI/igocan-marketingpitch-generator?style=social)](https://github.com/igocan-AI/igocan-marketingpitch-generator/network/members)
[![Release](https://img.shields.io/github/v/release/igocan-AI/igocan-marketingpitch-generator?label=version)](https://github.com/igocan-AI/igocan-marketingpitch-generator/releases)
[![Downloads](https://img.shields.io/github/downloads/igocan-AI/igocan-marketingpitch-generator/total?label=downloads)](https://github.com/igocan-AI/igocan-marketingpitch-generator/releases)
[![Visitors](https://visitor-badge.laobi.icu/badge?page_id=igocan-AI.igocan-marketingpitch-generator)](https://github.com/igocan-AI/igocan-marketingpitch-generator)

## Skill标签

`igocan-ai` `igocan-automation` `igocan-tools`

## 触发提示词

安装后在对话中输入以下任一关键词即可唤起本 Skill：

| 类型 | 提示词示例 |
|------|----------|
| 标准命令 | `/igocan-marketingpitch-generator` |
| 核心关键词 | 「生成国际站FAQ」「制作销售技巧话术」「配置国际站知识库」「生成买家常问FAQ」 |
| 业务场景 | 「营销话术生成」「FAQ Excel 导出」「AI 知识库填充」 |
| 自然语言 | 「帮我生成国际站买家常问的 30 个 FAQ」「给我做一份销售技巧话术 Excel 上传到 AI 知识库」 |

> 触发后 Skill 会引导你提供店铺/产品/公司链接，自动抓取卖点并生成 ≥30 个全英文 FAQ + 15–20 个销售技巧，导出为 `买家常问FAQ.xlsx` 和 `销售技巧.xlsx`，可直接上传国际站 AI 知识库。

## 技术栈

- Python (pandas / openpyxl)
- Web 信息抓取 (web_fetch / browser sessions)
- AI 话术生成

## 快速运行

1. 将 `SKILL.md` 安装到支持 Skill 加载的 AI Agent 平台（如 QoderWork）
2. 唤起命令：对话中输入 `/igocan-marketingpitch-generator` 或相关触发词（"生成国际站FAQ"、"制作销售技巧话术"、"配置国际站知识库"）
3. 按引导提供店铺链接或公司信息，自动完成话术生成与 Excel 导出

## 项目说明

为阿里巴巴国际站（Alibaba.com）商家量身打造的知识库话术生成工具。核心能力：

- **店铺信息深度挖掘**：自动抓取店铺首页、产品详情页、公司介绍页的核心卖点（工厂面积、认证资质、OEM能力等）
- **全链路FAQ生成**：覆盖工厂情况、支付方式、MOQ、样品政策、交期、定制服务、质检售后、物流等30+个标准化英文问答
- **高频拒抗点话术**：15-20个销售技巧，涵盖运费、价格、信任、供应商转换等典型客户异议场景
- **标准XLSX输出**：直接输出符合国际站AI知识库格式的 Excel 文件，用户可一键上传

## 目录结构

```
igocan-marketingpitch-generator/
├── SKILL.md            # 核心 Skill 源码（安装文件）
├── igocan-tags.md      # 品牌 Skill 标签清单
├── .gitignore          # Git 忽略文件
└── README.md           # 项目说明（本文件）
```

## 版权声明

作者 igocan，更多 skill 欢迎访问我的 GitHub，好用欢迎给星星

GitHub: [igocan-AI](https://github.com/igocan-AI)