---
title: "Ekova: A Personality-Support Companion with Multi-Model Routing and Cross-Session Memory"
layout: single
permalink: /projects/ekova-en/
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


> ### 📌 Summary
>
> Ekova is a multi-model AI companion built around one idea: the friend who always gets you. Five distinct support personas adapt to whatever the moment calls for, while a unified memory layer carries everything the user has shared forward across every session and every mode switch.
>
> - Five support personas, Coach, Warm, Tsukkomi, Real, and Gonzo, each covering a functionally distinct conversational need, from emotional holding to structured action planning.
> - Dynamic routing selects the most suitable model and persona in real time. Users experience one coherent companion regardless of which backend is running.
> - Say it once, be understood everywhere. Prior context follows the user across persona switches, model changes, and new sessions with no re-introduction required.


{::nomarkdown}
<div id="ek-vsc-toc" aria-label="Table of contents">
  <input id="ek-vsc-toggle" type="checkbox" />
  <label id="ek-vsc-handle" for="ek-vsc-toggle" title="Open table of contents" aria-label="Open TOC"><span>≡</span></label>

  <div id="ek-vsc-panel" role="navigation" aria-label="Table of contents">
    <div class="ek-vsc-head">
      <div class="ek-vsc-title">Table of contents</div>
      <label id="ek-vsc-close" for="ek-vsc-toggle" title="Close table of contents" aria-label="Close">⟨</label>
    </div>

    <nav id="ek-vsc-links">
      <a href="#sec-1-overview">🧩 1. Product overview</a>
      <a class="l3" href="#sec-1-1-positioning">1.1 Why existing models fall short</a>
      <a class="l3" href="#sec-1-2-personas">1.2 The five personas</a>

      <a href="#sec-2-tech">⚙️ 2. Technical architecture</a>
      <a class="l3" href="#sec-2-1-routing">2.1 Context-aware model routing</a>
      <a class="l3" href="#sec-2-2-buffer">2.2 Transition buffer layer</a>
      <a class="l3" href="#sec-2-3-memory">2.3 Unified cross-session memory</a>
      <a class="l3" href="#sec-2-4-research">2.4 Research backing</a>

      <a href="#sec-3-demo">🎥 3. Interface showcase</a>

      <a href="#sec-4-capabilities">✨ 4. Core capabilities</a>
      <a class="l3" href="#sec-4-1-user">4.1 Value for users</a>
      <a class="l3" href="#sec-4-2-diff">4.2 Differentiation from existing models</a>

      <a href="#sec-5-product">📱 5. Product form and access</a>

      <a href="#sec-6-biz">📈 6. Commercial model</a>
      <a class="l3" href="#sec-6-1-target">6.1 Target users</a>
      <a class="l3" href="#sec-6-2-pricing">6.2 Pricing and access</a>
      <a class="l3" href="#sec-6-3-retention">6.3 Retention mechanics</a>

      <a href="#sec-7-roadmap">🧭 7. Future directions</a>

      <a href="#sec-8-contact">✉️ 8. Contact</a>
    </nav>
  </div>
</div>
{:/nomarkdown}


## 🧩 1. Product overview {#sec-1-overview}

Ekova is a **multi-model AI companion** that gives users one coherent "friend" backed by the best available foundation models. It routes each conversational moment to the most suitable model and persona combination, not by static configuration, but by reading the actual context in real time. Behind the single interface, Ekova runs GPT, Claude, Gemini, DeepSeek, and other mature models as interchangeable backends, while surfacing only one continuous identity to the user.

The core product promise is simple: say it once, be understood everywhere. A unified memory layer stores everything the user has disclosed across all sessions and all persona modes. When the routing engine switches from one persona or backend to another, it carries that entire history forward. The user never re-introduces themselves.

Ekova's personality system is grounded in research: five distinct support personas, each designed to do something no other can fully replace. The goal is not to make users feel better in the moment, but to help them understand themselves better over time.

### 1.1 Why existing models fall short {#sec-1-1-positioning}

Each major foundation model has a characteristic blind spot as a companion:

- **Gemini**: overdramatic, turns small problems into world-ending crises
- **DeepSeek**: over-mothering, reflexively responds with "you've been through so much," which feels patronizing in many contexts
- **GPT**: pure tool with no warmth, like talking to a customer service bot
- **Claude**: compulsive redirector, always trying to pull the conversation back to a "main topic"
- **All models**: persona consistency degrades across long sessions, and every model switch starts from zero with no shared memory

Ekova addresses all of these through routing, buffering, and memory rather than by betting on a single model.

### 1.2 The five personas {#sec-1-2-personas}

Each persona is a minimal functional unit grounded in the Personality Support framework. No two are substitutable: removing any one strictly reduces the system's ability to advance cognitive clarity across the full user population.

<span class="ek-persona ek-warm">Warm</span> Lowers self-disclosure resistance through emotional validation and grounded holding, creating space before any inquiry so the user feels heard rather than interrogated.

