---
layout: default
paper_url: https://arxiv.org/pdf/2604.08031
---

<style>
/* 隐藏 header 区域里指向主页的那条站点标题链接 */
header a[href="/"], /* 如果是根目录链接 */
header .site-title, /* 如果有 site-title 之类的 class */
.navbar-brand       /* 或者 bootstrap 里叫 navbar‑brand 的 */
{
  display: none !important;
}
</style>

<style>
.pill-bar{
  text-align:center;
  margin: 1.2rem 0 2rem;
}
.pill-bar a{
  display:inline-flex;
  align-items:center;
  gap:.4em;
  padding:.45rem 1.15rem;
  margin:0 .35rem;
  background:#333;
  color:#fff !important;
  border-radius:9999px;
  font-weight:500;
  text-decoration:none;
  font-size:0.95rem;
  line-height:1;
  transition:background .15s;
}
.pill-bar a:hover{ background:#555; }
.pill-bar img, .pill-bar i{
  height:1em;
  width:auto;
}

/* 1) 隐藏指向首页的第一个裸链接 */
body > a[href="/"],
body > a[href="{{ "/" | relative_url }}"],
body > a[href^="https://anonymous-ai97.github.io"]{
  display:none !important;
}

/* 保险：如果上面仍不中，就用这个“兜底” */
body > a:first-of-type{
  display:none !important;
}
</style>





<h1 align="center"><img src="/assets/Icon.png" alt="Paper Icon" style="height:2em; vertical-align:middle; margin-right:0.5em;"> POINT: Passenger Open-Ended Instruction Realization with LLM-Enabled Multi-Planner Scheduling in Autonomous Vehicles</h1>
<p align="center"> To facilitate community extensions, we are willing to release source code and dataset within 7 days of publication 🥰🥰🥰. Those interested in this project are advised to bookmark and subscribe for timely updates 😍😍! </p>


<div class="pill-bar">
  <a href="{{ page.paper_url }}"><img src="/assets/arxiv_icon.svg" alt=""> Paper</a>
  <a href="{{ page.code_url }}"><img src="/assets/github_icon.svg" alt=""> Code</a>
  <a href="{{ page.arxiv_url }}"><img src="/assets/dataset_icon.png" alt=""> Dataset</a>
</div>



# Abstract
Most Human-Machine Interaction (HMI) research overlooks the maneuvering needs of passengers in autonomous driving (AD). Natural language offers an intuitive interface, yet translating passenger open-ended instructions into control signals—without sacrificing interpretability and traceability—remains a challenge. This study proposes an innovative framework that leverages a large language model (LLM) to interpret instructions, generates executable scripts that schedule multiple motion planners based on real-time feedback, and converts planned trajectories into control signals. The scheduling-centric design decouples semantic reasoning from vehicle control at different timescales, establishing a transparent, auditable reasoning pathway from high-level instructions to low-level actions. Due to the absence of high-fidelity evaluation tools, this study also introduces the first benchmark for open-ended instruction realization in a closed-loop setting. Comprehensive experiments reveal that the framework significantly improves task-completion rates over LLM-agent and data-driven baselines, reduces LLM query costs, and achieves safety and compliance on par with specialized AD approaches.




# Modular Framework Design Enabling an Interpretable Reasoning Pathway
<h1 align="center"><img src="/assets/Overview.png" alt="Framwork Overview" style="height:15em; vertical-align:middle; margin-right:0.5em;"></h1>

This work proposes an instruction-realization framework powered by LLM. The framework leverages a LLM to interpret instructions (Stage 1) and generate executable scheduling scripts (Stage 2). These scripts schedule multiple motion planners using real-time environmental feedback and translate planned trajectories into control signals in a closed-loop setting (Stage 3).


# Open-Ended Passenger Instructions Exhibited High Lexical Diversity

<h1 align="center"><img src="/assets/sunburst_chart.png" alt="Word Distribution" style="height:30em; vertical-align:middle; margin-right:0.5em;"></h1>


# Animated Visualization Results of Our Framework
<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Left_Lane_Change_1.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Watch out for pedestrians!"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Left_Lane_Change_2.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"So, when do we get to join the fast lane club?"</figcaption>
    </td>
  </tr>
</table>


<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Pull_Over_2.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"I am not feeling great, can we stop for a second?"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Compositional_1.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Change to the fast lane after the turn."</figcaption>
    </td>
  </tr>
</table>



<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Right_Lane_Change_1.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"You are totally blocking the poor guy behind us!"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Right_Lane_Change_2.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Exit is just around the corner — get ready for the escape."</figcaption>
    </td>
  </tr>
</table>




<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Pull_Over_3.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"There’s a convenience store up ahead, mind if I grab something?"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Compositional_2.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Let’s chill for three and then go past."</figcaption>
    </td>
  </tr>
</table>





<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Left_Lane_Change_4.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"I feel unsafe behind that truck."</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Acceleration_1.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Hit the gas, grandma!"</figcaption>
    </td>
  </tr>
</table>


<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Left_Lane_Change_5.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"We’re kinda hogging the fast lane — maybe time to scoot over?"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Deceleration.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"This isn’t a highway, it’s a neighborhood street!"</figcaption>
    </td>
  </tr>
</table>










# Instruction Realization with Various LLMs

We contrasts the planner scheduling of Qwen‑3‑8B and DeepSeek‑V3 under identical simulation conditions for the left lane‑change command. Qwen‑3‑8B initiates the maneuver immediately at low speed, reducing traffic efficiency and leaving the lane change incomplete. DeepSeek‑V3 delays initiation until the ego vehicle speed exceeds 3 m/s, enlarging the target‑lane gap and shortening maneuver time, resulting in a smoother, earlier execution. This indicates that LLMs with different intelligence levels can exhibit substantial differences in behavior scheduling in dynamic traffic.

<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/SLM_1.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">Qwen-3-8B Scheduling: Directly change to the left Lane.</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/LLM_1.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">DeepSeek-V3 Scheduling: Change to the left Lane when ego vehicle speed exceeds 3 m/s.</figcaption>
    </td>
  </tr>
</table>





# Comparison with Instruction-Realization Baselines
DiLu++ occasionally overlooks critical inputs, such as historical behaviors and passenger instructions, resulting in incoherent driving decisions. Diffusion-ES frequently generates trajectories misaligned with instructions, largely due to the diffusion process functioning as a black box; despite test-time optimization, it often produces uncontrollable plans.

- "Watch out for pedestrians!"
<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/ChiTu.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">Ours</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/DiLu++.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">DiLu++</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/DiffusiomES.gif" alt="gif3" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">Diffusion-ES</figcaption>
    </td>
  </tr>
</table>



- "The current speed is fine, but I feels like we are kinda camping out in the fast lane..."
  
<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/ChiTu_2.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">Ours</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/DiLu++_2.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">DiLu++</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/DiffusionES_2.gif" alt="gif3" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">Diffusion-ES</figcaption>
    </td>
  </tr>
</table>


- "So, when do we get to join the fast lane club?"
  
<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/ChiTu_3.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">Ours</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/DiLu++_3.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">DiLu++</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:33.33%;">
      <img src="/assets/DiffusionES_3.gif" alt="gif3" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">Diffusion-ES</figcaption>
    </td>
  </tr>
</table>

