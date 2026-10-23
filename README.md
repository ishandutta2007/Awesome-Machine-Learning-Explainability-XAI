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

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



| Product | Description | Pricing | Free Tier Limit |

| :--- | :--- | :--- | :--- |

| **[Fiddler AI](https://www.fiddler.ai/)** | Model performance monitoring and explainable AI platform. Decouples monitoring, explainability, and fairness so you pay only for what you use. | Usage-based with annual commitment. Metrics: data ingested, number of models, number of explanations, and retention months. **Lite** and **Standard** plans available; contact sales for estimate . | No permanent free tier. **Trial available** via pricing estimate request. |

| **[Arize AI](https://arize.com/)** | AI observability and LLM evaluation platform with explainability features for tabular and unstructured models. | **AX Free**: $0. **AX Pro**: paid tier with 50k spans/month included. **Enterprise**: custom with self-hosted deployment option . | **AX Free**: 1 GB storage, 15-day retention, 25k spans/month, unlimited users, unlimited evaluations . |

| **[Arthur AI](https://www.arthur.ai/)** | AI governance and monitoring platform with built-in explainability, fairness, and "What-If" analysis. | **Free**: $0/mo. **Premium**: $60/mo. **Enterprise**: custom (VPC, SSO, SLAs) . | **Free plan**: 2 projects, 1 workspace, 300k spans/month, 12k inferences/month, 7-day retention, unlimited users, 3 custom alerts per model . |

| **[WhyLabs](https://whylabs.ai/)** | AI observability platform. **Transitioned to fully open-source** (Apache 2.0) after acquisition; legacy SaaS pricing remains on AWS Marketplace. | **Open Source**: Free. Legacy SaaS: $100/mo for 2 models, $200/mo for 3 models, Enterprise ~$8,333/mo . | **Entire platform is now free and open-source**, including whylogs and langkit . |

| **[H2O.ai](https://h2o.ai/)** | Enterprise AI platform with Driverless AI (AutoML) that includes built-in model explainability (variable importance, reason codes). | Enterprise-tier, quote-based. Driverless AI licensed per user or per deployment. | **Free API tier**: 2 requests/minute, 20/day, 500/month, ≤100k rows . Not a full XAI platform tier. |

| **[DataRobot](https://www.datarobot.com/)** | Automated ML platform with prediction explanations and model interpretation built into deployments. | Classic MLOps (Pricing 5.0): contact sales. Active deployments based pricing . | No public free tier. Trial available via sales engagement. |



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
