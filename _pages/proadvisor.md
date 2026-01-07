---
title: "ProAdvisor（专问）：AI 医美咨询顾问"
layout: single
permalink: /projects/proadvisor/
author_profile: false
toc: true
toc_sticky: true
toc_label: "目录"
classes: wide product-page
---

<style>
/* Page-local tweaks (safe to keep inside this markdown page) */
.product-page .page__title { display: none !important; }

.vv-hero{
  text-align: center;
  margin: 1.8rem 0 2.2rem;
}
.vv-logo{
  height: 84px;
  width: auto;
  display: inline-block;
}
.vv-name{
  font-size: 2.25rem;
  font-weight: 800;
  margin: .75rem 0 .35rem;
}
.vv-tagline{
  font-size: 1.05rem;
  opacity: .85;
}
</style>

<div class="vv-hero">
  <img class="vv-logo" src="/assets/proadvisor/logo.png" alt="ProAdvisor logo" />
  <div class="vv-name">ProAdvisor（专问）</div>
  <div class="vv-tagline">AI 医美咨询顾问</div>
</div>

> **English summary (for international visitors)**  
> ProAdvisor is a vertical-domain AI consultant for high-value medical aesthetics and dermatology services in China.  
> It currently has two main flows:  
> 
> - **Out-of-clinic concierge**: an AI front desk that talks to clients online, understands their needs and constraints, guides them through appointment booking, and generates a structured intake summary for the clinic.  
> - **In-clinic advisor**: a consultant-side tool that inherits all previous records, guides clients to upload photos, drafts a preliminary treatment plan, surfaces similar cases, and prepares a concise handover note for the specialist.  
>   The current demo, UI and training data are mainly in Chinese, focusing on real local consultation workflows.

---

## 1. 项目概述

**专问 ProAdvisor** 是一款面向垂直行业的专业顾问机器人，当前重点服务于**高客单医美 / 皮肤科机构**。

它不是一个简单的「聊天机器人」，而是把传统依赖资深咨询师的人力流程拆解成三件事：

1. **听得懂用户要什么**：从自然语言中抽取诉求、预算、时间预期、风险偏好等关键信息。  
2. **说得出像样的建议**：结合医美知识库与机构配置，给出结构化的初步方案与风险提示。  
3. **知道什么时候交给谁**：自动总结要点，并路由给院内资深顾问 / 合适的专家，节约他们的时间。

一句话：  

> 先替机构接住每一个潜在客户，再把真正棘手的问题交给合适的人类专家。

---

## 2. 医美场景与双版本设计

当前版本围绕一个典型路径设计：  
**院外线上咨询 → 院内深度沟通 → 专家面诊与执行**。

### 2.1 院外版：智能客服接待（Out-of-clinic Concierge）

**典型用户角色：**  

- 医美 / 皮肤科机构的客服、线上运营  
- 通过公众号、H5、小程序等入口触达的潜在客户

**它主要做四件事：**

1. **自然对话接待，而不是一上来就是表单**  
   
   - 用「像人一样说话」的方式欢迎用户  
   - 简单介绍机构能提供什么类型的服务  
   - 给用户一个安全感，而不是冷冰冰的机器人  

2. **结构化采集诉求与约束条件**  
   
   - 想改善什么（肤质 / 轮廓 / 抗衰 / 痘印…）  
   - 预算大概范围  
   - 能接受的恢复期 / 风险偏好  
   - 是否有基础疾病 / 既往治疗史等  
     对用户来说是聊天，对机构来说是**标准化 intake**。

| ![院外版：欢迎与引导界面](/assets/proadvisor/outclinic-welcome-face.png) | ![院外版：诉求与项目意向采集（一步）](/assets/proadvisor/outclinic-intent-face1.png) |
|:------------------------------------------------------------:|:------------------------------------------------------------------:|
| *图1：欢迎用户进入对话，展示轻松的问候与基础介绍，而不是冰冷的表单。*                         | *图2：通过多轮提问了解用户的主诉、预算和基本情况。*                                        |

3. **登记预约与建档**  
   
   - 在基本诉求明确之后，引导用户确认：  
     - 希望到院的时间区间  
     - 意向门店 / 医院  
     - 联系方式与沟通偏好（电话 / 微信等）  
   - 自动生成一条「预约意向 + 基础档案」，方便前台与运营跟进。

4. **自动生成《初步沟通记录》，用于后续流转**  
   
   - 把上面的关键信息整理成结构化小结：  
     - 基本诉求  
     - 可能适合的项目方向（不涉及具体医疗决策）  
     - 到诊意愿、时间窗口、联系方式  
   - 一键推送到院内顾问工作台，为下一步深聊做准备。

| ![院外版：预约登记与补充信息](/assets/proadvisor/outclinic-intent-face2.png) | ![院外版：自动生成初步沟通记录](/assets/proadvisor/outclinic-summary-face.png) |
|:--------------------------------------------------------------:|:---------------------------------------------------------------:|
| *图3：在完成诉求采集后，引导用户确认到院时间、门店与联系方式，完成预约登记与建档。*                    | *图4：对话结束后自动生成《初步沟通记录》，方便院内顾问接力沟通与跟进。*                           |

