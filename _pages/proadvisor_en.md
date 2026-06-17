---
title: "ProAdvisor: Industry-Customizable AI Professional Consultant"
layout: single
permalink: /projects/proadvisor-en/
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
  margin-bottom: 0.35rem !important;   /* reduce blank space under the title */
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
  padding: 0.8rem 1.0rem !important;   /* you can tune this smaller if you want */
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
  <div class="t">ProAdvisor: Industry-Customizable AI Professional Consultant</div>
</div> -->


> ### 📌 Summary
> 
> ProAdvisor is an industry-customizable AI consultant for professional advisory workflows where specialist time is scarce and decisions are high-impact.
> 
> - Pilot deployment: high-value medical aesthetics services in China.  
> - Planned verticals: education advising, legal triage, and other expert-heavy service workflows worldwide.
> 
> In the current medical aesthetics scenario, ProAdvisor supports two core flows:
> - Out-of-clinic concierge: an AI front desk that engages clients online, captures needs and key constraints, guides appointment booking, and produces a structured intake summary for handoff to the clinic team.
> - In-clinic advisor: a consultant-side tool that inherits prior records, guides photo and context collection, drafts structured discussion points, surfaces relevant cases, and generates a concise pre-specialist brief.


{::nomarkdown}
<div id="pa-vsc-toc" aria-label="Table of contents">
  <input id="pa-vsc-toggle" type="checkbox" />
  <label id="pa-vsc-handle" for="pa-vsc-toggle" title="Open table of contents" aria-label="Open TOC"><span>≡</span></label>

  <div id="pa-vsc-panel" role="navigation" aria-label="Table of contents">
    <div class="pa-vsc-head">
      <div class="pa-vsc-title">Table of contents</div>
      <label id="pa-vsc-close" for="pa-vsc-toggle" title="Close table of contents" aria-label="Close">⟨</label>
    </div>

    <nav id="pa-vsc-links">
<a href="#sec-1-overview">🧩 1. Product overview</a>
      <a class="l3" href="#sec-1-1-scale">1.1 Industry scalability</a>

<a href="#sec-2-medical">🏥 2. First deployed scenario: medical aesthetics</a>
      <a class="l3" href="#sec-2-1-outclinic">2.1 Out-of-clinic: intelligent reception desk</a>
      <a class="l3" href="#sec-2-2-inclinic">2.2 In-clinic: senior consultant assistant</a>
      <a class="l3" href="#sec-2-3-specialist">2.3 Specialist side: key decision confirmation</a>

      <a href="#sec-3-demo">🎥 3. Scenario showcase</a>
      <a href="#sec-4-capabilities">✨ 4. Core capabilities</a>
      <a class="l3" href="#sec-4-1-product">4.1 Value at the product level</a>
      <a class="l3" href="#sec-4-2-org">4.2 Value at the organization level</a>
<a href="#sec-5-arch">⚙️ 5. Technical architecture</a>

<a href="#sec-6-biz">📈 6. Commercial operations</a>
      <a class="l3" href="#sec-6-1-target">6.1 Target customers</a>
      <a class="l3" href="#sec-6-2-model">6.2 Business model</a>
      <a class="l3" href="#sec-6-3-growth">6.3 Operations and growth playbook</a>

<a href="#sec-7-roadmap">🧭 7. Future directions</a>
      <a class="l3" href="#sec-7-1-product">7.1 Product roadmap</a>
      <a class="l3" href="#sec-7-2-scale">7.2 Scaling path</a>
      <a class="l3" href="#sec-7-3-eco">7.3 Ecosystem partnerships</a>

<a href="#sec-8-contact">✉️ 8. Contact</a>
    </nav>
  </div>
</div>
{:/nomarkdown}


## 🧩 1. Product overview {#sec-1-overview}

ProAdvisor is a **consultant** product for **professional services** teams. Driven by a **workflow engine**, it distills senior consultants’ methods into configurable dialogue flows, plug-and-play industry knowledge components, compliance and risk boundaries, and expert handoff and collaboration mechanisms. It supports end-to-end delivery from client reception to specialist collaboration, continuously accumulating **reusable** advisory assets.

It productizes advisory services into deliverable capability modules and crystallizes them into three core capabilities:
- **Structured needs capture**: transforms natural-language consultations into a structured requirement profile, clarifying goals, constraints, and risk preferences to improve triage efficiency and information completeness.
- **Plan drafting and risk prompting**: combines the requirement profile with industry knowledge components to output structured plan talking points and risk prompts, improving recommendation quality and communication consistency.
- **Expert handoff and routing**: compresses the dialogue context into a specialist-ready pre-brief, completing routing and handoff, freeing specialist time and improving collaboration efficiency.


