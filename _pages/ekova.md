---
title: "奕可（Ekova）：面向自我认识对话的人格支持智能体"
layout: single
permalink: /projects/ekova/
classes: wide product-page

author_profile: false
toc: false

---
<style>
/* =========================
   Ekova page enhancements
   - VSCode-like left sidebar TOC (overlay, does NOT change content width)
   - Logo inline with the page title
   ========================= */
/* Wider content (text + images) */
.page__inner-wrap{ max-width: 1680px; }
.page__content{ max-width: 1560px; width: 100%; }
/* Reduce side padding a bit */
.page__content{ padding-left: 0.25rem; padding-right: 0.25rem; }

/* Figure captions */
.ek-caption, .ek-caption em{ color: #777; font-size: 0.85rem;}

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
  background: url("{{ '/assets/ekova/ekova-logo.png' | relative_url }}") no-repeat center / contain;
}

/* ----- VSCode-like floating TOC (overlay) ----- */
#ek-vsc-toc{
  position: fixed;
  left: 16px;
  top: 110px;
  z-index: 9999;
  font-family: inherit;
}

/* checkbox: CSS-only toggle */
#ek-vsc-toggle{ display:none; }

/* Handle (collapsed) */
#ek-vsc-handle{
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
#ek-vsc-handle span{
  font-size: 18px;
  line-height: 1;
  color: #444;
}

/* Panel (expanded) */
#ek-vsc-panel{
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
  display: none;
}

#ek-vsc-panel .ek-vsc-head{
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  margin-bottom: 8px;
}
#ek-vsc-panel .ek-vsc-title{
  font-weight: 800;
  font-size: 1.05rem;
  color: #333;
}
#ek-vsc-close{
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
#ek-vsc-links a{
  display: block;
  padding: 4px 0;
  text-decoration: none;
  color: #444;
  font-size: .78rem;
}
#ek-vsc-links a:hover{
  text-decoration: underline;
}
#ek-vsc-links a.l3{
  padding-left: 12px;
  opacity: .92;
  font-size: .74rem;
}

/* Open state (CSS-only) */
#ek-vsc-toggle:checked + #ek-vsc-handle{ display: none; }
#ek-vsc-toggle:checked ~ #ek-vsc-panel{ display: block; }

/* Mobile: hide floating sidebar */
@media (max-width: 900px){
  #ek-vsc-toc{ display:none; }
}

/* Tighten space between title and first paragraph */
h1.page__title{
  margin-bottom: 0.35rem !important;
}
.page__content > p:first-child{
  margin-top: 0.25rem !important;
}
.page__content > h2:first-child,
.page__content > h3:first-child{
  margin-top: 0.45rem !important;
}

/* Summary block */
.page__content blockquote{
  background: rgba(0,0,0,0.03);
  border-left: 4px solid rgba(0,0,0,0.10);
  padding: 0.8rem 1.0rem !important;
  border-radius: 14px;
}
.page__content blockquote p{ margin: 0 !important; }
.page__content blockquote > :first-child{ margin-top: 0 !important; }
.page__content blockquote > :last-child{ margin-bottom: 0 !important; }

/* Global line spacing */
.page__content{
  line-height: 1.9 !important;
}
.page__content h1,
.page__content h2,
.page__content h3,
.page__content h4{
  line-height: 1.25 !important;
}
.page__content p{
  margin-top: 0 !important;
  margin-bottom: 0.55rem !important;
  line-height: 1.9 !important;
}
.page__content ul,
.page__content ol{
  margin-top: 0.15rem !important;
  margin-bottom: 0.55rem !important;
  padding-top: 0 !important;
  padding-bottom: 0 !important;
}
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
.page__content li > p{
  margin: 0 !important;
  line-height: 1.9 !important;
}
.page__content ul ul,
.page__content ol ol,
.page__content ul ol,
.page__content ol ul{
  margin-top: 0.10rem !important;
  margin-bottom: 0.10rem !important;
}