> 运营视角：院外版等于是一个**永不下线、统一话术的“线上前台 + 初筛顾问 + 预约登记助手”**。

---

### 2.2 院内版：资深顾问助手（In-clinic Advisor）

**典型用户角色：**  

- 已经在院内与用户面对面沟通的医美 / 皮肤科资深顾问

院内版连接的是**顾问日常工作流**：

1. **承接院外资料，从重点问题切入**  
   
   - 顾问打开某个客户时，系统自动展示：  
     - 院外客服阶段的沟通小结  
     - 用户的基础诉求、预算、时间窗口与预约信息  
   - 顾问可以直接从重点问题切入，而不是再做一遍问卷。
   
   ![院内版：顾问工作台与院外记录承接](/assets/proadvisor/inclinic-console-face.png)  
   *图1：顾问工作台汇总院外沟通记录与预约信息，直接从用户最在意的问题切入。*

2. **引导上传照片，结合知识库生成初步方案要点**  
   
   - 支持上传正脸 / 侧脸照片（院内使用，走院内局域网）  
   - 系统根据照片 + 主诉，生成结构化的「方案要点草稿」，例如：  
     - 重点关注区域  
     - 可选项目组合（不替代医生决策）  
     - 需要提前解释的风险点  
   - 顾问可以一边展示图片，一边用通俗话术和用户一起 review。
   
   ![院内版：照片上传与方案要点](/assets/proadvisor/inclinic-plan-face.png)  
   *图2：上传用户照片后，系统自动生成可与用户一起讨论的初步方案要点。*

3. **展示相似案例，帮助用户建立预期**  
   
   - 支持调出相似案例（同区域 / 同年龄段 / 类似预算）  
   - 给用户看「真实前后对比 + 基本参数」，帮助建立合理预期。
   
   ![院内版：相似案例展示](/assets/proadvisor/inclinic-cases-face.png)  
   *图3：根据主诉与特征调出相似案例，帮助用户建立更清晰的效果预期。*

4. **生成《专家前置小结》**  
   
   - 在沟通接近尾声时，系统自动整理：  
     - 用户关心点与主要诉求  
     - 已经讨论过的方案方向  
     - 用户表达过的担忧与偏好  
   - 形成一份给专家看的结构化小结，避免关键信息遗漏。
   
   ![院内版：专家前置小结](/assets/proadvisor/inclinic-expert-face1.png)  
   *图4：系统根据顾问与用户的沟通自动生成《专家前置小结》，突出关键信息。*

5. **对接专家并流转小结**  
   
   - 顾问在系统里选择合适的专家 / 科室  
   - 系统将《专家前置小结》与预约信息一起推送到专家端 / 医院内部系统  
   - 专家面诊时可以**直接在此基础上精修方案与执行**，无需再重复收集信息。
   
   ![院内版：对接专家与流转](/assets/proadvisor/inclinic-expert-face2.png)  
   *图5：在顾问端直接选择合适的专家 / 科室，将小结与预约信息一并流转。*

> 工作流视角：院内版让顾问从「重复讲基础」升级为「做真正需要经验与信任的沟通」，同时让专家把时间集中在决策与操作上。

---

### 2.3 专家端：只看到精炼的小结

在当前设计里，**专家不直接使用专问界面**，而是通过顾问与系统协同工作：

- 顾问与专问一起完成 80% 的信息收集与初步沟通  
- 专问帮助生成结构化的小结，并附带预约信息  
- 专家面诊时只需要：  
  - 快速过一遍小结  
  - 精修方案、解答关键疑问  
  - 进行操作和术后跟进方案设计

从专家视角，这意味着：  

> 每一位来到面诊室的顾客，都是**已经被充分沟通过的“高质量咨询”**。

---

## 3. 核心功能与特点（卖点）

从「产品体验」和「机构运营」两个角度，可以简单概括为：

### 3.1 产品层面的特点

- **会听：能听懂模糊、不完整的表达**  
  用户不会说「我需要中深层剥脱 + 抗炎方案」，只会说「皮肤粗糙暗沉，感觉显老」。  
  专问负责把这些**自然语言 → 需求要素**，避免漏信息。

- **会说：不是生硬回答，而是结构化解释**  
  
  - 不简单堆知识点，而是按「问题 → 解释 → 选择 → 风险提示 → 下一步」的结构回复  
  - 回复中融入一定的共情话术，让用户感觉被理解、被认真对待

- **会转接：知道自己该退到哪一步**  
  
  - 对超出边界的问题，专问不会硬答，而是明确说明需要医生 / 专家判断  
  - 同时帮忙整理用户关切点，降低专家接手成本

### 3.2 机构层面的价值

- **把咨询流程“标准化 + 可复制”**  
  不再完全依赖某几位资深咨询师的个人经验，而是沉淀为可复用的流程和话术。

