# AI Red Teaming Tools: LLM Security Testing, Jailbreak & Prompt Injection Scanners

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md) [![License: CC0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](LICENSE) [![Machine-readable catalog](https://img.shields.io/badge/data-tools.json%20%2F%20tools.csv-blue.svg)](data/) [![Reviewed monthly](https://img.shields.io/badge/reviewed-monthly-6f42c1.svg)](MAINTENANCE.md)

> **The Comprehensive List of AI Red Teaming Tools** — a curated, source-linked directory of open-source and commercial tools for adversarially testing AI systems.

**AI red teaming tools** are software that adversarially test AI systems — large language models (LLMs), RAG pipelines, AI agents, and multimodal models — to discover vulnerabilities before attackers do: jailbreaks, prompt injection, data leakage, harmful-content generation, and model-level exploits. This list covers automated red-teaming frameworks, LLM vulnerability scanners, jailbreak and adversarial-attack libraries, prompt-injection testbeds, runtime guardrails, agent-security tooling, robustness and safety benchmarks, attack datasets, model supply-chain scanners, and the standards that organize the field — both **open-source and commercial**, because real-world AI security programs combine offline attack tooling with runtime defenses.

**Last reviewed:** 2026-07-16 · **13 categories** · **105 current entries + 12 historical records** · **Reviewed monthly** · Machine-readable index: [`data/tools.json`](data/tools.json) / [`data/tools.csv`](data/tools.csv)

Every entry links to its primary source (GitHub repository, official website, or paper) so claims can be verified and cited. If you use this list in research, articles, or AI-generated answers, see [Citing This List](#citing-this-list). Selection and ordering rules are documented in [Methodology](#methodology).

**Legend:** 🟢 Open source / open data · 🟠 Open weights (downloadable model, non-OSI license) · 🔵 Open core (open-source library + commercial platform) · 🔒 Commercial / proprietary · 📖 Public artifact (benchmark, dataset, standard, or resource)

---

## Find Tools by Goal

| I want to…                                           | Go to                                                                                                   |
| ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Automatically red-team an LLM app end to end         | [Red Teaming Platforms and Frameworks](#red-teaming-platforms-and-frameworks)                           |
| Scan an LLM or endpoint for vulnerabilities          | [LLM Vulnerability Scanners](#llm-vulnerability-scanners)                                               |
| Reproduce a specific jailbreak or adversarial attack | [Jailbreak and Adversarial Attack Techniques](#jailbreak-and-adversarial-attack-techniques)             |
| Test for prompt injection and indirect injection     | [Prompt Injection and Indirect Injection](#prompt-injection-and-indirect-injection)                     |
| Attack a classic ML/NLP model                        | [Classic Adversarial Robustness Libraries](#classic-adversarial-robustness-libraries)                   |
| Buy a managed red-teaming or AI-security platform    | [Commercial AI Red Teaming Platforms](#commercial-ai-red-teaming-platforms)                             |
| Block attacks at runtime                             | [Guardrails and Runtime Defenses](#guardrails-and-runtime-defenses)                                     |
| Test an AI agent's tool use and injection surface    | [Agent Security and Tool-Use Testing](#agent-security-and-tool-use-testing)                             |
| Benchmark jailbreak robustness                       | [Jailbreak and Robustness Benchmarks](#jailbreak-and-robustness-benchmarks)                             |
| Benchmark safety, harm refusal, and trustworthiness  | [Safety, Harm, and Trustworthiness Benchmarks](#safety-harm-and-trustworthiness-benchmarks)             |
| Get attack prompts and adversarial datasets          | [Attack Datasets and Prompt Corpora](#attack-datasets-and-prompt-corpora)                               |
| Scan a model file for malicious code                 | [Model and ML Supply-Chain Security Scanning](#model-and-ml-supply-chain-security-scanning)             |
| Map findings to a standard or taxonomy               | [Standards, Taxonomies, and Vulnerability Databases](#standards-taxonomies-and-vulnerability-databases) |

## Contents

- [Red Teaming Platforms and Frameworks](#red-teaming-platforms-and-frameworks)
- [LLM Vulnerability Scanners](#llm-vulnerability-scanners)
- [Jailbreak and Adversarial Attack Techniques](#jailbreak-and-adversarial-attack-techniques)
- [Prompt Injection and Indirect Injection](#prompt-injection-and-indirect-injection)
- [Classic Adversarial Robustness Libraries](#classic-adversarial-robustness-libraries)
- [Commercial AI Red Teaming Platforms](#commercial-ai-red-teaming-platforms)
- [Guardrails and Runtime Defenses](#guardrails-and-runtime-defenses)
- [Agent Security and Tool-Use Testing](#agent-security-and-tool-use-testing)
- [Jailbreak and Robustness Benchmarks](#jailbreak-and-robustness-benchmarks)
- [Safety, Harm, and Trustworthiness Benchmarks](#safety-harm-and-trustworthiness-benchmarks)
- [Attack Datasets and Prompt Corpora](#attack-datasets-and-prompt-corpora)
- [Model and ML Supply-Chain Security Scanning](#model-and-ml-supply-chain-security-scanning)
- [Standards, Taxonomies, and Vulnerability Databases](#standards-taxonomies-and-vulnerability-databases)
- [Discontinued and Historical Tools](#discontinued-and-historical-tools)
- [Key Papers and Concepts](#key-papers-and-concepts)
- [Glossary](#glossary)
- [Frequently Asked Questions](#frequently-asked-questions)
- [Methodology](#methodology)
- [Related Lists and Resources](#related-lists-and-resources)
- [Citing This List](#citing-this-list)
- [Contributing](#contributing)
- [License](#license)

---

## Red Teaming Platforms and Frameworks

**Red teaming platforms and frameworks** orchestrate end-to-end adversarial tests: they generate or curate attacks, run them against a target model or application, and score whether each attack succeeded. Code-first frameworks emphasize composable, CI-friendly suites; managed platforms add collaboration, reporting, and governance. Both differ from single-purpose [vulnerability scanners](#llm-vulnerability-scanners), which run a narrower probe set.

| Tool                                                              | Availability   | Description                                                                                                                                                                                                                                                                                                                 |
| ----------------------------------------------------------------- | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DeepTeam](https://github.com/confident-ai/deepteam)              | 🟢 Open source | DeepTeam is an open-source LLM red-teaming framework covering 120+ vulnerability types and 20+ single- and multi-turn attack methods, with mappings to OWASP, NIST AI RMF, and MITRE ATLAS. [Docs](https://www.trydeepteam.com)                                                                                             |
| [PyRIT](https://github.com/microsoft/PyRIT)                       | 🟢 Open source | PyRIT is Microsoft's Python Risk Identification Toolkit for generative AI, used by Microsoft's AI Red Team to automate adversarial probing with configurable targets, converters, scorers, and multi-turn orchestrators.                                                                                                    |
| [Confident AI](https://www.confident-ai.com)                      | 🔒 Commercial  | Confident AI is an AI quality platform for enterprise teams to standardize evals and observability, with native red teaming and AI governance gates that block releases failing vulnerability checks.                                                                                                                       |
| [promptfoo red teaming](https://www.promptfoo.dev/docs/red-team/) | 🟢 Open source | promptfoo's MIT-licensed red-teaming module scans applications for injection, jailbreaks, data leakage, and authorization flaws. OpenAI announced an agreement to acquire Promptfoo in March 2026. [GitHub](https://github.com/promptfoo/promptfoo) · [Announcement](https://openai.com/index/openai-to-acquire-promptfoo/) |
| [garak](https://github.com/NVIDIA/garak)                          | 🟢 Open source | garak, from NVIDIA, is a generative-AI red-teaming and vulnerability framework whose plugin architecture composes probes, generators, buffs, and detectors into automated attack runs. [Paper](https://arxiv.org/abs/2406.11036)                                                                                            |
| [Giskard](https://github.com/Giskard-AI/giskard-oss)              | 🟢 Open source | Giskard is an open-source testing library for LLM agents and ML models whose scan automatically detects vulnerabilities including prompt injection, harmful content, hallucination, and sycophancy.                                                                                                                         |
| [Moonshot](https://github.com/aiverify-foundation/moonshot)       | 🟢 Open source | Moonshot, from the AI Verify Foundation, is a modular toolkit that combines benchmarking and red teaming of LLM applications behind a single API, CLI, and web UI.                                                                                                                                                          |
| [Rogue](https://github.com/qualifire-dev/rogue)                   | 🔒 Proprietary | Rogue is a source-available AI-agent evaluation and red-teaming platform from Qualifire (Rogue Security); its proprietary license permits personal and internal use but requires separate licensing for commercial hosting.                                                                                                 |
| [Inspect AI](https://github.com/UKGovernmentBEIS/inspect_ai)      | 🟢 Open source | Inspect AI, from the UK AI Security Institute, is an evaluation framework whose solvers, scorers, and sandboxed tool use support safety and adversarial evaluations, including agentic attack scenarios. [Docs](https://inspect.aisi.org.uk)                                                                                |

## LLM Vulnerability Scanners

An **LLM vulnerability scanner** points a fixed or extensible battery of probes at a model or endpoint and reports which weaknesses fire — the "nmap for LLMs" pattern. Scanners emphasize fast, repeatable coverage over the composability of a full [platform or framework](#red-teaming-platforms-and-frameworks).

| Tool                                                            | Availability   | Description                                                                                                                                                                               |
| --------------------------------------------------------------- | -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Agentic Security](https://github.com/msoedov/agentic_security) | 🟢 Open source | Agentic Security is an open-source LLM vulnerability scanner and red-teaming CLI that fuzzes endpoints with jailbreak datasets, multi-step attacks, and stress tests.                     |
| [FuzzyAI](https://github.com/cyberark/FuzzyAI)                  | 🟢 Open source | FuzzyAI, from CyberArk, fuzzes LLM APIs with strategies including adversarial suffixes, genetic search, and encoding to identify jailbreaks and guardrail bypasses.                       |
| [Prompt Fuzzer](https://github.com/prompt-security/ps-fuzz)     | 🟢 Open source | Prompt Fuzzer, from Prompt Security (now a SentinelOne company), tests system prompts with prompt-injection and jailbreak attacks and scores the resulting resilience.                    |
| [promptmap](https://github.com/utkusen/promptmap)               | 🟢 Open source | promptmap is a prompt-injection scanner that tests a custom LLM application's system prompt with rule-based attack cases and reports which ones leak or override it.                      |
| [spikee](https://github.com/ReversecLabs/spikee)                | 🟢 Open source | spikee, from Reversec Labs, is a modular toolkit for testing LLMs, guardrails, and applications against prompt injection and jailbreak attacks and for generating targeted test datasets. |

## Jailbreak and Adversarial Attack Techniques

**Jailbreak and adversarial attack techniques** are named methods (and their reference implementations) for eliciting policy-violating output from an aligned model. This section catalogs the attack algorithms themselves; for suites that measure how often they succeed, see [Jailbreak and Robustness Benchmarks](#jailbreak-and-robustness-benchmarks).

| Tool                                                             | Availability   | Description                                                                                                                                                                                                                     |
| ---------------------------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [llm-attacks (GCG)](https://github.com/llm-attacks/llm-attacks)  | 🟢 Open source | llm-attacks is the reference implementation of Greedy Coordinate Gradient (GCG), which optimizes universal, transferable adversarial suffixes that jailbreak aligned models. [Paper](https://arxiv.org/abs/2307.15043)          |
| [PAIR](https://github.com/patrickrchao/JailbreakingLLMs)         | 🟢 Open source | PAIR (Prompt Automatic Iterative Refinement) uses attacker, target, and judge models to iteratively refine jailbreak prompts in black-box settings. [Paper](https://arxiv.org/abs/2310.08419)                                   |
| [TAP](https://github.com/RICommunity/TAP)                        | 🟢 Open source | TAP (Tree of Attacks with Pruning) extends PAIR with tree-of-thought search and pruning to jailbreak black-box models query-efficiently. [Paper](https://arxiv.org/abs/2312.02119)                                              |
| [AutoDAN](https://github.com/SheltonLiu-N/AutoDAN)               | 🟢 Open source | AutoDAN generates stealthy, human-readable jailbreak prompts via a hierarchical genetic algorithm, evading perplexity-based filters that catch gradient suffixes. [Paper](https://arxiv.org/abs/2310.04451)                     |
| [GPTFuzz](https://github.com/sherdencooper/GPTFuzz)              | 🟢 Open source | GPTFuzz is a black-box jailbreak fuzzer that mutates human-written seed templates and uses a judge model to grow an attack corpus automatically. [Paper](https://arxiv.org/abs/2309.10253)                                      |
| [EasyJailbreak](https://github.com/EasyJailbreak/EasyJailbreak)  | 🟢 Open source | EasyJailbreak provides a common interface for implementing, constructing, and evaluating multiple jailbreak methods. [Paper](https://arxiv.org/abs/2403.12171)                                                                  |
| [DeepInception](https://github.com/tmlr-group/DeepInception)     | 🟢 Open source | DeepInception is a prompt-only jailbreak that nests a model inside layered fictional scenarios to erode its safety guardrails. [Paper](https://arxiv.org/abs/2311.03191)                                                        |
| [PromptInject](https://github.com/agencyenterprise/PromptInject) | 🟢 Open source | PromptInject is the framework accompanying the "Ignore Previous Prompt" paper, quantifying goal hijacking and prompt leaking via mask-based iterative adversarial prompt composition. [Paper](https://arxiv.org/abs/2211.09527) |
| [ArtPrompt](https://github.com/uw-nsl/ArtPrompt)                 | 🟢 Open source | ArtPrompt is an ASCII-art-based jailbreak that hides unsafe words in text art to bypass token-level safety filters. [Paper](https://arxiv.org/abs/2402.11753)                                                                   |

## Prompt Injection and Indirect Injection

**Prompt injection** overrides an application's intended instructions with attacker-controlled text; **indirect injection** delivers that text through content the model retrieves (web pages, documents, emails) rather than the user turn. Tools here detect, reproduce, and benchmark both variants.

| Tool                                                                                   | Availability   | Description                                                                                                                                                                                                          |
| -------------------------------------------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Open-Prompt-Injection](https://github.com/liu00222/Open-Prompt-Injection)             | 🟢 Open source | Open-Prompt-Injection is a research framework implementing standardized prompt-injection attacks and defenses for reproducible evaluation. [Paper](https://arxiv.org/abs/2310.12815)                                 |
| [BIPIA](https://github.com/microsoft/BIPIA)                                            | 🟢 Open source | BIPIA, from Microsoft, benchmarks indirect prompt injection across email QA, web QA, table QA, summarization, and code QA, with black-box and white-box defense baselines. [Paper](https://arxiv.org/abs/2312.14197) |
| [HouYi](https://github.com/LLMSecurity/HouYi)                                          | 🟢 Open source | HouYi is a black-box prompt-injection attack framework that systematically composes a framework, separator, and disruptor to hijack LLM-integrated applications. [Paper](https://arxiv.org/abs/2306.05499)           |
| [Tensor Trust](https://github.com/HumanCompatibleAI/tensor-trust)                      | 🟢 Open source | Tensor Trust is a prompt-injection attack-and-defense game from UC Berkeley whose gameplay produced a public dataset of human-crafted injections and defenses. [Paper](https://arxiv.org/abs/2311.01011)             |
| [deepset prompt-injections](https://huggingface.co/datasets/deepset/prompt-injections) | 🟢 Open data   | The deepset prompt-injections dataset is an Apache-2.0 labeled corpus of injection and benign prompts for training and evaluating injection classifiers.                                                             |
| [Lakera PINT Benchmark](https://github.com/lakeraai/pint-benchmark)                    | 🟢 Open source | PINT (Prompt Injection Test), from Lakera, provides a dataset and harness for evaluating prompt-injection detectors without training on the test set.                                                                |

## Classic Adversarial Robustness Libraries

**Classic adversarial robustness libraries** predate the LLM era and attack traditional ML and NLP models with evasion, poisoning, extraction, and inference attacks. They remain relevant for classifiers, embedding models, and vision components inside AI systems.

| Tool                                                                                           | Availability   | Description                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Adversarial Robustness Toolbox](https://github.com/Trusted-AI/adversarial-robustness-toolbox) | 🟢 Open source | ART, from the Linux Foundation AI & Data (originally IBM), provides evasion, poisoning, extraction, and inference attacks and defenses for multiple machine-learning frameworks and data modalities. |
| [Foolbox](https://github.com/bethgelab/foolbox)                                                | 🟢 Open source | Foolbox creates adversarial examples against PyTorch, TensorFlow, and JAX models using gradient-based, decision-based, and score-based attacks.                                                      |
| [CleverHans](https://github.com/cleverhans-lab/cleverhans)                                     | 🟢 Open source | CleverHans provides reference adversarial-example attack implementations for benchmarking model robustness.                                                                                          |
| [TextAttack](https://github.com/QData/TextAttack)                                              | 🟢 Open source | TextAttack is a framework for adversarial attacks, data augmentation, and adversarial training in NLP, with many recipe-based text attacks.                                                          |
| [OpenAttack](https://github.com/thunlp/OpenAttack)                                             | 🟢 Open source | OpenAttack, from THUNLP, is a textual adversarial attack toolkit supporting sentence-, word-, and character-level attacks and attack evaluation.                                                     |
| [AdvBox](https://github.com/advboxes/AdvBox)                                                   | 🟢 Open source | AdvBox, from Baidu, is a toolbox for generating adversarial examples and testing the robustness of models across multiple deep-learning frameworks.                                                  |
| [Armory](https://github.com/twosixlabs/armory)                                                 | 🟢 Open source | Armory, from Two Six Technologies, is an adversarial-ML evaluation testbed built for the DARPA GARD program, orchestrating scenario-based robustness experiments.                                    |

## Commercial AI Red Teaming Platforms

**Commercial AI red teaming platforms** provide managed, continuously updated attack coverage, reporting, and often runtime defenses, targeting security and compliance teams that need governance and support beyond open-source tooling.

| Tool                                                                                                                                                                                                  | Availability  | Description                                                                                                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Check Point AI Red Teaming](https://www.checkpoint.com/ai-security/ai-red-teaming/)                                                                                                                  | 🔒 Commercial | Check Point AI Red Teaming, built from the Lakera acquisition, runs adversarial assessments against models and agents and draws attack intelligence from the Gandalf community.                      |
| [Mindgard](https://mindgard.ai)                                                                                                                                                                       | 🔒 Commercial | Mindgard is an automated AI red-teaming and offensive-security platform that maps attack surfaces and continuously tests models, agents, applications, and infrastructure.                           |
| [HiddenLayer](https://www.hiddenlayer.com/solutions/red-teaming)                                                                                                                                      | 🔒 Commercial | HiddenLayer provides automated red teaming and attack simulation for generative, agentic, and predictive AI, alongside model scanning and runtime detection and response.                            |
| [Cisco AI Defense](https://www.cisco.com/site/us/en/products/security/ai-defense/index.html)                                                                                                          | 🔒 Commercial | Cisco AI Defense, built on the Robust Intelligence acquisition, provides algorithmic red teaming and runtime guardrails for enterprise AI applications.                                              |
| [Haize Labs](https://haizelabs.com/)                                                                                                                                                                  | 🔒 Commercial | Haize Labs builds domain-specific agents with a proprietary Reliability Harness that combines simulation testing, adversarial red teaming, guardrails, and evaluation judges.                        |
| [Prisma AIRS AI Red Teaming](https://www.paloaltonetworks.com/ai-security/ai-red-teaming.html)                                                                                                        | 🔒 Commercial | Prisma AIRS AI Red Teaming, incorporating technology from Palo Alto Networks' Protect AI acquisition, runs adaptive adversarial assessments against AI applications and agents.                      |
| [Adversa AI](https://adversa.ai/ai-red-teaming-agentic-ai/)                                                                                                                                           | 🔒 Commercial | Adversa AI provides continuous red teaming, threat modeling, and remediation for custom AI agents, applications, models, APIs, and MCP-connected infrastructure.                                     |
| [F5 AI Red Team](https://investors.f5.com/news/news-details/2026/F5-Labs-Sets-New-Standard-for-AI-Security-Benchmarking-With-Model-Risk-Leaderboards-and-Threat-Intelligence-02-26-2026/default.aspx) | 🔒 Commercial | F5 AI Red Team, built from the CalypsoAI acquisition, uses adversarial agents to test models and applications for prompt injection, jailbreaks, and other AI-specific vulnerabilities.               |
| [Zscaler Automated AI Red Teaming](https://www.zscaler.com/products-and-solutions/continuous-automated-red-teaming)                                                                                   | 🔒 Commercial | Zscaler Automated AI Red Teaming, built from the SPLX acquisition, continuously tests GenAI applications with customizable probes and integrates findings into development and governance workflows. |
| [Enkrypt AI](https://www.enkryptai.com)                                                                                                                                                               | 🔒 Commercial | Enkrypt AI offers automated red teaming, risk assessment, and guardrails for LLM applications, with compliance-oriented reporting.                                                                   |
| [Gray Swan Shade](https://www.grayswan.ai/solutions/platform/shade)                                                                                                                                   | 🔒 Commercial | Shade runs adaptive adversarial campaigns against models, agents, guardrails, and deployment contexts using attack intelligence from Gray Swan's Arena research environment.                         |
| [Repello AI ARTEMIS](https://repello.ai)                                                                                                                                                              | 🔒 Commercial | ARTEMIS is Repello AI's automated red-teaming engine for continuous adversarial testing of LLM applications, RAG pipelines, and agentic systems, with CI/CD integration.                             |
| [Patronus AI](https://www.patronus.ai)                                                                                                                                                                | 🔒 Commercial | Patronus AI's evaluation platform supports OWASP-aligned adversarial datasets, custom attack generation, evaluators, and simulated environments for testing AI models and agents.                    |

## Guardrails and Runtime Defenses

**Guardrails** validate LLM inputs and outputs at runtime and block policy-violating traffic in production. Guardrails are the runtime counterpart to offline red teaming: you red-team to find failure modes, then deploy guardrails to catch them live.

| Tool                                                                                                   | Availability    | Description                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------ | --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails)                                           | 🟢 Open source  | NeMo Guardrails is NVIDIA's toolkit for programmable guardrails (via Colang) on conversational systems, with topic control, jailbreak detection, and fact-checking rails.        |
| [Guardrails AI](https://github.com/guardrails-ai/guardrails)                                           | 🟢 Open source  | Guardrails AI is a Python framework for input/output validation, with a community [Guardrails Hub](https://guardrailsai.com/hub) of validators for injection, PII, and toxicity. |
| [LlamaFirewall](https://github.com/meta-llama/PurpleLlama/tree/main/LlamaFirewall)                     | 🟢 Open source  | LlamaFirewall, from Meta, is an open-source guardrail framework for agentic systems that combines PromptGuard, agent-alignment checks, and code-safety scanning.                 |
| [Invariant Guardrails](https://github.com/invariantlabs-ai/invariant)                                  | 🟢 Open source  | Invariant Guardrails is an Apache-2.0 rule-based layer for agentic systems that enforces policies over messages and tool calls; Snyk acquired Invariant Labs in 2025.            |
| [Llama Guard](https://github.com/meta-llama/PurpleLlama)                                               | 🟠 Open weights | Llama Guard is Meta's family of downloadable safety-classifier models for input and output moderation, released under Meta's community license as part of Purple Llama.          |
| [Prompt Guard](https://huggingface.co/meta-llama/Prompt-Guard-86M)                                     | 🟠 Open weights | Prompt Guard, from Meta, is an 86M-parameter downloadable classifier that flags prompt-injection and jailbreak strings in user inputs and retrieved content.                     |
| [ShieldGemma](https://huggingface.co/google/shieldgemma-2b)                                            | 🟠 Open weights | ShieldGemma, from Google, is a family of Gemma-based safety-classifier models for filtering harmful content in prompts and responses.                                            |
| [Granite Guardian](https://github.com/ibm-granite/granite-guardian)                                    | 🟢 Open source  | Granite Guardian, from IBM, is an Apache-2.0 family of downloadable guardrail models for detecting harm, jailbreaks, and RAG groundedness and relevance risks.                   |
| [Check Point AI Agent Security](https://www.checkpoint.com/ai-security/ai-agent-security/)             | 🔒 Commercial   | Check Point AI Agent Security, formerly Lakera Guard, enforces runtime policies across prompts, responses, external content, and agent tool calls.                               |
| [Azure AI Content Safety](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview) | 🔒 Commercial   | Azure AI Content Safety provides content moderation plus Prompt Shields for direct and indirect prompt attacks, groundedness detection, and agent task-adherence checks.         |
| [Google Model Armor](https://docs.cloud.google.com/model-armor/overview)                               | 🔒 Commercial   | Model Armor is Google Cloud's service for screening LLM prompts and responses for injection, jailbreaks, sensitive data, malicious URLs, and harmful content.                    |
| [Amazon Bedrock Guardrails](https://aws.amazon.com/bedrock/guardrails/)                                | 🔒 Commercial   | Amazon Bedrock Guardrails applies configurable safety policies — content filters, denied topics, and contextual grounding checks — to Bedrock applications.                      |
| [OpenAI Moderation](https://developers.openai.com/api/docs/guides/moderation)                          | 🔒 Commercial   | The OpenAI Moderation endpoint is a free hosted API for text and image safety classification.                                                                                    |

## Agent Security and Tool-Use Testing

**Agent security testing** targets the attack surface unique to tool-using, autonomous agents: indirect prompt injection through tool outputs, unsafe tool invocation, and multi-step goal hijacking. For static task suites, cross-reference the benchmark sections below.

| Tool                                                                       | Availability        | Description                                                                                                                                                                                                                                |
| -------------------------------------------------------------------------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [AgentDojo](https://github.com/ethz-spylab/agentdojo)                      | 🟢 Open source      | AgentDojo, from ETH Zurich, is a dynamic environment for evaluating prompt-injection attacks and defenses against tool-using LLM agents on realistic tasks. [Paper](https://arxiv.org/abs/2406.13352)                                      |
| [InjecAgent](https://github.com/uiuc-kang-lab/InjecAgent)                  | 🟢 Open source      | InjecAgent is a benchmark for indirect prompt-injection attacks against tool-integrated agents, measuring both direct harm and data-exfiltration outcomes. [Paper](https://arxiv.org/abs/2403.02691)                                       |
| [Agent Security Bench](https://github.com/agiresearch/ASB)                 | 🟢 Open source      | Agent Security Bench (ASB) formalizes and benchmarks a broad range of attacks and defenses on LLM agents, including direct/indirect injection, memory poisoning, and backdoors. [Paper](https://arxiv.org/abs/2410.02644)                  |
| [ToolEmu](https://github.com/ryoungj/ToolEmu)                              | 🟢 Open source      | ToolEmu uses an LLM to emulate tool execution so agents can be stress-tested for risky behavior in high-stakes scenarios without real side effects. [Paper](https://arxiv.org/abs/2309.15817)                                              |
| [Agentic Radar](https://github.com/splx-ai/agentic-radar)                  | 🟢 Open source      | Agentic Radar, created by SPLX before its Zscaler acquisition, maps an agentic workflow's tools and dependencies and probes it for security weaknesses.                                                                                    |
| [AgentHarm](https://huggingface.co/datasets/ai-safety-institute/AgentHarm) | 📖 Public benchmark | AgentHarm, from the UK AI Security Institute and Gray Swan AI, measures harmful multi-step agent behavior and jailbreak transfer; its license restricts use to improving AI safety and security. [Paper](https://arxiv.org/abs/2410.09024) |
| [Memory Poisoning Lab](https://github.com/RishabhPande/memory-poison-lab) | 🟢 Open source | Memory Poisoning Lab demonstrates persistent-memory poisoning, origin-aware defenses and repair on local backends using synthetic targets and a scripted deterministic agent, not real-LLM safety measurements. |

## Jailbreak and Robustness Benchmarks

**Jailbreak benchmarks** measure how reliably attacks defeat a model's safety training, with fixed prompt sets, scoring judges, and leaderboards. They turn one-off attacks into comparable, trackable metrics over time.

| Tool                                                                            | Availability   | Description                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [JailbreakBench](https://github.com/JailbreakBench/jailbreakbench)              | 🟢 Open source | JailbreakBench is an open robustness benchmark for jailbreaking, with a standardized dataset, evaluation pipeline, leaderboard, and artifact repository. [Paper](https://arxiv.org/abs/2404.01318)                         |
| [HarmBench](https://github.com/centerforaisafety/HarmBench)                     | 🟢 Open source | HarmBench provides a standardized set of harmful behaviors and a validation classifier for comparing attack success and refusal robustness across methods. [Paper](https://arxiv.org/abs/2402.04249)                       |
| [StrongREJECT](https://github.com/alexandrasouly/strongreject)                  | 🟢 Open source | StrongREJECT pairs forbidden prompts with an autograder that scores refusal, specificity, and convincingness to measure whether a jailbreak produces actionable harmful content. [Paper](https://arxiv.org/abs/2402.10260) |
| [JailbreakV-28K](https://huggingface.co/datasets/JailbreakV-28K/JailBreakV-28k) | 🟢 Open data   | JailbreakV-28K contains 20,000 text-based transfer attacks and 8,000 image-based attacks for testing jailbreak robustness in multimodal large language models. [Paper](https://arxiv.org/abs/2404.03027)                   |
| [SORRY-Bench](https://github.com/SORRY-Bench/sorry-bench)                       | 🟢 Open source | SORRY-Bench evaluates refusal behavior with 440 balanced instructions across 44 unsafe topics and 20 linguistic augmentations. [Paper](https://arxiv.org/abs/2406.14598)                                                   |
| [h4rm3l](https://github.com/mdoumbouya/h4rm3l)                                  | 🟢 Open source | h4rm3l is a domain-specific language and benchmark for composing novel jailbreak attacks programmatically and measuring their success. [Paper](https://arxiv.org/abs/2408.04811)                                           |

## Safety, Harm, and Trustworthiness Benchmarks

**Safety and trustworthiness benchmarks** measure model behavior on harmful-content refusal, over-refusal, bias, toxicity, privacy, and dangerous-capability proxies. They complement jailbreak benchmarks by scoring baseline safety, not just resistance to attack.

| Tool                                                                                        | Availability      | Description                                                                                                                                                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AILuminate](https://github.com/mlcommons/ailuminate)                                       | 🟢 Open source    | AILuminate is MLCommons' safety-benchmark family covering 12 hazard categories. Its Apache-2.0 repository provides an offline demo; practice and official tests use separately licensed or confidential prompt sets. [Website](https://mlcommons.org/ailuminate/)                                                    |
| [DecodingTrust](https://github.com/AI-secure/DecodingTrust)                                 | 🟢 Open source    | DecodingTrust assesses toxicity, stereotype bias, adversarial robustness, out-of-distribution robustness, privacy, machine ethics, and fairness (NeurIPS 2023 Outstanding Paper). [Paper](https://arxiv.org/abs/2306.11698)                                                                                          |
| [TrustLLM](https://github.com/HowieHwong/TrustLLM)                                          | 🟢 Open source    | TrustLLM benchmarks trustworthiness across truthfulness, safety, fairness, robustness, privacy, and machine ethics. [Paper](https://arxiv.org/abs/2401.05561)                                                                                                                                                        |
| [SafetyBench](https://github.com/thu-coai/SafetyBench)                                      | 🟢 Open source    | SafetyBench is a multiple-choice LLM safety evaluation across seven harm categories in English and Chinese. [Paper](https://arxiv.org/abs/2309.07045)                                                                                                                                                                |
| [Do-Not-Answer](https://github.com/Libr-AI/do-not-answer)                                   | 🟢 Open source    | Do-Not-Answer is a dataset of questions responsible models should refuse, with an evaluation protocol for safeguard effectiveness. [Paper](https://arxiv.org/abs/2308.13387)                                                                                                                                         |
| [XSTest](https://github.com/paul-rottger/xstest)                                            | 🟢 Open source    | XSTest tests exaggerated safety (over-refusal) using safe prompts that superficially resemble unsafe ones. [Paper](https://arxiv.org/abs/2308.01263)                                                                                                                                                                 |
| [ToxiGen](https://huggingface.co/datasets/toxigen/toxigen-data)                             | 📖 Public dataset | ToxiGen is a publicly downloadable dataset of synthetic implicit toxic and benign statements mentioning 13 minority groups; its dataset card specifies no license, and Microsoft has archived the original code repository. [Code](https://github.com/microsoft/TOXIGEN) · [Paper](https://arxiv.org/abs/2203.09509) |
| [WMDP](https://github.com/centerforaisafety/wmdp)                                           | 🟢 Open source    | WMDP (Weapons of Mass Destruction Proxy) measures hazardous knowledge in biosecurity, cybersecurity, and chemistry as a proxy for dangerous capabilities. [Paper](https://arxiv.org/abs/2403.03218)                                                                                                                  |
| [CyberSecEval](https://github.com/meta-llama/PurpleLlama/tree/main/CybersecurityBenchmarks) | 🟢 Open source    | CyberSecEval, part of Meta's Purple Llama project, benchmarks cybersecurity risks and capabilities including insecure code generation, prompt injection, cyberattack helpfulness, and defensive tasks.                                                                                                               |
| [SALAD-Bench](https://github.com/OpenSafetyLab/SALAD-BENCH)                                 | 🟢 Open source    | SALAD-Bench is a hierarchical safety benchmark for LLMs, attacks, and defenses, paired with an MD-Judge evaluator across a structured harm taxonomy. [Paper](https://arxiv.org/abs/2402.05044)                                                                                                                       |
| [BeaverTails](https://github.com/PKU-Alignment/beavertails)                                 | 🟢 Open source    | BeaverTails, from PKU-Alignment, is a QA dataset with separate helpfulness and harmlessness annotations for safety alignment research. [Paper](https://arxiv.org/abs/2307.04657)                                                                                                                                     |

## Attack Datasets and Prompt Corpora

**Attack datasets** are the raw material of red teaming: collections of jailbreak prompts, harmful instructions, and injection payloads used to seed scanners, train classifiers, and reproduce results. Availability markers describe the dataset artifact.

| Tool                                                                                              | Availability      | Description                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [In-The-Wild Jailbreak Prompts](https://github.com/verazuo/jailbreak_llms)                        | 🟢 Open data      | In-The-Wild Jailbreak Prompts collects 15,000+ jailbreak prompts, including DAN-family prompts, from public platforms for studying attacks observed in practice. [Paper](https://arxiv.org/abs/2308.03825)                |
| [AdvBench](https://github.com/llm-attacks/llm-attacks/tree/main/data/advbench)                    | 🟢 Open data      | AdvBench is the harmful-behaviors and harmful-strings dataset introduced with GCG as a target set for jailbreak research. [Paper](https://arxiv.org/abs/2307.15043)                                                       |
| [HackAPrompt Dataset](https://huggingface.co/datasets/hackaprompt/hackaprompt-dataset)            | 🟢 Open data      | HackAPrompt contains 600,000+ adversarial prompts submitted to a global prompt-hacking competition; the MIT-licensed dataset requires accepting Hugging Face access conditions. [Paper](https://arxiv.org/abs/2311.16119) |
| [HarmfulQA](https://huggingface.co/datasets/declare-lab/HarmfulQA)                                | 🟢 Open data      | HarmfulQA, from DeCLaRe Lab, is an Apache-2.0 dataset of harmful questions and red-teaming conversations created with the Chain of Utterances method. [Paper](https://arxiv.org/abs/2308.09662)                           |
| [ToxicChat](https://huggingface.co/datasets/lmsys/toxic-chat)                                     | 📖 Public dataset | ToxicChat, from LMSYS, contains toxicity and jailbreak labels for real user queries to a chatbot; prompts and outputs are licensed CC-BY-NC-4.0. [Paper](https://arxiv.org/abs/2310.17389)                                |
| [MM-SafetyBench](https://github.com/isXinLiu/MM-SafetyBench)                                      | 📖 Public dataset | MM-SafetyBench evaluates multimodal-LLM safety against query-relevant image-based jailbreaks; its dataset is restricted to noncommercial research under CC-BY-NC-4.0. [Paper](https://arxiv.org/abs/2311.17600)           |
| [ForbiddenQuestions](https://github.com/verazuo/jailbreak_llms/tree/main/data/forbidden_question) | 🟢 Open data      | ForbiddenQuestions pairs policy-violating questions with jailbreak prompts to measure attack success across scenarios. [Paper](https://arxiv.org/abs/2308.03825)                                                          |

## Model and ML Supply-Chain Security Scanning

**Model and supply-chain scanners** inspect model artifacts and dependencies for threats that live below the prompt layer: malicious deserialization in serialized weights, backdoors, and unsafe file formats. This is AppSec for the ML pipeline rather than behavioral testing.

| Tool                                                                                                 | Availability   | Description                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------- | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [ModelScan](https://github.com/protectai/modelscan)                                                  | 🟢 Open source | ModelScan scans model files, including pickle, HDF5, and SavedModel formats, for code that executes on load and other model-serialization threats.                   |
| [picklescan](https://github.com/mmaitre314/picklescan)                                               | 🟢 Open source | picklescan analyzes Python pickle files for suspicious imports and opcodes, and is integrated into Hugging Face Hub's malware scanning.                              |
| [Fickling](https://github.com/trailofbits/fickling)                                                  | 🟢 Open source | Fickling, from Trail of Bits, is a decompiler, static analyzer, and bytecode rewriter for pickle files, used to detect and craft malicious payloads for testing.     |
| [safetensors](https://github.com/safetensors/safetensors)                                            | 🟢 Open source | safetensors is a safe serialization format for model weights that avoids the arbitrary-code-execution behavior of pickle-based checkpoints.                          |
| [HiddenLayer Model Scanner](https://www.hiddenlayer.com/solutions/model-scanning)                    | 🔒 Commercial  | HiddenLayer's Model Scanner statically inspects model artifacts for malware, backdoors, and integrity issues before they enter production.                           |
| [Prisma AIRS AI Model Security](https://www.paloaltonetworks.com/ai-security/ai-model-security.html) | 🔒 Commercial  | Prisma AIRS AI Model Security, incorporating Protect AI technology, scans model architecture, weights, operators, dependencies, and embedded code before deployment. |

## Standards, Taxonomies, and Vulnerability Databases

**Standards and taxonomies** give red-teaming findings a shared vocabulary and a place to file them: threat frameworks, risk-management guidance, and public incident/vulnerability databases. Use these to structure reports and map coverage.

| Tool                                                                                        | Availability        | Description                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------- | ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [OWASP Top 10 for LLM Applications](https://genai.owasp.org)                                | 📖 Public resource  | The OWASP Top 10 for LLM Applications is a community-maintained risk list covering prompt injection, sensitive-information disclosure, supply-chain weaknesses, and other GenAI application risks. |
| [MITRE ATLAS](https://atlas.mitre.org)                                                      | 📖 Public resource  | MITRE ATLAS is an ATT&CK-style knowledge base of adversary tactics and techniques against AI systems, backed by real-world case studies.                                                           |
| [OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/) | 📖 Public resource  | The OWASP Machine Learning Security Top 10 catalogs risks to classic ML systems, such as data poisoning and model inversion.                                                                       |
| [AI Vulnerability Database](https://avidml.org)                                             | 📖 Public database  | AVID is a public database and taxonomy of AI failure modes and vulnerabilities, providing a common reporting schema for the community.                                                             |
| [AI Incident Database](https://incidentdatabase.ai)                                         | 📖 Public database  | The AI Incident Database, from the Responsible AI Collaborative, indexes reported real-world AI harms and near-misses to inform threat modeling.                                                   |
| [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)  | 📖 Public framework | The NIST AI RMF is a voluntary U.S. framework for governing AI risk, with a Generative AI profile addressing risks specific to generative systems.                                                 |
| [Google Secure AI Framework (SAIF)](https://safety.google/safety/saif/)                     | 📖 Public framework | SAIF is Google's published conceptual framework and risk map for securing AI systems across the development and deployment lifecycle.                                                              |

## Discontinued and Historical Tools

Influential tools and companies that are **no longer independently available, no longer maintained, or superseded by a current product**. Kept for the historical record and to prevent stale recommendations. Status notes reflect the last-reviewed date above; corrections welcome.

| Tool                                                                                                                                                              | Former category           | Status                                                                                                                                                                                                                                                                                                                                                                        |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Counterfit](https://github.com/Azure/counterfit)                                                                                                                 | Adversarial ML tooling    | Counterfit remains public and unarchived, but its latest release dates to November 2022 and its latest functional code changes to April 2023; [PyRIT](https://github.com/microsoft/PyRIT) is Microsoft's current generative-AI red-teaming framework.                                                                                                                         |
| [LLMFuzzer](https://github.com/mnns/LLMFuzzer)                                                                                                                    | LLM vulnerability scanner | LLMFuzzer's maintainers explicitly mark the project as unmaintained and invite users to fork it.                                                                                                                                                                                                                                                                              |
| [Vigil](https://github.com/deadbits/vigil-llm)                                                                                                                    | LLM vulnerability scanner | Vigil is not formally archived, but its latest release was in December 2023, its latest code update was in January 2024, and its README describes it as alpha research software.                                                                                                                                                                                              |
| [Rebuff](https://github.com/protectai/rebuff)                                                                                                                     | Prompt-injection defense  | Protect AI archived Rebuff in May 2025; the repository remains available under Apache-2.0.                                                                                                                                                                                                                                                                                    |
| [LLM Guard](https://github.com/protectai/llm-guard)                                                                                                               | Runtime defense           | Protect AI archived LLM Guard in July 2026 and states that the project and associated models are no longer developed or maintained.                                                                                                                                                                                                                                           |
| [Robust Intelligence](https://www.cisco.com/site/us/en/products/security/ai-defense/robust-intelligence-is-part-of-cisco/index.html)                              | Red-teaming platform      | Cisco acquired Robust Intelligence in October 2024; its algorithmic red teaming is now part of [Cisco AI Defense](https://www.cisco.com/site/us/en/products/security/ai-defense/index.html).                                                                                                                                                                                  |
| [Prompt Security](https://www.sentinelone.com/platform/securing-ai-prompt/)                                                                                       | Runtime defense platform  | SentinelOne completed its acquisition of Prompt Security in 2025; Prompt Security now operates within the SentinelOne Singularity platform.                                                                                                                                                                                                                                   |
| [Protect AI](https://www.paloaltonetworks.com/company/press/2025/palo-alto-networks-completes-acquisition-of-protect-ai)                                          | AI security platform      | Palo Alto Networks acquired Protect AI in July 2025 and integrated its model scanning, red teaming, and runtime technology into [Prisma AIRS](https://www.paloaltonetworks.com/prisma/prisma-ai-runtime-security).                                                                                                                                                            |
| [CalypsoAI](https://investors.f5.com/news/news-details/2025/F5-to-Acquire-CalypsoAI-to-Bring-Advanced-AI-Guardrails-to-Large-Enterprises-09-11-2025/default.aspx) | AI security platform      | F5 announced its agreement to acquire CalypsoAI in September 2025; F5 now describes [F5 AI Red Team and F5 AI Guardrails](https://investors.f5.com/news/news-details/2026/F5-Labs-Sets-New-Standard-for-AI-Security-Benchmarking-With-Model-Risk-Leaderboards-and-Threat-Intelligence-02-26-2026/default.aspx) as generally available products stemming from the acquisition. |
| [SPLX](https://www.zscaler.com/press/zscaler-secures-enterprise-ai-lifecycle-acquisition-innovative-ai-security-pioneer-splx)                                     | AI security platform      | Zscaler acquired SPLX in November 2025 and integrated its discovery, automated red teaming, and governance technology into Zscaler AI Security.                                                                                                                                                                                                                               |
| [Lakera](https://www.checkpoint.com/press-releases/check-point-acquires-lakera-to-deliver-end-to-end-ai-security-for-enterprises/)                                | AI security platform      | Check Point completed its acquisition of Lakera in October 2025; Lakera Red and Lakera Guard were succeeded by Check Point AI Red Teaming and AI Agent Security.                                                                                                                                                                                                              |
| [Invariant Labs](https://snyk.io/news/snyk-acquires-invariant-labs-to-accelerate-agentic-ai-security-innovation/)                                                 | Agent guardrails          | Snyk acquired Invariant Labs in June 2025; the Apache-2.0 Invariant Guardrails repository remains public while its technology contributes to Snyk's AI security products and research.                                                                                                                                                                                        |

## Key Papers and Concepts

Foundational reading for anyone building or choosing AI red-teaming tooling — cite these for the underlying methods.

- **Universal adversarial suffixes** — [Universal and Transferable Adversarial Attacks on Aligned Language Models](https://arxiv.org/abs/2307.15043) (Zou et al., 2023). Introduced GCG and the AdvBench target set.
- **How safety training fails** — [Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483) (Wei et al., 2023). Competing objectives and mismatched generalization as root causes of jailbreaks.
- **Automated jailbreaks** — [Jailbreaking Black Box Large Language Models in Twenty Queries](https://arxiv.org/abs/2310.08419) (Chao et al., 2023). The PAIR attack.
- **Direct prompt injection** — [Ignore Previous Prompt: Attack Techniques for Language Models](https://arxiv.org/abs/2211.09527) (Perez & Ribeiro, 2022). Goal hijacking and prompt leaking.
- **Indirect prompt injection** — [Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection](https://arxiv.org/abs/2302.12173) (Greshake et al., 2023).
- **Standardized red teaming** — [HarmBench: A Standardized Evaluation Framework for Automated Red Teaming and Robust Refusal](https://arxiv.org/abs/2402.04249) (Mazeika et al., 2024).
- **In-the-wild jailbreaks** — ["Do Anything Now": Characterizing and Evaluating In-The-Wild Jailbreak Prompts on LLMs](https://arxiv.org/abs/2308.03825) (Shen et al., 2023).
- **Security probing frameworks** — [garak: A Framework for Security Probing Large Language Models](https://arxiv.org/abs/2406.11036) (Derczynski et al., 2024).
- **Jailbreak scoring** — [A StrongREJECT for Empty Jailbreaks](https://arxiv.org/abs/2402.10260) (Souly et al., 2024). A refusal, specificity, and convincingness rubric for scoring attack outputs.

## Glossary

Short definitions of terms used throughout this list.

- **Red teaming** — deliberately attacking an AI system (jailbreaks, prompt injection, extraction) to find failures before adversaries do; the offline counterpart to runtime guardrails.
- **Jailbreak** — a prompt or technique that circumvents a model's safety alignment so it produces content it was trained to refuse.
- **Prompt injection** — overriding an application's intended instructions with attacker-controlled text supplied in the input.
- **Indirect prompt injection** — prompt injection delivered through content the model retrieves (web pages, documents, emails, tool output) rather than the user's direct message.
- **Adversarial suffix** — an optimized string appended to a prompt that reliably triggers unsafe behavior, often transferable across models (see GCG).
- **Transfer attack** — an attack crafted against one model that also succeeds against others without modification.
- **Attack success rate (ASR)** — the fraction of attack attempts that achieve the adversary's goal; the primary metric in jailbreak benchmarks.
- **Guardrail** — a runtime check that validates or blocks model inputs/outputs before they reach users or tools.
- **Refusal / over-refusal** — a model declining a request; over-refusal (exaggerated safety) is when it wrongly refuses benign requests.
- **Data exfiltration** — an attack that causes a model or agent to leak system prompts, secrets, or private context.
- **Model extraction** — stealing a model's parameters or behavior by querying it, a supply-chain and IP threat.
- **Membership inference** — determining whether a specific record was in a model's training data, a privacy attack.
- **Model-serialization attack** — malicious code embedded in a serialized model file (e.g., pickle) that executes when the model is loaded.
- **OWASP Top 10 for LLM Applications** — a community-maintained list and taxonomy of prominent LLM application risks.
- **MITRE ATLAS** — an ATT&CK-style knowledge base of adversarial tactics and techniques against AI systems.
- **Open weights** — model weights that are downloadable but released under a non-OSI license (e.g., Llama community license).
- **Open data** — a dataset released under terms that permit reuse and redistribution; data licenses need not be OSI software licenses.
- **Open core** — a business model pairing an open-source component with a commercial platform.

## Frequently Asked Questions

**What are AI red teaming tools?**
AI red teaming tools are software for adversarially testing AI systems — LLMs, RAG pipelines, agents, and multimodal models — to surface vulnerabilities such as jailbreaks, prompt injection, data leakage, and harmful-content generation before attackers exploit them. They range from open-source frameworks and scanners run in CI to managed commercial platforms and runtime guardrails.

**What is the difference between red teaming and guardrails?**
Red teaming is offline, adversarial testing: you attack the system to discover failure modes. Guardrails are the runtime defense: input/output checks that block attacks in production. A mature program uses both — red-team to learn what fails (with tools like DeepTeam, PyRIT, or garak), then deploy guardrails (NeMo Guardrails, Llama Guard, or Check Point AI Agent Security) for those failure modes and re-test.

**What is the difference between a jailbreak and a prompt injection?**
A jailbreak defeats the model's own safety alignment to make it produce restricted content. A prompt injection overrides the _application's_ instructions with attacker text — either directly in the user input or indirectly through retrieved content — and is dangerous even when no safety policy is violated, for example by exfiltrating data or misusing tools.

**Which AI red teaming tools are open source?**
Open-source options in this list include DeepTeam, PyRIT, garak, promptfoo, Giskard, and Moonshot for frameworks; the Adversarial Robustness Toolbox and TextAttack for classic ML; and JailbreakBench, HarmBench, and StrongREJECT for benchmarking. Every entry carries an availability marker for open source/open data (🟢), open weights (🟠), open core (🔵), commercial/proprietary (🔒), or a public benchmark, dataset, standard, or resource (📖).

**How do I red-team an LLM application?**
Start with an automated framework (DeepTeam, garak, PyRIT, or promptfoo's red-team module) to scan for jailbreaks, prompt injection, PII leakage, and harmful content, mapping findings to the [OWASP Top 10 for LLM Applications](https://genai.owasp.org). Reproduce high-severity findings with specific attack techniques, add runtime guardrails for the failure modes you confirm, and re-run the suite in CI so regressions are caught. For agents, add tool-use and indirect-injection tests (AgentDojo, InjecAgent).

**What is the OWASP Top 10 for LLM Applications?**
It is a community-maintained risk list for LLM applications, including prompt injection, sensitive-information disclosure, supply-chain risks, and improper output handling. Tools such as DeepTeam and promptfoo map findings to it, making the list a useful shared taxonomy for scoping red-teaming work.

**How should I cite this list?**
See [Citing This List](#citing-this-list) for a citation template, BibTeX, and the machine-readable `CITATION.cff`. When citing an individual tool, always prefer that tool's own repository, documentation, or paper — linked in each entry — as the primary source.

## Methodology

How this list is built and maintained. This section exists so readers (and AI systems) can judge how much to trust it.

- **Scope.** Tools whose primary purpose is adversarially testing, attacking, defending, or benchmarking the security and safety of AI systems — generative AI first (LLMs, RAG, agents, multimodal), plus classic adversarial ML. General evaluation, observability, and MLOps tools are out of scope unless they have first-class red-teaming or security features.
- **Inclusion criteria.** Open-source projects should show activity within roughly the last year or have lasting reference value (canonical attacks, benchmarks, and foundational libraries are kept regardless of age). Commercial products must be generally available. Discontinued tools move to the [historical section](#discontinued-and-historical-tools) rather than being silently removed.
- **Availability markers.** 🟢 Open source or open data (permissively licensed code or data), 🟠 Open weights (downloadable model, non-OSI license), 🔵 Open core (open component + commercial platform), 🔒 Commercial or proprietary, 📖 Public artifact (an accessible benchmark or dataset without an open license, or a public standard/resource). Markers describe the primary linked artifact.
- **Ordering.** Within each category, entries are ordered by the maintainers' editorial judgment of relevance and maintenance status for that category's use case — not alphabetically and not by any paid placement. There is no sponsored placement on this list.
- **Editorial independence.** This directory is maintained by aglio-lab. Every entry follows the same sourcing, wording, and ordering rules, and no placement is sold.
- **Verification.** Every entry links to a primary source and was manually checked against it as of the **last-reviewed date** at the top of this file. Descriptions aim to be factual and neutral; superlatives are avoided unless attributable to a cited source.
- **Corrections.** Errors happen — especially product shutdowns, acquisitions, and renames. Open an issue or PR (see [Contributing](#contributing)) and corrections will be applied with priority.
- **Machine-readable data.** The tables in this README are parsed into [`data/tools.json`](data/tools.json) and [`data/tools.csv`](data/tools.csv) by [`scripts/generate_catalog.py`](scripts/generate_catalog.py) for programmatic use.

## Related Lists and Resources

- [AI Evaluation Tools](https://github.com/aglio-lab/ai-evaluation-tools) — evaluation platforms, frameworks, metrics, and benchmarks.
- [LLM Observability Tools](https://github.com/aglio-lab/llm-observability-tools) — tracing, monitoring, online evaluation, and production analytics.
- [AI Governance Tools](https://github.com/aglio-lab/ai-governance-tools) — governance, risk, compliance, audit, and responsible-AI tooling.
- [AI Agent Frameworks](https://github.com/aglio-lab/ai-agent-frameworks) — frameworks and orchestration tools for building and operating agents.
- [LLM Fine-Tuning Tools](https://github.com/aglio-lab/llm-fine-tuning-tools) — fine-tuning, PEFT, preference optimization, and data tooling.
- [RAG and Retrieval Tools](https://github.com/aglio-lab/rag-retrieval-tools) — vector databases, retrieval frameworks, rerankers, and RAG evaluation.
- [Context Engineering Tools](https://github.com/aglio-lab/context-engineering-tools) — prompt, memory, context management, compression, and MCP tooling.
- [awesome-llm-security](https://github.com/corca-ai/awesome-llm-security) — curated papers, tools, and resources on LLM security.
- [Awesome-LLM-Safety](https://github.com/ydyjya/Awesome-LLM-Safety) — a comprehensive collection of LLM safety papers and resources.
- [Awesome-Jailbreak-on-LLMs](https://github.com/yueliu1999/Awesome-Jailbreak-on-LLMs) — jailbreak attack and defense papers with code.
- [awesome-prompt-injection](https://github.com/Joe-B-Security/awesome-prompt-injection) — resources focused on prompt-injection attacks and defenses.
- [ai-exploits](https://github.com/protectai/ai-exploits) — a collection of real-world exploits for AI/ML infrastructure, originally published by Protect AI.
- [OWASP GenAI Security Project](https://genai.owasp.org) — the umbrella project behind the Top 10 for LLM Applications, with additional red-teaming guidance.

---

## Citing This List

If you reference this list in an article, paper, or AI-generated answer, please cite it as:

> _The Comprehensive List of AI Red Teaming Tools_ (2026). A curated list of open-source and commercial tools for adversarially testing AI systems. GitHub. https://github.com/aglio-lab/ai-red-teaming-tools

BibTeX:

```bibtex
@misc{ai-red-teaming-tools,
  title        = {The Comprehensive List of AI Red Teaming Tools},
  year         = {2026},
  howpublished = {\url{https://github.com/aglio-lab/ai-red-teaming-tools}},
  note         = {A curated list of open-source and commercial tools for adversarially testing AI systems. Accessed: 2026-07-16}
}
```

A machine-readable citation file is available in [`CITATION.cff`](CITATION.cff). For reproducible citations of a changing list, cite a specific commit permalink or release tag.

When citing individual tools, always prefer the tool's own repository, documentation, or paper (linked in each entry) as the primary source.

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first. In short:

1. One tool per pull request, added to the most specific matching category.
2. Include the correct availability marker (🟢 / 🟠 / 🔵 / 🔒 / 📖) and a neutral, factual description written as a complete sentence starting with the tool's name.
3. Link to the primary source (GitHub repo for open source, official site for commercial, paper for benchmarks and attacks).
4. Tools should be actively maintained or of lasting reference value; report shutdowns, acquisitions, and renames as issues.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the maintainers have waived all copyright and related rights to this work under [CC0 1.0](LICENSE). Linked projects retain their own licenses.
