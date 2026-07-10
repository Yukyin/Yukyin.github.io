---
title: "专问（ProAdvisor）：行业定制化AI专业顾问"
layout: single
permalink: /projects/proadvisor/
classes: wide product-page

author_profile: false
toc: false

---
<style>
/* =========================
   ProAdvisor page enhancements
   - VSCode-like left sidebar TOC (overlay, does NOT change content width)
   - Logo inline with the page title
   ========================= */
/* Wider content (text + images) */
.page__inner-wrap{ max-width: 1680px; }
.page__content{ max-width: 1560px; width: 100%; }
/* Reduce side padding a bit */
.page__content{ padding-left: 0.25rem; padding-right: 0.25rem; }

/* Figure captions */
.pa-caption, .pa-caption em{ color: #777; font-size: 0.85rem;}

/* Under numbered lists, force sub-bullets to be solid (●) */
.page__content ol ul{
  list-style-type: disc !important;
}


/* Title layout + logo */
h1.page__title, .page__title{
  display: flex;
  align-items: center;
  gap: 0px;
}
h1.page__title::before, .page__title::before{
  content: "";
  width: 110px;
  height: 110px;
  flex: 0 0 auto;
  background: url("{{ '/assets/proadvisor/zhuanwen-logo.png' | relative_url }}") no-repeat center / contain;
}

/* ----- VSCode-like floating TOC (overlay) ----- */
#pa-vsc-toc{
  position: fixed;
  left: 16px;
  top: 110px;            /* adjust if your top nav overlaps */
  z-index: 9999;
  font-family: inherit;
}

/* checkbox: CSS-only toggle */
#pa-vsc-toggle{ display:none; }

/* Handle (collapsed) */
#pa-vsc-handle{
  width: 44px;
  height: 44px;
  border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.12);
  background: rgba(255,255,255,0.98);
  box-shadow: 0 10px 22px rgba(0,0,0,0.10);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  user-select: none;
}
#pa-vsc-handle span{
  font-size: 18px;
  line-height: 1;
  color: #444;
}

/* Panel (expanded) */
#pa-vsc-panel{
  position: absolute;
  left: 0;
  top: 0;
  width: 280px;
  max-height: 70vh;
  overflow: auto;
  border-radius: 14px;
  border: 1px solid rgba(0,0,0,0.10);
  background: rgba(255,255,255,0.98);
  box-shadow: 0 14px 30px rgba(0,0,0,0.12);
  padding: 14px 14px 10px;
  display: none; /* default collapsed */
}

#pa-vsc-panel .pa-vsc-head{
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  margin-bottom: 8px;
}
#pa-vsc-panel .pa-vsc-title{
  font-weight: 800;
  font-size: 1.05rem;
  color: #333;
}
#pa-vsc-close{
  width: 28px;
  height: 28px;
  border-radius: 8px;
  border: 1px solid rgba(0,0,0,0.12);
  background: #fff;
  cursor: pointer;
  font-size: 16px;
  line-height: 28px;
  text-align: center;
  color: #444;
}

/* Links */
#pa-vsc-links a{
  display: block;
  padding: 4px 0;
  text-decoration: none;
  color: #444;
  font-size: .78rem;
}
#pa-vsc-links a:hover{
  text-decoration: underline;
}
#pa-vsc-links a.l3{
  padding-left: 12px;
  opacity: .92;
  font-size: .74rem;
}

/* Open state (CSS-only) */
#pa-vsc-toggle:checked + #pa-vsc-handle{ display: none; }
#pa-vsc-toggle:checked ~ #pa-vsc-panel{ display: block; }

/* Mobile: hide floating sidebar */
@media (max-width: 900px){
  #pa-vsc-toc{ display:none; }
}


/* Tighten space between the page title and the first paragraph/heading */
h1.page__title{
  margin-bottom: 0.35rem !important;   /* 缩小标题下方空白 */
}

/* If the English summary starts right after title as a paragraph */
.page__content > p:first-child{
  margin-top: 0.25rem !important;
}

/* If it starts as a heading instead (h2/h3) */
.page__content > h2:first-child,
.page__content > h3:first-child{
  margin-top: 0.45rem !important;
}

/* Subtle backgrounds (clean & investor-friendly) */

