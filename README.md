# Awesome-Machine-Learning-Explainability-XAI

## Top Machine Learning Explainability (XAI) Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Model Interpretation, Feature Attribution & Self-Hosted Explainability Toolkits*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Machine Learning Explainability (XAI)**. These tools help data scientists and stakeholders understand *why* a model made a specific prediction—surfacing feature importance, generating local explanations, and auditing models for fairness and compliance.



**Examples** include SHAP, LIME, InterpretML, Fiddler AI, Arize AI, Arthur AI, and WhyLabs (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, avoiding per-explanation SaaS fees, and controlling the interpretation layer. The open-source landscape is anchored by **SHAP** (the game-theoretic attribution standard), **LIME** (the original local surrogate method), and **InterpretML** (Microsoft's unified glassbox/blackbox toolkit), with **Captum** and **Alibi** serving PyTorch-native and TensorFlow-friendly needs respectively.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global Explainable AI (XAI) and ML interpretability market is estimated at **$9.2B–$11.1B in 2025–2026**, growing at a CAGR of ~18–20% driven by enterprise regulatory compliance (such as the EU AI Act and financial fair-lending mandates). The sector is **moderately fragmented** overall: major cloud hyperscalers (AWS SageMaker Clarify, Azure ML, Google Vertex AI Explainable AI) hold a concentrated top tier, while independent platforms and open-source ecosystems compete dynamically through deep domain diagnostics, governance templates, and specialized attribution toolkits.

## SaaS/Hosted Platforms

| Product | Company Size (Valuation / Revenue) | Description | Pricing | Free Tier Limit |
| :--- | :--- | :--- | :--- | :--- |
| **[DataRobot](https://www.datarobot.com/)** | **$6.3B valuation** (~$250M ARR) | Automated ML and governance platform with native prediction explanations, feature impact, and model interpretation pipelines. | Starts at **$25,000/year** (custom annual subscriptions based on active user seats, compute AI units, and production deployments). | **30-day free trial** with full platform access (capped at shared modeling workers, ~1,000 LLM calls, and 15 vector DBs). |
| **[H2O.ai](https://h2o.ai/)** | **$1.7B valuation** (~$75M ARR) | Enterprise AI platform featuring Driverless AI with automated machine learning interpretability (reason codes, surrogate models, Shapley values). | Starts at **$25,000/year** (single-node BYOL license; multi-node and H2O AI Cloud typically $75k–$100k+/year). | **21-day free trial** license key for Driverless AI (full feature access; self-hosted or BYOL on cloud infrastructure) + permanently free open-source H2O-3. |
| **[Arize AI](https://arize.com/)** | **$915M valuation** (~$30M ARR; Acquired by Dynatrace) | AI observability and LLM evaluation platform with explainability workflows for tabular, computer vision, and unstructured models. | **AX Free**: $0/mo. Paid tier starts at **$50/month** (AX Pro, includes 50k spans/mo and 10 GB ingestion). Enterprise offers custom VPC deployment. | **Free forever plan**: 25k spans/month, 1 GB ingestion volume, 15-day data retention, unlimited users, Alyx AI assistant. |
| **[Fiddler AI](https://www.fiddler.ai/)** | **~$200M valuation** (~$30M ARR; $30M Series C) | Model performance monitoring and explainable AI platform with unified metrics for data drift, game-theoretic attributions, and bias tracking. | Developer tier starts at **$0.002 per trace**; enterprise production monitoring plans start around **$1,500/month** ($18,000/year). | **Free plan** for real-time safety guardrails & evaluations; plus **30-day free trial** on AWS Marketplace (SageMaker Partner AI App) supporting up to 5 models. |
| **[Arthur AI](https://www.arthur.ai/)** | **~$45M valuation** (~$5M ARR) | AI governance and monitoring platform with built-in model explainability, fairness audits, and counterfactual "What-If" scenario analysis. | **Free**: $0/mo. Paid tier starts at **$60/month** (Premium tier). Custom pricing for Enterprise VPC/SSO. | **Free forever plan**: 2 projects, 1 workspace, 300k spans/month, 12,000 model inferences/month, 7-day data retention, unlimited seats, 3 custom alerts/model. |
| **[WhyLabs](https://whylabs.ai/)** | **~$37M valuation** (~$10M ARR; Acquired) | AI observability and model profiling platform utilizing statistical profiling (whylogs) to track data drift and feature distribution changes. | **Free & Open Source** (Platform open-sourced under Apache 2.0). Legacy SaaS on AWS Marketplace starts at **$100/month** (for 2 models; $200/mo for 3 models). | **Entire platform is 100% free forever and open-source** (self-hostable Apache 2.0 without tier limits or explanation caps). |

## Open-Source GitHub Projects



- **[SHAP](https://github.com/slundberg/shap)** [![GitHub Stars](https://img.shields.io/github/stars/slundberg/shap?style=social&color=white)](https://github.com/slundberg/shap/stargazers)  

  **The game-theoretic attribution standard.** ~25.6k stars . Implements Shapley values from cooperative game theory to assign each feature a contribution to the prediction—theoretically grounded and consistent. **Model-agnostic** (works with tree models, neural networks, linear models) with optimized implementations for XGBoost/LightGBM. **Visualizations**: force plots, summary plots, dependence plots, waterfall charts. Best for teams wanting the most widely accepted, defensible feature attribution method with strong visualization support.



- **[LIME](https://github.com/marcotcr/lime)** [![GitHub Stars](https://img.shields.io/github/stars/marcotcr/lime?style=social&color=white)](https://github.com/marcotcr/lime/stargazers)  

  **The original local surrogate method.** ~11,979 stars . Explains individual predictions by fitting a simple interpretable model (linear regression, decision tree) to perturbations of the input around the prediction point. **Model-agnostic** and conceptually intuitive: "what local behavior approximates the black box here?" **Limitations**: sampling-based and can be unstable; explanations vary between runs. Best for quick, intuitive local explanations and as a complement to SHAP's global consistency.



- **[InterpretML](https://github.com/interpretml/interpret)** [![GitHub Stars](https://img.shields.io/github/stars/interpretml/interpret?style=social&color=white)](https://github.com/interpretml/interpret/stargazers)  

  **Microsoft's unified glassbox and blackbox toolkit.** Provides **Explainable Boosting Machine (EBM)**—a glassbox model that is competitive with gradient boosting while being fully interpretable—plus SHAP, LIME, and partial dependence plots in a single API. **Strengths**: one interface for both inherently interpretable models and post-hoc explanations. Best for teams wanting to choose between transparent models and blackbox explanations without leaving one library.



- **[Captum](https://github.com/pytorch/captum)** [![GitHub Stars](https://img.shields.io/github/stars/pytorch/captum?style=social&color=white)](https://github.com/pytorch/captum/stargazers)  

  **The PyTorch-native interpretation library.** Implements integrated gradients, saliency maps, GradCAM, DeepLIFT, and Shapley values specifically for PyTorch models. **Strengths**: tight integration with PyTorch tensors and autograd; optimized for deep learning workflows. Best for PyTorch practitioners needing gradient-based and perturbation-based explanations for neural networks.



- **[Alibi](https://github.com/SeldonIO/alibi)** [![GitHub Stars](https://img.shields.io/github/stars/SeldonIO/alibi?style=social&color=white)](https://github.com/SeldonIO/alibi/stargazers)  

  **The Seldon-backed explanation library.** Supports both TensorFlow and PyTorch, with anchor explanations, counterfactuals, integrated gradients, and kernel SHAP. **Strengths**: strong on counterfactual explanations ("what minimal change would flip the prediction?"). Best for teams needing counterfactual analysis alongside standard attribution methods.



### Additional Strong Open-Source Options



- **dalex** — R and Python library for model-agnostic exploration, with break-down plots, SHAP, and partial dependence. Best for R users and teams wanting a unified exploration workflow.

- **eli5** — Older but still useful library for debugging ML classifiers and inspecting feature importances. Best for quick sanity checks on scikit-learn models.

- **shapash** — Web-based dashboard for SHAP-based explanations, designed for business stakeholders. Best for teams wanting to share explanations without building a custom UI.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- **SHAP and LIME answer different questions**: SHAP provides consistent, game-theoretic attributions; LIME provides local approximations that are intuitive but can be unstable. Many teams use both—SHAP for rigorous analysis, LIME for quick stakeholder explanations.

- **SaaS XAI pricing is opaque and usage-based**: Fiddler and DataRobot require sales engagement for quotes; Arize and Arthur offer transparent free tiers but scale with volume . Model your explanation volume before committing.

- **WhyLabs is now fully open-source**: after acquisition, the platform (including whylogs) is free under Apache 2.0. The legacy SaaS tiers remain on marketplaces but are no longer the primary path .

- **Explainability is not fairness**: SHAP tells you *why* a prediction happened, not whether the model is fair. Pair XAI with dedicated fairness auditing tools.



---



**Made for data scientists, ML engineers, and organizations building transparent, accountable machine learning systems.**  

Let's make ML explainability more open, rigorous, and accessible.