<span class="ek-persona ek-tsuk">Tsukkomi</span> Dissolves defensive narratives through irony, deflecting via humor to trigger cognitive reframing without head-on confrontation.

<span class="ek-persona ek-real">Real</span> Separates fact from self-attribution, reframing the situation through constraint analysis and causal structure without softening the reality check.

<span class="ek-persona ek-gonzo">Gonzo</span> Establishes an estranged perspective through cross-domain analogy, recontextualizing via high-dimensional metaphor so the user sees their situation from a structurally different angle.

<span class="ek-persona ek-coach">Coach</span> Crystallizes insight into a concrete action plan, structuring variables, routing options, and closing with specific steps toward problem articulation and resolution.


## ⚙️ 2. Technical architecture {#sec-2-tech}

### 2.1 Context-aware model routing {#sec-2-1-routing}

Routing is dynamic, not a static weight assignment. The system first responds with a neutral acknowledgment to receive the user, then lightly probes for context before committing to a routing decision. Once the situation is clear, it selects the most suitable persona and backend model for that moment. Probing before routing produces significantly more accurate decisions than immediate inference from the first message.

### 2.2 Transition buffer layer {#sec-2-2-buffer}

Large persona jumps, for example from Warm directly to Coach, feel like a personality transplant to users. Ekova uses a GPT buffer layer to bridge stylistically distant transitions: Warm to one or two GPT buffer turns to Coach or Gonzo, rather than a direct cut. This preserves the sense of one continuous companion across mode changes.

### 2.3 Unified cross-session memory {#sec-2-3-memory}

All conversation history is stored in a centralized database owned by the platform. Every model call, regardless of which backend is selected, receives the relevant prior context as part of the prompt. The user's disclosed information accumulates across interactions: the more they share, the more precisely Ekova can route, respond, and personalize, compounding self-understanding over time.

This design makes memory the core retention mechanism. The more context a user has built up, the higher the switching cost to any alternative that starts from zero.

### 2.4 Research backing {#sec-2-4-research}

Ekova's persona system is grounded in peer-reviewed research. The underlying work, submitted to COLM 2026 as **"Ekova: A Personality-Support Agent for Self-Discovery Dialogue"**, establishes the five-persona structure through a purpose-built training framework and a real longitudinal interaction dataset. Each persona is validated as functionally distinct: no two are substitutable, and the system is designed so that removing any one of them would meaningfully reduce what the companion can offer. This gives Ekova's multi-persona design an interpretable, research-backed foundation rather than ad-hoc style tuning.


## 🎥 3. Demo and interface showcase {#sec-3-demo}

Ekova surfaces as a single companion whose voice adapts based on what you select. In Default mode the system automatically picks the most fitting persona for your input. In Custom mode you choose which personas to blend, and Ekova synthesizes them into one unified response. The demo uses deterministic outputs to ensure consistent, stable replies across sessions.

<div style="margin:0.4rem 0 0.8rem;">
  <video id="demo-ekova" controls playsinline preload="metadata"
    style="display:block; width:80%; max-width:860px; margin:0 auto; border-radius:14px;">
    <source src="https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/ekova-demo.mp4" type="video/mp4">
    Your browser does not support video playback. You can also directly visit: https://github.com/Yukyin/Yukyin.github.io/releases/download/videos-v1/ekova-demo.mp4
  </video>
</div>

<div class="pa-watchguide" data-video="demo-ekova"
     style="max-width:860px; margin:0.55rem auto 0.9rem; font-size:.78rem; color:#444; line-height:1.8;">
  <span class="wg" data-t="0">0:00 Default mode: auto persona selection</span>
  <span class="wg" data-t="27">0:27 Custom mode: one persona selected</span>
  <span class="wg" data-t="33">0:33 Custom mode: three personas blended</span>
  <span class="wg" data-t="52">0:52 Custom mode: four personas blended</span>
  <span class="wg" data-t="76">1:16 Custom mode: all five personas</span>
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

- Default mode: Ekova automatically selects the most suitable support persona and routes to the appropriate backend based on the user's current input, maintaining a coherent interaction identity across sessions.

<div style="text-align:center; margin: 0.55rem 0 0.9rem;">
  <img src="/assets/ekova/ekova-interface.png"
      alt="Ekova main interface, adaptive routing across five personas"
      style="width:80%; max-width:860px; height:auto; display:inline-block;" />
  <div class="ek-caption" style="margin-top:0.35rem;">
    <em>Fig 1: Ekova adaptive routing interface. The agent selects a support persona, here Gonzo, and generates a response that recontextualizes the user's workplace frustration through a machine learning analogy.</em>
  </div>
</div>

- Personalized mode: users can manually select a specific persona, or combine preferred personas, to receive reference responses under each chosen support style simultaneously.