### 1.1 Industry scalability {#sec-1-1-scale}

ProAdvisor scales via two standardized capability sets that make advisory services reusable across industries and deployable at scale.
- Industry template packs
  - Abstract the advisory chain into configurable workflow nodes, scripts, and deliverable specifications
  - Help teams execute a unified standard across reception, triage, recordkeeping, and routing, continuously accumulating reusable industry assets
- Organization deploymentplan
  - Provide configurable permission systems, audit trails, and risk-boundary controls
  - Support unified deployment from small pilots to multi-branch and multi-business-line rollouts, meeting traceable and operable management requirements

ProAdvisor prioritizes advisory scenarios where **specialist time is scarce, decision thresholds are high, and compliance requirements are strong**. Current focus verticals include:
- Medical aesthetics
- Education planning and advising
- Legal compliance consulting

💡 Medical aesthetics has completed deployment validation, forming a replicable industry template pack and deployment playbook, providing a foundation for replication into other high-ticket advisory scenarios.


## 🏥 2. First deployed scenario: medical aesthetics {#sec-2-medical}
The current version is designed around high-ticket advisory chains, covering a closed-loop pipeline from out-of-clinic reception to in-clinic continuation and then specialist consultation. The goals are to reduce missed leads and repetitive communication, improve conversion and follow-up efficiency, and shorten specialist decision time.

<!-- Closed loop: out-of-clinic online consult → in-clinic deep discussion → specialist consult and execution -->
### 2.1 Out-of-clinic: intelligent reception desk {#sec-2-1-outclinic}
The out-of-clinic version is primarily self-service, with human customer service stepping in as a fallback. It covers four key stages:
- Friendly conversational reception
  - Welcome and basic introduction via a friendly dialogue
  - Unify service messaging, reduce communication barriers, and improve trust

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/outclinic-welcome-face.png"
      alt="Out-of-clinic: welcome and guidance UI"
      style="width:65%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 1: Welcome and guidance UI for conversational intake and basic introduction</em>
  </div>
</div>

- Structured collection of requests and constraints
  - Primary concern and desired improvements
  - Budget range
  - Recovery window and risk preference
  - Relevant history and precautions

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/outclinic-intent-face1.png"
      alt="Out-of-clinic: collecting requests and service intent (step 1)"
      style="width:65%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 2: Multi-turn intake to capture concerns, budget, and constraints in a structured profile</em>
  </div>
</div>

- Appointment registration and profiling
  - Confirm the visit time window and preferred location
  - Collect contact details and communication preferences
  - Generate appointment intent and a basic profile for ongoing follow-up

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/outclinic-intent-face2.png"
      alt="Out-of-clinic: appointment registration and additional info"
      style="width:65%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 3: Booking and profiling UI capturing visit window, location, and contact details</em>
  </div>
</div>

- Auto-generate a preliminary communication record and route it forward
  - Summarize key information and the likely service direction in a structured form
  - Record visit intent, time window, and contact details
  - One-click push to the in-clinic consultant workspace for deeper discussion and conversion

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/outclinic-summary-face.png"
      alt="Out-of-clinic: auto-generated preliminary communication record"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 4: Auto-generated preliminary record for handoff and follow-up</em>
  </div>
</div>

> The out-of-clinic version primarily relies on client self-service for reception, request capture, and booking/profiling, while human customer service only intervenes as a fallback at sticking points.


### 2.2 In-clinic: senior consultant assistant {#sec-2-2-inclinic}

The in-clinic version is still primarily self-service, with human consultants stepping in as a fallback. It covers five key stages:

- Inherit out-of-clinic materials and start from the key questions  
  - Automatically ingest the out-of-clinic summary and booking information to avoid duplicate collection.  

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-console-face.png"
      alt="In-clinic: consultant workspace and out-of-clinic record handoff"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 5: Consultant workspace summarizes the out-of-clinic record and booking details for a focused start</em>
  </div>
</div>

- Guide supplementary materials and generate plan discussion talking points  
  - Support uploading client photos and additional context; generate structured talking points based on materials and concerns to help explain plans and risk boundaries. 

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-plan-face.png"
      alt="In-clinic: photo upload and plan talking points"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 6: After uploading materials, the system drafts structured talking points for consultation</em>
  </div>
</div>

- Show similar cases to support expectation management  
  - Retrieve similar cases based on concerns and features to align effect expectations and feasible scope, and to explain differences and risk prompts.  

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-cases-face.png"
      alt="In-clinic: similar case display"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 7: Retrieve similar cases to support expectation alignment</em>
  </div>
</div>