/* Summary block (your > ### Summary) */
.page__content blockquote{
  background: rgba(0,0,0,0.03);
  border-left: 4px solid rgba(0,0,0,0.10);
  padding: 0.85rem 1.0rem;
  border-radius: 14px;
}

/* Demo section background (wrap with a div, see below) */
.pa-demo-wrap{
  background: rgba(0,0,0,0.02);
  border: 1px solid rgba(0,0,0,0.06);
  border-radius: 16px;
  padding: 0.8rem 0.9rem;
  margin: 0.6rem 0 1.0rem;
}

/* Fix extra blank space inside grey blockquote */
.page__content blockquote p{
  margin: 0 !important;
}
.page__content blockquote{
  padding: 0.8rem 1.0rem !important;   /* 你也可以再调小一点 */
}

/* Remove extra top gap inside blockquote (Summary) */
.page__content blockquote > :first-child{
  margin-top: 0 !important;
}
.page__content blockquote > :last-child{
  margin-bottom: 0 !important;
}

.page__content .pa-caption{ margin-top:0.85rem !important; padding-top:0 !important; }
.page__content .pa-watchguide{ margin-top:0.95rem !important; padding-top:0 !important; }


/* Global line spacing for all text inside the content area */
.page__content{
  line-height: 1.9 !important;
}

/* Keep headings compact so they do not look too loose */
.page__content h1,
.page__content h2,
.page__content h3,
.page__content h4{
  line-height: 1.25 !important;
}




/* =========================
   spacing fix (tight + consistent)
   Keep line-height 1.9, but remove large vertical gaps before/inside lists.
   ========================= */
.page__content{
  line-height: 1.9 !important;
}

/* Paragraph margins: tighter to match list rhythm */
.page__content p{
  margin-top: 0 !important;
  margin-bottom: 0.55rem !important;
  line-height: 1.9 !important;
}

/* List block margins */
.page__content ul,
.page__content ol{
  margin-top: 0.15rem !important;
  margin-bottom: 0.55rem !important;
  padding-top: 0 !important;
  padding-bottom: 0 !important;
}

/* List items: remove "loose" spacing */
.page__content ul > li,
.page__content ol > li{
  margin: 0 !important;
  padding: 0 !important;
  line-height: 1.9 !important;
}
.page__content ul > li + li,
.page__content ol > li + li{
  margin-top: 0.15rem !important;
}

/* Most important: kill the extra paragraph margins inside list items */
.page__content li > p{
  margin: 0 !important;
  line-height: 1.9 !important;
}

/* Nested lists: tighter */
.page__content ul ul,
.page__content ol ol,
.page__content ul ol,
.page__content ol ul{
  margin-top: 0.10rem !important;
  margin-bottom: 0.10rem !important;
}

</style>


<!-- <div class="pa-top-title">
  <img src="/assets/proadvisor/zhuanwen-logo.png" alt="ProAdvisor logo" />
  <div class="t">ProAdvisor：行业定制化AI专业顾问</div>
</div> -->


> ### 📌 摘要
> 
> 专问是一款面向专家时间稀缺、决策高影响的专业咨询场景的行业定制化AI顾问。
> 
> - 首个落地场景为中国高客单医疗美容服务。
> - 规划中的拓展方向包括教育升学规划、法律合规咨询等专家密集型服务场景。
> 
> 在当前医疗美容场景下，专问支持两大核心流程：
> - 院外接待，AI前台在线接待客户，采集需求与关键约束条件，引导预约登记，并生成结构化沟通小结，用于向机构团队交接。
> - 院内顾问，顾问侧工具承接院外记录，引导照片与背景资料补充，起草结构化讨论要点，检索相关案例，并生成简洁的专家前置小结。


{::nomarkdown}
<div id="pa-vsc-toc" aria-label="Table of contents">
  <input id="pa-vsc-toggle" type="checkbox" />
  <label id="pa-vsc-handle" for="pa-vsc-toggle" title="打开目录" aria-label="Open TOC"><span>≡</span></label>

  <div id="pa-vsc-panel" role="navigation" aria-label="目录">
    <div class="pa-vsc-head">
      <div class="pa-vsc-title">目录</div>
      <label id="pa-vsc-close" for="pa-vsc-toggle" title="关闭目录" aria-label="Close">⟨</label>
    </div>

    <nav id="pa-vsc-links">
<a href="#sec-1-overview">🧩 1. 产品总览</a>
      <a class="l3" href="#sec-1-1-scale">1.1 行业可扩展性</a>

