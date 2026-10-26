<div align="center">
  <img src="https://avatars.githubusercontent.com/u/332657925?s=200&v=4" width="110" alt="Sievehouse" />

  # Sievehouse

  <img src="https://readme-typing-svg.demolab.com/?font=Fira+Code&weight=500&size=22&duration=3000&pause=1000&color=38BDF8&center=true&vCenter=true&width=600&lines=GPU+%26+AI+Infrastructure+Research;Evidence+over+assumptions;Independent+verification%2C+not+trust" alt="typing banner" />

  [![GitHub org](https://img.shields.io/badge/org-Sievehouse-1e2327?style=flat-square&logo=github)](https://github.com/Sievehouse)
  [![Followers](https://img.shields.io/github/followers/Sievehouse?style=social)](https://github.com/orgs/Sievehouse/followers)
  [![LinkedIn](https://img.shields.io/badge/LinkedIn-Sievehouse-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/144023602/)
  [![Email](https://img.shields.io/badge/email-sievehouse.gpu%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:sievehouse.gpu@gmail.com)
  ![Profile views](https://komarev.com/ghpvc/?username=Sievehouse&style=flat-square&color=38BDF8&label=profile+views)
</div>

<br/>

## About

Sievehouse explores software opportunities across GPU and AI infrastructure, with a focus on reliability, independent verification, and evidence based performance assurance.

Current research investigates how GPU cloud customers and providers can verify delivered compute quality against contractual requirements: acceptance testing, SLA evidence, tenant isolation assurance, and compute risk signals relevant to lenders and insurers.

We prioritize independent research, reproducible measurements, open source tooling, and evidence driven validation. We test assumptions before committing to building a product. This is a research backed opportunity, not a claim of an established commercial offering.

## Tech stack

![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![NVIDIA](https://img.shields.io/badge/NVIDIA-76B900?style=for-the-badge&logo=nvidia&logoColor=white)

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sievehouse&layout=compact&theme=dark&hide_border=true&langs_count=8" alt="Top languages" />
</p>

## Ecosystem

A layered view of how the projects relate: evidence at the base, observability in the middle, research and code health feeding the same discipline back in.

```mermaid
flowchart TB
    classDef evidence fill:#1e3a8a,stroke:#60a5fa,color:#fff,stroke-width:2px
    classDef observe fill:#064e3b,stroke:#34d399,color:#fff,stroke-width:2px
    classDef research fill:#581c87,stroke:#c084fc,color:#fff,stroke-width:2px
    classDef cluster fill:#1e2327,stroke:#9ca3af,color:#fff,stroke-width:1px

    Cluster["GPU Cluster\nDCGM / Prometheus / K8s / Slurm"]:::cluster

    subgraph L1["Evidence and Contracts"]
        GS["gpu-sentinel\nsigned evidence logs, SLA engine, XID agent"]:::evidence
    end

    subgraph L2["Observability"]
        GL["gpu-lens\nread only incident intelligence"]:::observe
        CL["cncf-lens\nunified K8s + Prometheus + Loki + Jaeger timeline"]:::observe
    end

    subgraph L3["Code and Model Health"]
        TB["truebug\nstatic analysis + fine tuned LLM triage"]:::research
        SRT["shap-review-toolkit\nevidence driven SHAP review"]:::research
    end

    Cluster -->|telemetry, events| GS
    Cluster -->|telemetry, events| GL
    Cluster -->|telemetry, events| CL
    GS -->|sealed SLA statements| Consumer["Provider / Customer / Insurer / Lender"]
    GL -->|incident reports| Consumer
    CL -->|correlated timeline| GL
    TB -.shared evidence over assertion discipline.-> GS
    SRT -.shared evidence over assertion discipline.-> GS
```

### How a dispute gets resolved

```mermaid
sequenceDiagram
    autonumber
    participant Node as GPU Node
    participant GS as gpu-sentinel
    participant GL as gpu-lens
    participant Ops as Operator
    participant Cust as Customer / Insurer

    Node->>GS: signed heartbeats + XID events
    Node->>GL: DCGM / Prometheus telemetry
    GL->>Ops: incident report, rule based and deterministic
    Ops->>GS: confirm fault window
    GS->>GS: compute sealed SLA statement, SHA-256
    GS->>Cust: statement plus raw signed events
    Cust->>GS: independent replay
    GS-->>Cust: same hash, statement stands
```

### Project positioning

Illustrative, not a scorecard.

```mermaid
quadrantChart
    title Research stage vs infrastructure depth
    x-axis Lighter infra --> Deeper infra
    y-axis Research stage --> Production stage
    quadrant-1 Production infra
    quadrant-2 Infra research
    quadrant-3 Early research
    quadrant-4 Production tooling
    gpu-sentinel: [0.75, 0.35]
    gpu-lens: [0.70, 0.55]
    cncf-lens: [0.55, 0.60]
    truebug: [0.30, 0.25]
    shap-review-toolkit: [0.25, 0.55]
```

## Projects

<table>
<tr>
<td width="50%">

<a href="https://github.com/Sievehouse/gpu-sentinel">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=Sievehouse&repo=gpu-sentinel&theme=dark&hide_border=true" alt="gpu-sentinel" />
</a>

![status](https://img.shields.io/badge/status-pre--alpha%20v0.2.0-orange?style=flat-square)
![last commit](https://img.shields.io/github/last-commit/Sievehouse/gpu-sentinel?style=flat-square)
![license](https://img.shields.io/github/license/Sievehouse/gpu-sentinel?style=flat-square)

Signed, hash chained evidence logs and a replayable SLA engine for rented GPU clusters. Sealed monthly statements, provider vs tenant corroboration, group testing fault localization.

</td>
<td width="50%">

<a href="https://github.com/Sievehouse/gpu-lens">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=Sievehouse&repo=gpu-lens&theme=dark&hide_border=true" alt="gpu-lens" />
</a>

![status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)
![last commit](https://img.shields.io/github/last-commit/Sievehouse/gpu-lens?style=flat-square)

Self-hosted, strictly read only GPU fleet diagnostics for Kubernetes. Six deterministic rules turn DCGM and K8s state into incident reports. [Live demo](https://gpu-lens.onrender.com/)

</td>
</tr>
<tr>
<td width="50%">

<a href="https://github.com/Sievehouse/cncf-lens">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=Sievehouse&repo=cncf-lens&theme=dark&hide_border=true" alt="cncf-lens" />
</a>

![status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)
![last commit](https://img.shields.io/github/last-commit/Sievehouse/cncf-lens?style=flat-square)
![license](https://img.shields.io/github/license/Sievehouse/cncf-lens?style=flat-square)

Unified CLI correlating Kubernetes, Prometheus, Loki, and Jaeger onto one timeline.

</td>
<td width="50%">

<a href="https://github.com/Sievehouse/truebug">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=Sievehouse&repo=truebug&theme=dark&hide_border=true" alt="truebug" />
</a>

![status](https://img.shields.io/badge/status-research-blueviolet?style=flat-square)
![last commit](https://img.shields.io/github/last-commit/Sievehouse/truebug?style=flat-square)
![license](https://img.shields.io/github/license/Sievehouse/truebug?style=flat-square)

Self-hosted repository intelligence: static analysis candidates verified and triaged by small fine tuned LLMs. No commercial LLM API dependency.

</td>
</tr>
<tr>
<td width="50%">

<a href="https://github.com/Sievehouse/shap-review-toolkit">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=Sievehouse&repo=shap-review-toolkit&theme=dark&hide_border=true" alt="shap-review-toolkit" />
</a>

![status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)
![last commit](https://img.shields.io/github/last-commit/Sievehouse/shap-review-toolkit?style=flat-square)

Evidence driven, reproduction first toolkit for reviewing the [SHAP](https://github.com/shap/shap) library: static, runtime, and differential analysis, fuzzing, provenance tracking.

</td>
<td width="50%" valign="top">

**Also in the org**

`crosscurrent` and `plumb`: placeholders, no code pushed yet.

`.github`: the org profile repo this file lives in.

</td>
</tr>
</table>

## Design principles

| Principle | What it means in practice |
|---|---|
| No AI in verdicts that move money or claim a defect | Deterministic engines decide; models triage, explain, draft |
| Evidence over assertion | Every claim traces to a signed log, a replay, or a reproduction |
| Least privilege, read only by default | gpu-lens and gpu-sentinel agents only read; never reset, drain, or schedule |
| Two vantage points beat one | Provider and tenant probes measure independently, then get compared |
| Honest limits | "No defect found by these tests" is the ceiling, never "no defect exists" |

## Roadmap

```mermaid
timeline
    title Sievehouse trajectory
    Oct 2026 : gpu-sentinel v0.2, heartbeats and tenant probe
             : AMD support, signed bundles
             : gpu-lens and cncf-lens in active development
    Next : gpu-sentinel v0.3
         : hosted multi party ledger
         : co-signed monthly statements
```

## Connect

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-Sievehouse-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Sievehouse)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sievehouse-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/144023602/)
[![Gmail](https://img.shields.io/badge/Email-sievehouse.gpu%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sievehouse.gpu@gmail.com)

*Open-source engineering. Independent verification. Evidence over assumptions.*

</div>