- Generate a pre-specialist brief  
  - Automatically summarize user concerns, discussed directions, preferences, and key risk prompts in a structured brief to reduce omissions and improve specialist intake efficiency. 

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-expert-face1.png"
      alt="In-clinic: pre-specialist brief"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 8: Auto-generate a pre-specialist brief highlighting the most critical information</em>
  </div>
</div>

- Specialist matching and brief routing  
  - After selecting the specialist and department, route the brief together with booking information so the specialist can move directly to key decision-making and consultation execution, reducing repetitive Q&A and context backtracking.  

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/proadvisor/inclinic-expert-face2.png"
      alt="In-clinic: specialist routing and handoff"
      style="width:100%; height:auto; display:inline-block;" />
  <div class="pa-caption" style="margin-top:0.35rem;">
    <em>Fig 9: Route the brief together with booking details to the right specialist</em>
  </div>
</div>

> The in-clinic version primarily relies on client self-service for information completion and material submission, while human consultants only intervene as a fallback at sticking points.

### 2.3 Specialist side: key decision confirmation {#sec-2-3-specialist}

In the current design, the specialist side remains lightweight, while the preparatory work is completed jointly by the consultant and the system:

- The consultant completes key information during in-clinic discussion and aligns initial explanations and risk boundaries
- ProAdvisor automatically generates a structured pre-specialist brief with booking information, key constraints, and discussed directions
- During the specialist consultation, the specialist focuses on quickly reviewing the brief, confirming risks and preferences, and finalizing the plan and executing the consult

> From the specialist perspective, this means clients entering the consultation stage have already completed key upfront information capture and communication, allowing the specialist to focus time on key decisions and execution.




## 🎥 3. Scenario showcase {#sec-3-demo}

- Out-of-clinic scenario
<div style="margin:0.4rem 0 0.8rem;">
  <video id="demo-out" controls playsinline preload="metadata"
    style="display:block; width:65%; max-width:684px; margin:0 auto; border-radius:14px;">
    <source src="https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/zhuanwen-outclinic.fast.mp4" type="video/mp4">
    Your browser does not support video playback. You can also directly visit: https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/zhuanwen-outclinic.fast.mp4
  </video>
</div>

<div class="pa-watchguide" data-video="demo-out"
     style="max-width:684px; margin:0.55rem auto 0.55rem; font-size:.78rem; color:#444; line-height:1.8;">
  <span class="wg" data-t="0">0:00 Friendly conversational reception</span>
  <span class="wg" data-t="31">0:31 Requests and constraints intake</span>
  <span class="wg" data-t="108">1:48 Booking registration and profiling</span>
  <span class="wg" data-t="122">2:02 Record generation and routing</span>
</div>

- In-clinic scenario
<div style="margin:0.35rem 0 0.8rem;">
  <video id="demo-in" controls playsinline preload="metadata"
    style="display:block; width:100%; max-width:980px; margin:0 auto; border-radius:14px;">
    <source src="https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/zhuanwen-inclinic.fast.mp4" type="video/mp4">
    Your browser does not support video playback. You can also directly visit: https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/zhuanwen-inclinic.fast.mp4
  </video>
</div>

<div class="pa-watchguide" data-video="demo-in"
     style="max-width:980px; margin:0.55rem auto 0.4rem; font-size:.78rem; color:#444; line-height:1.8;">
  <span class="wg" data-t="0">0:00 Start from key questions</span>
  <span class="wg" data-t="43">0:43 Material completion and talking points</span>
  <span class="wg" data-t="98">1:38 Similar case display</span>
  <span class="wg" data-t="114">1:54 Pre-specialist brief</span>
  <span class="wg" data-t="156">2:36 Matching and routing</span>
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



## ✨ 4. Core capabilities {#sec-4-capabilities}

From both product experience and organizational operations perspectives:

### 4.1 Value at the product level {#sec-4-1-product}
- “Listens”: structured needs capture converts colloquial and ambiguous user expressions into structured requirement elements and key constraints, reducing the risk of missed information and misunderstandings.
- “Explains”: consistent, explanatory outputs organize replies by question clarification, reason explanation, optional plans, risk boundaries, and next actions, improving communication efficiency and service consistency while reducing repeated questioning and misunderstandings.
- “Hands off”: boundary control and low-cost handoff proactively narrows questions that exceed boundaries, makes specialist judgment explicit, and auto-generates a ready-to-use handoff brief, reducing specialist takeover cost.
- “Scales”: multimodal and structured inputs can be incorporated as supporting materials when information sources are clear, improving context completeness (for communication and pre-triage, not as a replacement for professional diagnosis).

### 4.2 Value at the organization level {#sec-4-2-org}
- Standardized and replicable advisory flows: distill experience-based service into workflow and script templates, enabling consistent delivery across staff and branches.
- Controllable and traceable conversion pipeline: preserve structured information at key nodes, reducing dropped leads and information gaps, supporting operations follow-up and quality management.
- Free frontline and specialist time: reduce repeated collection and repeated explanation so consultants and specialists can focus on high-value communication and key decisions.