<a href="#sec-2-medical">🏥 2. 首个落地场景：医疗美容</a>
      <a class="l3" href="#sec-2-1-outclinic">2.1 院外版：智能接待台</a>
      <a class="l3" href="#sec-2-2-inclinic">2.2 院内版：资深顾问助手</a>
      <a class="l3" href="#sec-2-3-specialist">2.3 专家端：关键决策确认</a>

      <a href="#sec-3-demo">🎥 3. 场景展示</a>
      <a href="#sec-4-capabilities">✨ 4. 核心能力</a>
      <a class="l3" href="#sec-4-1-product">4.1 产品层面的价值</a>
      <a class="l3" href="#sec-4-2-org">4.2 机构层面的价值</a>
<a href="#sec-5-arch">⚙️ 5. 技术架构</a>

<a href="#sec-6-biz">📈 6. 商业运营</a>
      <a class="l3" href="#sec-6-1-target">6.1 目标客户</a>
      <a class="l3" href="#sec-6-2-model">6.2 商业模式</a>
      <a class="l3" href="#sec-6-3-growth">6.3 运营与增长打法</a>

<a href="#sec-7-roadmap">🧭 7. 未来方向</a>
      <a class="l3" href="#sec-7-1-product">7.1 产品路线</a>
      <a class="l3" href="#sec-7-2-scale">7.2 规模化路径</a>
      <a class="l3" href="#sec-7-3-eco">7.3 生态合作</a>

<a href="#sec-8-contact">✉️ 8. 联系方式</a>
    </nav>
  </div>
</div>
{:/nomarkdown}


## 🧩 1. 产品总览 {#sec-1-overview}

专问（ProAdvisor）是一款面向**专业服务**团队的**顾问**产品，由**流程引擎**驱动，将资深顾问的方法沉淀为：可配置的对话流程、可插拔的行业知识组件、合规与风险边界、以及专家交接与协同机制。它支持从用户接待到专家协同的全链路交付，并持续沉淀**可复用**的行业咨询资产。

它将咨询服务产品化为可交付的能力模块，沉淀为三类核心能力：
- **需求结构化**：将自然语言咨询转化为结构化需求画像，明确目标、约束与风险偏好，提升初筛效率与信息完整度。
- **方案生成与风险提示**：将需求画像与行业知识组件结合，输出结构化方案要点与风险提示，提升建议质量与沟通一致性。
- **专家交接与路由**：将对话上下文压缩为专家可直接使用的前置小结，完成专家路由与交接，释放专家时间并提升协作效率。


### 1.1 行业可扩展性 {#sec-1-1-scale}

专问的可扩展性来自两类标准化能力，将咨询服务沉淀为可在不同行业复用并规模化部署的产品形态。
- 行业模板包
  - 将咨询链条抽象为可配置的流程节点、话术与交付物规范
  - 帮助团队在接待、初筛、记录与流转中执行统一标准，持续沉淀可复用的行业资产
- 机构部署方案
  - 提供可配置的权限体系、审计留痕与风险边界能力
  - 支持从小规模试点到多门店、多业务线的统一部署，满足可追溯、可运营的管理要求

专问优先聚焦**专家时间稀缺、决策门槛高、合规要求强的咨询场景**，当前重点扩展方向为：
- 医疗美容
- 教育升学规划
- 法律合规咨询

💡 医疗美容已完成落地验证，形成可复制的行业模板包与部署方法，为后续在其他同类高客单咨询场景中的复制提供基础。


## 🏥 2. 首个落地场景：医疗美容 {#sec-2-medical}
当前版本围绕高客单咨询链条设计，覆盖从院外接待到院内承接再到专家面诊的闭环链路，目标是减少漏单与重复沟通、提升到院转化与跟进效率，并缩短专家决策时间。

<!-- 闭环链路：院外线上咨询 → 院内深度沟通 → 专家面诊与执行 -->
### 2.1 院外版：智能接待台 {#sec-2-1-outclinic}
院外版以客户自助为主，客服兜底介入。覆盖四个关键环节：
- 友好对话接待
  - 以友好对话完成欢迎与基础介绍
  - 统一服务口径，降低沟通门槛，提升信任感

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/outclinic-welcome-face.png"
      alt="院外版：欢迎与引导界面"
      style="width:65%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图1：欢迎与引导界面，完成对话式接待与基础信息介绍<br/>Fig 1: Welcome and guidance UI for conversational intake and basic introduction</em>
  </div>