<div style="text-align:center; margin: 0.25rem 0 0.9rem;">
  <img src="/assets/ekova/five-interface.png"
      alt="Ekova persona selection interface, all five personas"
      style="width:80%; max-width:860px; height:auto; display:inline-block;" />
  <div class="ek-caption" style="margin-top:0.35rem;">
    <em>Fig 2: Customized persona selection interface. Users choose a support style and view the corresponding reference response. The same user input about a failed delivery yields five structurally distinct responses: emotional holding (Warm), ironic distance (Tsukkomi), factual reframing (Real), analogical reframing via "paid DLC" (Gonzo), and a three-step resolution plan (Coach).</em>
  </div>
</div>




## ✨ 4. Core capabilities {#sec-4-capabilities}

### 4.1 Value for users {#sec-4-1-user}

- **Continuity**: the unified memory layer means users never re-explain their situation. Prior context persists across persona switches, model changes, and new sessions.
- **Multiplicity**: one interface, five functionally distinct conversational modes. Users receive what the moment actually calls for, not the same flavor every time.
- **Depth over time**: self-knowledge compounds. As users disclose more, Ekova builds a more accurate model of their patterns, constraints, and recurring situations, improving routing precision and response relevance with each session.
- **No forced positivity**: Ekova will challenge, reframe, call out, and push back when that serves cognitive clarity, not just validate. The five personas cover the full range from emotional holding to hard structural confrontation.

### 4.2 What makes Ekova different {#sec-4-2-diff}

Most AI companions ask users to pick a tool and stick with it. Ekova works the other way around: the right support style comes to the user based on what the conversation actually needs. When the mode shifts, a buffer layer handles the transition so the experience stays smooth rather than abrupt. And because the memory layer is unified across all personas and backends, users never carry the burden of re-explaining context. The more they use Ekova, the more it understands them, and the less they have to say.


## 📱 5. Product form and access {#sec-5-product}

- **Web-first**: accessible via mobile browser, no app required. This avoids app store review constraints and accelerates iteration.
- **Voice input support**: speech-to-text input adapted for mobile use patterns.
- **Manual onboarding**: early access by invitation only. User accounts are activated individually to maintain quality and gather structured feedback.
- **Language**: primary interface in Chinese (Simplified), serving mainland and diaspora Chinese users.
- **Name design**: Ekova is gender-neutral, suitable for all users without demographic targeting.


## 📈 6. Commercial model {#sec-6-biz}

### 6.1 Target users {#sec-6-1-target}

- Heavy multi-model users who have already paid for GPT Plus, Claude Pro, Gemini Advanced, and still context-switch between them manually
- Users with genuine emotional companionship needs who are unsatisfied with any single model's fixed personality
- Technically-aware users comfortable with API key management (BYOK model in early stage)
- Chinese-speaking users globally: mainland China, Hong Kong, Taiwan, and diaspora communities

### 6.2 Pricing and access {#sec-6-2-pricing}

Early access is free for the first 20 conversation turns to let users experience the memory payoff firsthand. Paid access is currently available by reaching out to the founder directly. Longer-term, Ekova will offer public subscription through ModelsLive Inc. API costs are transparently separated from the platform fee.

### 6.3 Retention mechanics {#sec-6-3-retention}

Memory is the primary retention driver. The more context a user accumulates, the higher the migration cost to any fresh-start alternative. The product goal is to deliver a clear "the system remembered what I said" moment within the user's first week. This is the most reliable trigger for converting free users to paid subscribers.


## 🧭 7. Future directions {#sec-7-roadmap}

- **Multi-language extension**: the current system is Chinese-native. English and multilingual support is a planned expansion, contingent on dataset extension and persona adaptation for cross-cultural conversational norms.
- **Memory management interface**: give users visibility into and control over their accumulated context, including what has been stored and what can be edited or removed.
- **Persona combination modes**: allow users to configure blended personas for specific recurring use cases (e.g., Warm + Coach for career conversations, Real + Gonzo for creative blocks).
- **Cross-session benchmarking**: develop evaluation metrics suited to persistent agent assessment. Current NLP benchmarks are single-turn and cannot capture the compounding self-understanding trajectory that defines Ekova's core value.
- **ModelsLive platform integration**: connect Ekova's memory and routing layer with ProAdvisor and VerbalValue under a unified ModelsLive API, enabling shared user context across product surfaces.


## ✉️ 8. Contact {#sec-8-contact}

If you are:
- A Chinese-speaking user who has bounced between multiple AI tools and wants one that actually remembers you
- An investor focused on AI companionship, multi-agent routing, or Chinese-language AI products
- A researcher or collaborator interested in Personality Support systems, persistent memory agents, or multi-persona dialogue

Feel free to reach out to exchange product progress and collaboration opportunities.

### 👤 Founder
Ekova was founded by Dr. Yuyan Chen and is led in R&D by Dr. Chen. She received her Ph.D. in Computer Science from Fudan University and is currently a postdoctoral researcher in Computational Biology in the United States at Cornell University. She has long focused on innovation and real-world deployment of large models and AI4Health. Related results have been published in top international conferences and journals, and have received multiple national invention patents.
- Homepage: [Yukyin.github.io](https://yukyin.github.io/)
- Email: [yolandachen0313@gmail.com](mailto:yolandachen0313@gmail.com)
