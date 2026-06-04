---
name: igocan-marketingpitch-generator
description: 阿里国际站销售技巧与买家常问FAQ生成器。结合店铺主营产品、公司信息，自动提取卖点，并生成至少30个全英文FAQ和高转化销售话术，最后输出符合国际站AI知识库格式要求的Excel文件。
version: 1.0.0
author: igocan-AI
github: https://github.com/igocan-AI/igocan-marketingpitch-generator
tags:
  - igocan-ai
  - igocan-automation
  - igocan-tools
---

# 阿里国际站知识库（FAQ与销售技巧）生成向导

本技能用于为阿里巴巴国际站（Alibaba.com）商家自动生成符合"AI知识库"要求的"销售技巧"与"买家常问FAQ"。话术注重专业性、引导性和促单转化。

## 触发条件

当用户要求"生成国际站FAQ"、"制作销售技巧话术"、"配置国际站知识库"、"生成买家常问FAQ"等情况时触发。

## 执行流程

### Step 1: 收集店铺与产品信息 (Information Gathering)

需要获取客户的主营产品、公司优势以及店铺定位。请按以下逻辑执行：

1. **优先提取已有资产**：若用户已授权或绑定了"生意助手（Sycm）"，优先尝试获取主营产品；或者在当前工作空间内寻找是否有公司介绍、产品目录等。
2. **引导用户提供链接（Fallback）**：若无现有资料，请回复用户并请其提供以下三类网址（Prompt建议如下）：
   - 店铺首页链接
   - 店铺每个主营品类的一个产品链接
   - 店铺管理 - 管理公司信息页面的链接（或直接用文字介绍公司核心优势）
3. **网页信息抓取**：当用户提供链接后，请使用 `sessions_spawn` (agent_id: `browser` 或 `explore`) 或 `web_fetch` 抓取并总结页面中的核心卖点（如：工厂面积、研发实力、OEM/ODM、认证、起订量限制、发货周期等）。

### Step 2: 话术规划与生成 (Content Generation)

基于搜集到的信息，严格按照模板规范生成话术。
**核心规则（极度重要）**：
- **全英文输出**：生成的FAQ和销售技巧内容必须为英文（符合国际站买家习惯）。
- **标点符号限制**：内容中**绝对不能包含英文双引号 `"`**（如有引用需使用单引号 `''`，这是知识库系统的硬性要求）。
- **话术风格**：解答要专业且带有引导性，最好以反问句（如：Which method works best for you? / What is your target quantity?）结尾，促进客户持续互动。

**需要生成的内容清单**：
1. **买家常问FAQ (至少30个)**：涵盖工厂情况(Location/Factory tour)、支付方式(Payment)、起订量(MOQ)、样品政策(Sample)、交期(Lead time)、定制(OEM/ODM/Logo)、质检与售后(Quality Control/Warranty)、物流(Shipping)等全链路问题。
2. **销售技巧 (15-20个)**：涵盖典型抗拒点处理，如：运费太贵(Freight costs are high)、为什么用阿里(Why Alibaba/Trade Assurance)、价格太贵(Price is too high)、我们之前有固定的供应商(I have a regular supplier)、如何信任你们(Trust issues)等。

### Step 3: 文件导出 (Delivery)

生成内容后，必须将数据直接写入到符合国际站知识库要求的 `.xlsx` 模板文件中，方便用户直接上传。
请使用 bash 工具，编写一段 Python (pandas/openpyxl) 脚本，在当前工作目录下生成两个 Excel 文件：
1. `买家常问FAQ.xlsx`
2. `销售技巧.xlsx`

**Excel 格式要求（必须精准对应）**：
- **Row 1（说明行）**：
  - FAQ第一行：`填写说明：1. 请将内容填写在AB列，直接从第三行直接开始填写问题和答案，勿对1，2行做任何修改。2. 内容不能包含英文双引号。`
  - 销售技巧第一行：`填写说明：1. 请将内容填写在AB列，直接从第三行直接开始填写问题和答案，勿做其他修改。2. 内容不能包含英文双引号。`
- **Row 2（表头行）**：
  - A列：`index` (填写客户提问/异议)
  - B列：`content` (填写业务员回复话术)
- **Row 3 开始**：具体生成的数据。

### Step 4: 成果汇报

文件生成成功后，向用户简要汇报（中文），总结你提取到的核心优势，并给出两个 `.xlsx` 文件的相对路径供用户点击下载和上传至国际站AI知识库。

## Pitfalls

- **首行 YAML frontmatter 易错**：SKILL.md 文件第一行必须是 `---`，前面不能有任何字符、注释或空行，否则安装时将报错"缺少 YAML frontmatter"。
- **双引号禁用**：生成的 FAQ 和销售技巧内容中绝对不能包含英文双引号 `"`，这是国际站知识库系统的硬性要求，必须使用单引号替代。
- **语言一致性**：所有生成的话术必须为全英文，不要混入中文字段。
- **XLSX 模板精确**：Excel 文件的行结构和说明行内容必须严格匹配模板，Row 1 和 Row 2 不能做任何修改。
- **引导式结尾**：每段话术最好以反问句结尾（如 Which option suits your project best?），促进客户持续互动而不是结束对话。

## Verification

- [ ] 已获取到用户店铺/产品的核心信息（至少确认了1-2个核心卖点）
- [ ] 生成的 FAQ 数量 >= 30 个，覆盖工厂、支付、MOQ、样品、交期、定制、质检、物流等全链路
- [ ] 生成的销售技巧数量在 15-20 个之间，覆盖主流抗拒点
- [ ] 所有内容为全英文，不含英文双引号
- [ ] Excel 文件 Row 1-2 完全匹配模板要求
- [ ] 话术结尾具有引导性（反问句/开放性问题）

---

> 如有使用问题请反馈，好用欢迎给星星，skill 升级的最新版本会同步到 GitHub: [igocan-AI](https://github.com/igocan-AI)