</div>

- 诉求与约束条件结构化采集
  - 主诉与期望改善点
  - 预算范围
  - 恢复期与风险偏好
  - 既往相关史与注意事项

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/outclinic-intent-face1.png"
      alt="院外版：诉求与项目意向采集（一步）"
      style="width:65%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图2：多轮提问采集主诉、预算与关键约束条件，形成结构化信息<br/>Fig 2: Multi-turn intake to capture concerns, budget, and constraints in a structured profile</em>
  </div>
</div>

- 预约登记与建档
  - 确认到院时间区间与意向门店
  - 采集联系方式与沟通偏好
  - 生成预约意向与基础档案，便于持续跟进

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/outclinic-intent-face2.png"
      alt="院外版：预约登记与补充信息"
      style="width:65%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图3：预约登记与建档界面，记录到院时间、门店与联系方式等信息<br/>Fig 3: Booking and profiling UI capturing visit window, location, and contact details</em>
  </div>
</div>

- 自动生成初步沟通记录并流转
  - 结构化汇总关键信息与项目方向
  - 记录到诊意愿、时间窗口与联系方式
  - 一键推送至院内顾问工作台，支持后续深聊与转化

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/outclinic-summary-face.png"
      alt="院外版：自动生成初步沟通记录"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图4：自动生成初步沟通记录，用于院外到院内的接力沟通与跟进<br/>Fig 4: Auto-generated preliminary record for handoff and follow-up</em>
  </div>
</div>

> 院外版以客户自助完成接待、诉求采集与预约建档为主，人工客服仅在卡点时兜底介入。


### 2.2 院内版：资深顾问助手 {#sec-2-2-inclinic}

院外版依然以客户自助为主，人工顾问兜底介入。覆盖五个关键环节：

- 承接院外资料，从重点问题切入  
  - 自动接入院外沟通小结与预约信息，避免重复采集。  

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-console-face.png"
      alt="院内版：顾问工作台与院外记录承接"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图5：顾问工作台汇总院外沟通记录与预约信息，支持从关键问题切入<br/>Fig 5: Consultant workspace summarizes the out-of-clinic record and booking details for a focused start</em>
  </div>
</div>

- 引导补充资料，生成方案讨论要点  
  - 支持上传客户资料图片与补充信息，基于资料与主诉生成结构化讨论要点，便于解释方案与风险边界。 

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-plan-face.png"
      alt="院内版：照片上传与方案要点"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图6：上传资料后生成初步讨论要点，辅助院内沟通与解释<br/>Fig 6: After uploading materials, the system drafts structured talking points for consultation</em>
  </div>
</div>

- 展示相似案例，辅助预期管理  
  - 基于主诉与特征检索相似案例，支持对齐效果预期与可行范围，并便于说明差异点与风险提示。  

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-cases-face.png"
      alt="院内版：相似案例展示"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图7：基于主诉与特征检索相似案例，用于预期对齐<br/>Fig 7: Retrieve similar cases to support expectation alignment</em>
  </div>
</div>

- 生成专家前置小结  
  - 自动汇总用户关心点、已讨论方向、偏好与关键风险提示要点，输出结构化小结，减少信息遗漏，提升专家接诊效率。 

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-expert-face1.png"
      alt="院内版：专家前置小结"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图8：根据沟通内容自动生成专家前置小结，突出关键信息<br/>Fig 8: Auto-generate a pre-specialist brief highlighting the most critical information</em>
  </div>
</div>

- 专家对接与小结流转  
  - 顾问选择专家与科室后，将前置小结与预约信息一并流转，支持专家直接进入关键决策与面诊环节，减少重复问答与信息回溯。  

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-expert-face2.png"
      alt="院内版：对接专家与流转"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>图9：选择专家与科室并流转前置小结与预约信息<br/>Fig 9: Route the brief together with booking details to the right specialist</em>
  </div>
</div>

> 院内版以客户自助信息补全与材料提交为主，人工顾问仅在卡点时兜底介入。

### 2.3 专家端：关键决策确认 {#sec-2-3-specialist}

在当前设计中，专家端保持轻量接入，前置工作由顾问与系统协同完成：