## ⚙️ 5. Technical architecture {#sec-5-arch}

ProAdvisor consists of a **workflow engine**, **LLM** capabilities, and an **industry knowledge base**, designed for controllable advisory delivery processes. It can be decomposed into three layers:
- Dialogue and workflow engine layer 
  - Manages dialogue state and stage transitions 
  - Controls the triggering and ordering of key nodes such as questioning, summarization, explanation, and handoff
  - Enforces risk-boundary control and escalation strategies, handing over to consultants and specialists when needed
- LLM and expression layer
  - Uses a general-purpose LLM as the foundation for understanding and generation
  - Through prompt engineering and vertical adaptation, combined with templates and retrieval, and lightweight fine-tuning when necessary, ensures outputs are structured, explainable, and reusable
  - Maintains a consistent generation strategy across clarity of expression, risk boundaries, and compliance requirements
- Knowledge assets and organization configuration layer
  - Industry knowledge base: concept and service-item explanations, applicability conditions, and precautions (or key risk prompts), etc.
  - Case library: anonymized similar cases and comparison materials for communication and expectation alignment
  - Organization configuration: specialist roles, departments and service paths, sellable service items and booking rules, etc.

In addition, ProAdvisor supports organization-level permissions, audit trails, and compliance governance for scalable deployment and operational management.



## 📈 6. Commercial operations {#sec-6-biz}
### 6.1 Target customers {#sec-6-1-target}
- Professional service teams with high-ticket and high-stakes decisions: long advisory chains, scarce specialist time, and service quality dependent on experience and scripts.
- Chain or group organizations: emphasize service consistency and compliance boundaries, aiming to distill advisory workflows into reusable industry assets and replicate them across branches.

### 6.2 Business model {#sec-6-2-model}
- Organization subscription: tiered by branch scale and role seats, supporting pilots through scaled deployments.
- Industry template pack delivery: deliver configurable workflow templates and industry knowledge components for fast deployment and replication.
- Value-added modules: compliance auditing, dashboards, specialist collaboration, etc., enabled on demand.
- Primary bundle: organization subscription plus industry template packs, expanded by value-added modules based on organizational needs.

### 6.3 Operations and growth playbook {#sec-6-3-growth}
- Benchmark organization pilots: validate the closed loop through pilots, distilling reusable templates and deployment methods.
- Standardized delivery and training system: form delivery packs and training flows to shorten go-live time and reduce delivery costs.
- Channel and ecosystem collaboration: acquire and deliver jointly with channel partners and industry organizations, building a stable acquisition and delivery network.



## 🧭 7. Future directions {#sec-7-roadmap}
### 7.1 Product roadmap {#sec-7-1-product}
- Deepen organization-level deliverable capabilities: support unified deployment from pilots to multi-branch and multi-business-line rollouts.
- Strengthen safety and compliance: cover permission management, audit trails, risk boundaries, and traceability.
- Build an industry template library and knowledge components: improve replication speed and reduce vertical deployment costs.

### 7.2 Scaling path {#sec-7-2-scale}
- Use industry template packs and organization deploymentplan as core assets to drive cross-branch replication.
- Drive expansion by service consistency, handoff efficiency, and customer satisfaction as key metrics.
- Continuously iterate scripts, workflows, and risk boundaries through the data closed loop.

### 7.3 Ecosystem partnerships {#sec-7-3-eco}
- Collaboration with channel partners and industry organizations: link acquisition and delivery.
- Connect data and toolchains: build a sustainable, iterative advisory operations closed loop.



## ✉️ 8. Contact {#sec-8-contact}
If you are:
- A medical aesthetics organization or chain professional services team looking to use AI to improve advisory efficiency and service consistency
- An investorfocused on AI-driven digitization of professional services
- A partner interested in collaborating on vertical AI consultant products and industry template packs

Feel free to reach out to exchange product progress and collaboration opportunities.

### 👤 Founder
ProAdvisor is one of the flagship products of ModelsLive Inc. It was founded by Dr. Yuyan Chen. She received her Ph.D. in Computer Science from Fudan University and is currently a postdoctoral researcher in Computational Biology in the United States at Cornell University. She has long focused on innovation and real-world deployment of large models and AI4Health. Related results have been published in top international conferences and journals, and have received multiple national invention patents.
- Personal homepage: [yukyin.github.io](https://yukyin.github.io/)
- Company homepage: [modelslive.org](https://modelslive.org/)
- Email: [ychen@modelslive.org](mailto:ychen@modelslive.org)