/* Persona color badges */
.ek-persona{
  display: inline-block;
  padding: 2px 10px;
  border-radius: 999px;
  font-size: 0.82rem;
  font-weight: 600;
  margin-right: 6px;
  margin-bottom: 4px;
}
.ek-coach{ background: #dce8fb; color: #2c5fa0; }
.ek-warm{ background: #fde9d8; color: #b85c10; }
.ek-tsuk{ background: #dff0d3; color: #3d7520; }
.ek-real{ background: #fdd8d8; color: #a01010; }
.ek-gonzo{ background: #ead8f5; color: #5a1e8a; }

</style>


> ### 📌 摘要
>
> 奕可是一款多模型 AI 陪伴产品，围绕一个核心理念构建：一个永远懂你的朋友。五个功能不同的支持人格随时适配当下场景，一个统一记忆层则将用户在所有会话与所有模式切换中分享过的一切延续下去。
>
> - 五个支持人格，Coach、Warm、Tsukkomi、Real、Gonzo，各自覆盖一种功能上无法互相替代的对话需求，从情感托底到结构化行动规划。
> - 动态路由实时选择最合适的模型与人格。无论后端运行的是哪一个模型，用户体验到的都是同一个连贯的陪伴者。
> - 说一次，处处懂你。人格切换、模型切换、新会话开启时，前序上下文都会跟随用户，无需重新自我介绍。


{::nomarkdown}
<div id="ek-vsc-toc" aria-label="Table of contents">
  <input id="ek-vsc-toggle" type="checkbox" />
  <label id="ek-vsc-handle" for="ek-vsc-toggle" title="Open table of contents" aria-label="Open TOC"><span>≡</span></label>

  <div id="ek-vsc-panel" role="navigation" aria-label="Table of contents">
    <div class="ek-vsc-head">
      <div class="ek-vsc-title">目录</div>
      <label id="ek-vsc-close" for="ek-vsc-toggle" title="Close table of contents" aria-label="Close">⟨</label>
    </div>

    <nav id="ek-vsc-links">
      <a href="#sec-1-overview">🧩 1. 产品总览</a>
      <a class="l3" href="#sec-1-1-positioning">1.1 现有模型的不足</a>
      <a class="l3" href="#sec-1-2-personas">1.2 五个人格</a>

      <a href="#sec-2-tech">⚙️ 2. 技术架构</a>
      <a class="l3" href="#sec-2-1-routing">2.1 上下文感知的模型路由</a>
      <a class="l3" href="#sec-2-2-buffer">2.2 过渡缓冲层</a>
      <a class="l3" href="#sec-2-3-memory">2.3 统一的跨会话记忆</a>

      <a href="#sec-3-demo">🎥 3. 界面展示</a>
      <a href="#sec-4-demo">🎬 4. 演示视频</a>

      <a href="#sec-5-capabilities">✨ 5. 核心能力</a>
      <a class="l3" href="#sec-5-1-user">5.1 用户价值</a>
      <a class="l3" href="#sec-5-2-diff">5.2 奕可的差异化</a>

      <a href="#sec-6-product">📱 6. 产品形态与访问</a>

      <a href="#sec-7-biz">📈 7. 商业模式</a>
      <a class="l3" href="#sec-7-1-target">7.1 目标用户</a>
      <a class="l3" href="#sec-7-2-pricing">7.2 定价与访问</a>
      <a class="l3" href="#sec-7-3-retention">7.3 留存机制</a>

      <a href="#sec-8-roadmap">🧭 8. 未来方向</a>

      <a href="#sec-9-contact">✉️ 9. 联系方式</a>
    </nav>
  </div>
</div>
{:/nomarkdown}


## 🧩 1. 产品总览 {#sec-1-overview}

奕可是一款**多模型 AI 陪伴产品**，为用户提供一个由当下最好的底座模型共同支撑的连贯朋友。它将每一个对话时刻路由到最合适的模型与人格组合，不依赖静态配置，而是实时读取真实上下文。在单一界面之下，奕可将 GPT、Claude、Gemini、DeepSeek 及其他成熟模型作为可替换后端运行，同时对用户仅呈现一个连续的身份。

产品的核心承诺很简单：说一次，处处懂你。统一记忆层存储用户在所有会话和所有人格模式下透露过的一切。当路由引擎从一个人格或后端切换到另一个时，会将全部历史一并延续。用户永远无需重新自我介绍。

奕可的人格系统建立在研究之上：五个功能不同的支持人格，每一个都做着其他人格无法完全替代的事情。目标不是让用户当下感觉更好，而是帮助他们随着时间更好地理解自己。

### 1.1 现有模型的不足 {#sec-1-1-positioning}

每一个主流底座模型作为陪伴者都有其特征性的盲区：

- **Gemini**：过度戏剧化，将小问题渲染为世界末日般的危机
- **DeepSeek**：过度母性化，条件反射地回应你辛苦了这么久，在很多语境下让人感到被居高临下地对待
- **GPT**：纯工具没有温度，像在跟客服机器人说话
- **Claude**：强迫性拉回，总是试图把对话拉回到某个所谓的主线话题
- **所有模型**：长会话下人格一致性衰减，每一次模型切换都从零开始，没有共享记忆

奕可通过路由、缓冲和记忆解决所有这些问题，而不是押注单一模型。

### 1.2 五个人格 {#sec-1-2-personas}

每一个人格都是建立在人格支持框架之上的最小功能单元。任何两个都不可互相替代：去掉其中任何一个，都会严格降低系统在全体用户群体中推进认知清晰的能力。

<span class="ek-persona ek-warm">Warm</span> 通过情感验证与稳定托底降低自我披露的阻力，在任何追问之前先创造出被听见而非被审问的空间。

<span class="ek-persona ek-tsuk">Tsukkomi</span> 通过反讽消解防御性叙事，用幽默侧向偏移触发认知重构，而不进行正面对抗。

<span class="ek-persona ek-real">Real</span> 将事实与自我归因剥离开，通过约束分析与因果结构重新框定情境，不弱化现实检查的力度。

<span class="ek-persona ek-gonzo">Gonzo</span> 通过跨域类比建立疏离视角，用高维隐喻重新语境化，让用户从结构性完全不同的角度看待自己的处境。

<span class="ek-persona ek-coach">Coach</span> 将洞察结晶为具体的行动方案，梳理变量、路由选项，并以走向问题澄清与解决的具体步骤收尾。


## ⚙️ 2. 技术架构 {#sec-2-tech}

### 2.1 上下文感知的模型路由 {#sec-2-1-routing}

路由是动态的，不是静态的权重分配。系统首先以中性的应答接住用户，再轻度探询上下文，然后才做出路由决策。一旦情境明朗，就为当下选择最合适的人格与后端模型。先探询后路由，比从第一条消息直接推断要准确得多。

### 2.2 过渡缓冲层 {#sec-2-2-buffer}

大幅度的人格跳转，例如从 Warm 直接跳到 Coach，对用户来说像人格移植。奕可使用一层 GPT 缓冲层来桥接风格差距较大的过渡：Warm 经过一到两轮 GPT 缓冲，再切换到 Coach 或 Gonzo，而不是直接切换。这样即便模式变化，用户依然感受到的是一个连续的陪伴者。

### 2.3 统一的跨会话记忆 {#sec-2-3-memory}

全部对话历史存储在平台方拥有的中央数据库中。每一次模型调用，不论选择的是哪个后端，都会将相关的前序上下文作为提示词的一部分接收。用户披露的信息在互动中不断积累：分享越多，奕可就能越精准地路由、回应与个性化，随着时间推移复利式地增进自我认识。

这样的设计让记忆成为核心留存机制。用户积累的上下文越多，切换到任何从零开始的替代方案的迁移成本就越高。




## 🎥 3. 界面展示 {#sec-3-demo}

- 默认模式：奕可根据用户当下的输入，自动选择最合适的支持人格并路由到对应的后端，在多次会话中保持连贯的互动身份。

<div style="text-align:center; margin: 0.55rem 0 0.9rem;">
  <img src="/assets/ekova/ekova-interface.png"
      alt="Ekova main interface, adaptive routing across five personas"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="ek-caption" style="margin-top:0.35rem;">
    <em>图1：奕可的自适应路由界面。系统选择了一个支持人格，此处为 Gonzo，通过一个机器学习类比重新语境化用户在工作场景中的挫败感。</em>
  </div>
</div>

- 个性化模式：用户可以手动选择某一个具体人格，或组合偏好的多个人格，在所选择的每一种支持风格下同时获得参考回应。

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/ekova/five-interface.png"
      alt="Ekova persona selection interface, all five personas"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="ek-caption" style="margin-top:0.35rem;">
    <em>图2：自定义人格选择界面。用户选择一种支持风格并查看对应的参考回应。同一段关于外卖失败的用户输入产生五种结构上完全不同的回应：情感托底 Warm，反讽疏离 Tsukkomi，事实重构 Real，通过付费 DLC 的类比进行的类比重构 Gonzo，以及一份三步走的解决方案 Coach。</em>
  </div>
</div>


## 🎬 4. 演示视频 {#sec-4-demo}

奕可以单一陪伴者的形态出现，其声音会根据你的选择而变化。在默认模式下，系统自动选取最契合你输入的人格。在自定义模式下，你选择要融合哪些人格，奕可将它们综合为一段统一的回应。演示中使用确定性输出，以确保跨会话的回答保持一致与稳定。

<div style="margin:0.4rem 0 0.8rem;">
  <video id="demo-ekova" controls playsinline preload="metadata"
    style="display:block; width:100%; margin:0 auto; border-radius:14px;">
    <source src="https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/ekova-demo.fast.mp4" type="video/mp4">
    你的浏览器不支持视频播放。你也可以直接访问：https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/ekova-demo.fast.mp4
  </video>
</div>

<div class="pa-watchguide" data-video="demo-ekova"
     style="margin:0.55rem auto 0.9rem; font-size:.78rem; color:#444; line-height:1.8;">
  <span class="wg" data-t="0">0:00 默认模式：自动人格选择</span>
  <span class="wg" data-t="27">0:27 自定义模式：选择一个人格</span>
  <span class="wg" data-t="33">0:33 自定义模式：三个人格融合</span>
  <span class="wg" data-t="52">0:52 自定义模式：四个人格融合</span>
  <span class="wg" data-t="76">1:16 自定义模式：五个人格全部融合</span>
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




## ✨ 5. 核心能力 {#sec-5-capabilities}

### 5.1 用户价值 {#sec-5-1-user}

- **连贯性**：统一记忆层意味着用户无需重复解释自己的情境。人格切换、模型切换、新会话开启时，前序上下文都会延续下来。
- **多样性**：一个界面，五种功能上完全不同的对话模式。用户获得的是当下真正需要的东西，而非每次都同一种口味。
- **随时间加深**：自我认识可以复利累积。用户披露得越多，奕可就能对他们的模式、约束与反复出现的情境建立越准确的模型，每一次会话都在提升路由精度与回应相关性。
- **拒绝强制正向**：当认知清晰需要挑战、重构、点破或反推时，奕可就会去做，而不是一味肯定。五个人格覆盖从情感托底到硬结构对质的完整范围。

### 5.2 奕可的差异化 {#sec-5-2-diff}

大多数 AI 陪伴产品要求用户选定一种工具并一直用它。奕可反过来做：合适的支持风格根据对话真正需要什么，主动来到用户面前。当模式发生切换时，缓冲层负责处理过渡，让体验顺滑而非突兀。而因为记忆层在所有人格与所有后端之间是统一的，用户永远不必背负重述上下文的负担。用得越多，奕可就越理解他们，他们要说的也就越少。


## 📱 6. 产品形态与访问 {#sec-6-product}

- **Web 优先**：通过移动浏览器访问，无需下载 app。这避免了应用商店审核约束，加速迭代。
- **语音输入支持**：适配移动端使用习惯的语音转文字输入。
- **人工邀请注册**：早期访问采用邀请制。用户账号逐个开通，以保持质量并收集结构化反馈。
- **语言**：主界面为简体中文，服务中国大陆及海外华人用户。
- **命名设计**：奕可为中性名，适用于所有用户，无人群定向。


## 📈 7. 商业模式 {#sec-7-biz}

### 7.1 目标用户 {#sec-7-1-target}

- 已经付费购买 GPT Plus、Claude Pro、Gemini Advanced 却仍然要在它们之间手动切换的重度多模型用户
- 有真实情感陪伴需求，但对任何单一模型的固定人格都不满意的用户
- 熟悉 API key 管理的技术型用户，早期为 BYOK 模式
- 全球中文用户：中国大陆、香港、台湾以及海外华人社区

### 7.2 定价与访问 {#sec-7-2-pricing}

早期访问对前 20 轮对话免费，让用户第一手体验记忆带来的价值。付费访问目前通过直接联系创始人获得。长期来看，奕可将通过 ModelsLive Inc. 提供公开订阅。API 成本与平台服务费透明分离。

### 7.3 留存机制 {#sec-7-3-retention}

记忆是主要的留存驱动力。用户积累的上下文越多，迁移到任何从零开始的替代产品的成本就越高。产品目标是在用户使用的第一周内，交付一个明确的系统记得我说过什么的时刻。这是将免费用户转化为付费订阅者最可靠的触发点。


## 🧭 8. 未来方向 {#sec-8-roadmap}

- **多语言扩展**：当前系统以中文为原生语言。英语和多语言支持是规划中的扩展，取决于数据集扩展与跨文化对话规范下的人格适配。
- **记忆管理界面**：让用户可以看到并控制自己积累的上下文，包括哪些被存储、哪些可以编辑或删除。
- **人格组合模式**：允许用户为反复出现的特定使用场景配置融合人格，例如 Warm 加 Coach 用于职业对话，Real 加 Gonzo 用于创作瓶颈。
- **跨会话评测基准**：开发适用于持久化智能体评估的指标体系。当前 NLP 基准都是单轮的，无法捕捉定义奕可核心价值的、复利累积的自我认识轨迹。
- **ModelsLive 平台集成**：将奕可的记忆与路由层与专问、言值引擎连接到统一的 ModelsLive API 之下，实现跨产品共享用户上下文。


## ✉️ 9. 联系方式 {#sec-9-contact}

如果你是：
- 在多个 AI 工具之间切换、想要一个真正记得你的中文用户
- 关注 AI 陪伴、多智能体路由或中文 AI 产品的投资人
- 对人格支持系统、持久化记忆智能体或多人格对话感兴趣的研究者或合作者

欢迎联系，交流产品进展与合作机会。

### 👤 创始人
奕可是 ModelsLive Inc. 的旗舰产品之一，由陈昱妍博士创立并主导研发。陈博士于复旦大学获得计算机博士学位，曾任美国康奈尔计算生物方向博士后研究员，长期聚焦大模型与 AI4Health 的技术创新与场景落地。相关成果发表于国际顶级会议与期刊，并获多项国家发明专利授权。现为 ModelsLive Inc. 创始人兼首席执行官。
- 公司主页：[modelslive.org](https://modelslive.org/)
- 邮箱：[contact@modelslive.org](mailto:contact@modelslive.org)
- 个人主页：[yukyin.github.io](https://yukyin.github.io/)