- 顾问在院内沟通中补全关键信息，并完成初步解释与风险边界对齐
- 专问自动生成结构化专家前置小结，附带预约信息、关键约束与已讨论方向
- 专家面诊阶段聚焦于快速阅览小结，确认风险与偏好，完成方案精修与面诊执行

> 从专家视角，这意味着进入面诊环节的客户已完成关键前置信息收集与沟通，专家可把时间集中在关键决策与面诊执行。




## 🎥 3. 场景展示 {#sec-3-demo}

- 院外版（Out-of-clinic scenario）
<div style="margin:0.4rem 0 0.8rem;">
  <video id="demo-out" controls playsinline preload="metadata"
    style="display:block; width:65%; max-width:684px; margin:0 auto; border-radius:14px;">
    <source src="https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/zhuanwen-outclinic.fast.mp4" type="video/mp4">
    你的浏览器不支持视频播放。你也可以直接访问：https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/zhuanwen-outclinic.fast.mp4
  </video>
</div>

<div class="pa-watchguide" data-video="demo-out"
     style="max-width:684px; margin:0.55rem auto 0.55rem; font-size:.78rem; color:#444; line-height:1.8;">
  <span class="wg" data-t="0">0:00 友好对话接待</span>
  <span class="wg" data-t="31">0:31 诉求与约束采集</span>
  <span class="wg" data-t="108">1:48 预约登记与建档</span>
  <span class="wg" data-t="122">2:02 沟通记录与流转</span>
</div>

- 院内版（In-clinic scenario）
<div style="margin:0.35rem 0 0.8rem;">
  <video id="demo-in" controls playsinline preload="metadata"
    style="display:block; width:100%; max-width:980px; margin:0 auto; border-radius:14px;">
    <source src="https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/zhuanwen-inclinic.fast.mp4" type="video/mp4">
    你的浏览器不支持视频播放。你也可以直接访问：https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/zhuanwen-inclinic.fast.mp4
  </video>
</div>

<div class="pa-watchguide" data-video="demo-in"
     style="max-width:980px; margin:0.55rem auto 0.4rem; font-size:.78rem; color:#444; line-height:1.8;">
  <span class="wg" data-t="0">0:00 重点问题切入</span>
  <span class="wg" data-t="43">0:43 资料补充与要点</span>
  <span class="wg" data-t="98">1:38 相似案例展示</span>
  <span class="wg" data-t="114">1:54 专家前置小结</span>
  <span class="wg" data-t="156">2:36 对接与流转</span>
</div>

<script>
document.addEventListener("click", (e) => {
  const el = e.target.closest(".pa-watchguide .wg");
  if(!el) return;
  const wrap = el.closest(".pa-watchguide");
  const vid = document.getElementById(wrap.dataset.video);
  if(!vid) return;
  vid.currentTime = Number(el.dataset.t || 0);
  vid.play();
});
</script>

<style>
.pa-watchguide .wg{
  display:inline-block;
  margin:0 10px 6px 0;
  padding:2px 10px;
  border:1px solid rgba(0,0,0,.12);
  border-radius:999px;
  cursor:pointer;
  background:#fff;
  user-select:none;
}
.pa-watchguide .wg:hover{
  text-decoration: underline;
}
</style>



## ✨ 4. 核心能力 {#sec-4-capabilities}

从产品体验和机构运营两个角度，可概括为：

### 4.1 产品层面的价值 {#sec-4-1-product}
- 「会听」需求结构化：将用户的口语化、模糊表达转化为结构化需求要素与关键约束，降低漏采与误解风险。
- 「会说」一致口径的解释型输出：按问题澄清，原因解释，可选方案，风险边界，下一步行动组织回复，提升沟通效率与服务一致性，减少反复追问与误解。
- 「会转接」边界控制与低成本交接：对超出边界的问题主动收敛，明确需专家判断，并自动生成可直接使用的交接小结，降低专家接手成本。
- 「可扩展」多模态与结构化信息接入：在信息来源明确的场景下，可接入图像与结构化信息作为辅助材料，提升上下文完整度（用于沟通与预筛，不替代专业诊断）。

### 4.2 机构层面的价值 {#sec-4-2-org}
- 咨询流程标准化与可复制：将经验型服务沉淀为流程与话术模板，支持跨人员、跨门店的一致交付。
- 转化链路可控与可追溯：关键节点信息结构化留存，减少漏单与信息断层，便于运营跟进与质量管理。
- 释放一线与专家时间：减少重复采集与重复解释，让顾问与专家集中精力处理高价值沟通与关键决策。