- **提升高客单用户的转化率与体验**  
  高客单项目更需要前期充分沟通，专问可以让每一个有潜力的客户被认真对待和记录。

- **减轻一线坐席与顾问的重复性工作**  
  让人类顾问把时间花在真正需要经验和信任构建的环节上。

---

## 4. Demo 视频与录屏占位

你已经准备好了完整的录屏，这里可以预留位置，稍后替换为实际链接。

```markdown
### Demo 演示

- 🎥 院外版 Demo：  



<div style="margin: 0.75rem 0 1.25rem;">
  <div style="font-weight:700; margin: 0.25rem 0 0.5rem;">院外版 Demo</div>
  <video controls playsinline preload="metadata" style="width:100%; max-width: 980px; border-radius: 14px;">
    <source src="/assets/proadvisor/videos/outclinic-demo.mp4" type="video/mp4">
    你的浏览器不支持视频播放。你也可以直接访问：/assets/proadvisor/videos/outclinic-demo.mp4
  </video>
</div>


- 🎥 院内版 Demo：  




<div style="margin: 0.75rem 0 0.5rem;">
  <div style="font-weight:700; margin: 0.25rem 0 0.5rem;">院内版 Demo</div>
  <video controls playsinline preload="metadata" style="width:100%; max-width: 980px; border-radius: 14px;">
    <source src="/assets/proadvisor/videos/inclinic-demo.mp4" type="video/mp4">
    你的浏览器不支持视频播放。你也可以直接访问：/assets/proadvisor/videos/inclinic-demo.mp4
  </video>
</div>

## 5. 技术架构

在技术上，专问更像是一个**“流程引擎 + 大模型 + 行业知识库”的组合**，而不是单一的聊天模型。

可以简单拆成三层：

1. **对话与流程引擎（Conversation & Flow Engine）**  
   
   - 负责对话状态管理、阶段切换（院外 → 院内）  
   - 控制何时提问、何时总结、何时给出建议  
   - 决定什么时候需要「交给人类顾问 / 医生」

2. **大模型与定制化表达（LLM + Domain Adapters）**  
   
   - 使用通用大模型作为理解与生成基础  
   - 通过提示工程与定制化微调，让其适配医美场景  
   - 尽量在「解释清楚」与「不过度医疗化」之间取得平衡

3. **知识库与案例库（Knowledge & Case Base）**  
   
   - 医美项目说明、适应症 / 禁忌、术后护理要点  
   - 匿名化的相似案例与前后对比  
   - 机构内部的专家信息、科室分工、常见路径

> 当前线上展示的是 demo 版，高风险医疗决策仍由人类医生完成，专问聚焦在「沟通与信息整理」层面。

---

## 6. 商业化与运营思路

### 6.1 面向谁？

- 高客单医美 / 皮肤科机构  
- 有一定品牌和服务能力、希望提升咨询转化与用户体验的机构  
- 有意愿做流程标准化与数字化沉淀的连锁 / 集团

### 6.2 收费模式

> 以下为探索中的方向，实际合作可根据机构情况定制。

- **SaaS 订阅**  
  
  - 基础版：院外版 + 简单院内版（按门店/席位计价）  
  - 专业版：支持专家前置小结、自定义知识库接入  
  - 企业版：跨门店统一管理、数据看板等

- **定制项目**  
  
  - 对接医院现有 HIS / CRM / 小程序系统  
  - 深度共创咨询流程与知识库  
  - 以项目形式计费

- **API / 能力开放**  
  
  - 如果机构有自己的系统团队，可通过 API 方式接入专问能力  
  - 按调用量与功能模块分层计费

### 6.3 落地与运营节奏

- 先与 1–2 家典型机构做 POC：  
  - 小范围上线院外版和院内版  
  - 跟踪转化率、顾问满意度和用户反馈  
- 在此基础上继续打磨：  
  - 行业话术模板  
  - 风险提示边界  
  - 与专家端配合的最佳实践

---

## 7. 当前进展与下一步计划

**当前进展：**

- ✅ 完成院外版 / 院内版 Demo，并录制全流程演示  
- ✅ 跑通从「线上咨询 → 院内顾问 → 专家前置小结」的样例闭环  
- 🔄 正在根据真实对话，不断优化话术风格与流程细节

**下一步计划：**

- 寻找 1–2 家愿意一起共创的试点机构  
- 完善权限管理、日志与合规相关功能  
- 在医美 / 皮肤科场景成熟后，探索扩展到其他服务型行业（如教育、健康管理等）

---

## 8. 联系方式

如果你是：

- 🏥 医美 / 皮肤科机构，希望尝试用 AI 提升咨询效率与用户体验  
- 💼 关注「AI + 医疗服务 / 客户服务数字化」方向的投资人  
- 🤝 对垂直行业 AI 顾问产品感兴趣的合作伙伴

欢迎联系我，一起讨论可能性。

- 个人主页：<https://yukyin.github.io/>  
- 邮箱：<yolandachen0313@gmail.com>