## ⚙️ 5. 技术架构 {#sec-5-arch}

专问由**流程引擎**、**大模型**能力与**行业知识库**协同构成，面向可控的咨询交付流程。整体可拆为三层：
- 对话与流程引擎层 
  - 负责对话状态管理与阶段切换 
  - 控制提问、总结、解释、交接等关键节点的触发与顺序
  - 执行风险边界控制与升级策略，在需要时转交顾问与专家
- 大模型与表达层
  - 以通用大模型作为理解与生成基础
  - 通过提示工程与行业化适配，结合模板与检索，必要时进行轻量微调，确保输出结构化、可解释、可复用
  - 在表达清晰、风险边界与合规要求之间保持一致的生成策略
- 知识资产与机构配置层
  - 行业知识库：概念与服务项说明、适用条件与注意事项（或风险提示要点）等
  - 案例库：匿名化相似案例与对比材料，用于沟通与预期对齐
  - 机构配置：专家分工、科室与服务路径、可售服务项与预约规则等

此外，专问支持机构级权限体系、审计留痕与合规治理，便于规模化部署与运营管理。



## 📈 6. 商业运营 {#sec-6-biz}
### 6.1 目标客户 {#sec-6-1-target}
- 高客单与高决策的专业服务团队：咨询链条长，专家时间稀缺，服务质量依赖经验与话术。
- 连锁与集团型机构：强调服务一致性与合规边界，希望将咨询流程沉淀为可复用的行业资产，并支持跨门店复制。

### 6.2 商业模式 {#sec-6-2-model}
- 机构订阅：按门店规模与角色席位分层，支持从试点到规模化部署。
- 行业模板包交付：交付可配置流程模板与行业知识库组件，支持快速落地与复制。
- 增值模块：合规审计、数据看板、专家协同等能力按需开通。
- 主推组合：机构订阅与行业模板包为基础，增值模块按机构需求扩展。

### 6.3 运营与增长打法 {#sec-6-3-growth}
- 标杆机构试点：以试点验证闭环，沉淀可复用模板与交付方法。
- 标准化交付与培训体系：形成交付包与培训流程，缩短上线周期并降低交付成本。
- 渠道与生态联动：与渠道伙伴及行业组织联合获客与交付，形成稳定的获客与交付网络。



## 🧭 7. 未来方向 {#sec-7-roadmap}
### 7.1 产品路线 {#sec-7-1-product}
- 做深机构级可交付能力：支持从试点到多门店、多业务线的统一部署。
- 强化安全与合规体系：覆盖权限管理、审计留痕、风险边界与可追溯。
- 建设行业模板库与知识组件：提升复制速度，降低行业落地成本。

### 7.2 规模化路径 {#sec-7-2-scale}
- 以行业模板包与机构部署方案为核心资产，推动跨门店复制。
- 以服务一致性、交接效率与客户满意度为核心指标驱动扩张。
- 通过数据闭环持续迭代话术、流程与风险边界。

### 7.3 生态合作 {#sec-7-3-eco}
- 渠道伙伴与行业组织协同：形成获客与交付联动。
- 打通数据与工具链：构建可持续迭代的咨询运营闭环。



## ✉️ 8. 联系方式 {#sec-8-contact}
如果你是：
- 医疗美容机构或连锁专业服务团队，希望用 AI 提升咨询效率与服务一致性
- 关注 AI 驱动专业服务数字化的投资人
- 对垂直行业 AI 顾问产品与行业模板包合作感兴趣的伙伴

欢迎联系，交流产品进展与合作机会。

### 👤 创始人
专问由陈昱妍博士创立并主导研发。陈博士于复旦大学获得计算机博士学位，曾任美国康奈尔计算生物方向博士后研究员，长期聚焦大模型与AI4Health的技术创新与场景落地。相关成果发表于国际顶级会议与期刊，并获多项国家发明专利授权。现为ModelsLive Inc.创始人兼首席执行官。
- 公司主页：[modelslive.org](https://modelslive.org/)
- 邮箱：[contact@modelslive.org](mailto:contact@modelslive.org)
- 个人主页：[Yukyin.github.io](https://yukyin.github.io/)




