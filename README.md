# 🛡️ Sentinel — AI Business Autopilot

> **An experimental decision-intelligence system for detecting business problems, estimating impact, simulating interventions, and enforcing safe actions.**

**Status: Archived Hackathon Prototype**

Sentinel was built as a hackathon prototype exploring a simple question:

> **What if a business could identify a revenue-impacting problem, estimate its potential impact, compare possible responses, and only allow actions that pass predefined safety rules?**

The project is no longer under active development.

---

## ⚠️ Prototype Disclaimer

Sentinel is a **demonstration prototype**, not a production financial or payment system.

The current version uses simulated/demo merchant data and modeled outcomes. Its predictive and financial estimates have **not** been validated against production merchant data or live payment infrastructure.

The project should therefore be evaluated as an engineering and product experiment rather than as a production-ready prediction system.

---

## 🎯 The Problem

Business systems are often reactive:

```text
Problem occurs
      ↓
Merchant notices
      ↓
Team investigates
      ↓
Team decides
      ↓
Action is taken
```

By the time a problem is discovered, its financial impact may already be increasing.

Sentinel explored a more proactive workflow:

```text
Observe
   ↓
Predict
   ↓
Quantify
   ↓
Explain
   ↓
Simulate
   ↓
Decide
   ↓
Policy Check
   ↓
Act
   ↓
Verify
   ↓
Audit
```

The goal was not simply to detect an anomaly.

The goal was to help answer:

> **What is happening, what could happen next, how much could it matter, what could we do, and are we allowed to do it?**

---

## 🧠 Core Architecture

Sentinel separates **intelligence** from **authority**.

### Intelligence Layer

The system can:

* analyze operational signals
* identify abnormal changes
* estimate potential outcomes
* explain contributing signals
* estimate financial exposure
* compare intervention scenarios
* recommend an action

### Deterministic Policy Layer

The AI does **not** independently decide whether an action is allowed.

A deterministic policy layer evaluates conditions such as:

* confidence threshold
* action-value limit
* risk level
* merchant automation settings

Example:

```text
Confidence ≥ minimum threshold
AND
Action value ≤ automatic-action limit
AND
High-risk = false
AND
Automatic actions = enabled
```

This separation was one of the central architectural ideas explored in the project.

---

## 🔄 Example Decision Flow

The prototype demonstrates a hypothetical merchant scenario in which payment success deteriorates.

Example:

```text
Baseline success rate: 97.8%
Current success rate:   91.2%

Degradation:            6.6 percentage points
```

Sentinel then evaluates the situation through several stages.

### 1. Observe

Detect a significant change in merchant signals.

### 2. Predict

Estimate whether the disruption may continue.

The current prototype produces demonstration probabilities using an MVP model.

**Important:** these probabilities are not trained production predictions.

### 3. Quantify

Translate operational degradation into an estimated financial exposure.

The prototype uses:

```text
Affected transaction volume
×
Failure rate
×
Average order value
```

The resulting figure is intended as a **decision-support estimate**, not a guaranteed financial loss.

### 4. Explain

Surface signals associated with the detected degradation.

Example demonstration signals include:

| Signal          | Change |
| --------------- | -----: |
| UPI             | +16.2% |
| Bank-A          | +31.0% |
| Mobile          | +14.0% |
| Returning users | +11.8% |

### 5. Simulate

Compare possible interventions before recommending one.

Example modeled scenarios:

| Scenario       | Simulated Success Rate | Estimated Exposure |
| -------------- | ---------------------: | -----------------: |
| Do nothing     |                  91.2% |          ₹1,95,360 |
| Intervention A |                  97.1% |            ₹64,380 |
| Intervention B |                  95.2% |          ₹1,06,560 |

The prototype selects the scenario with the lowest modeled exposure among the permitted options.

**These are simulated outcomes, not measurements of live payment-network changes.**

---

## 🏗️ Repository Structure

```text
sentinel-ai-business-autopilot/
│
├── backend/              # Backend application and decision logic
├── frontend/             # Dashboard / user interface
├── data/                 # Prototype/demo data
├── docs/                 # Supporting documentation
├── .github/workflows/    # GitHub Actions workflows
│
├── .env.example          # Environment variable template
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE
├── SECURITY.md
├── index.html
└── README.md
```

---

## 🔐 Safety Philosophy

One of the main ideas explored by Sentinel was:

> **AI should provide intelligence; deterministic software should control authority.**

Instead of allowing an AI model to directly execute arbitrary business actions, the architecture places a policy boundary between recommendation and execution.

This creates a conceptual separation:

```text
AI
 ↓
Recommendation
 ↓
Deterministic Policy
 ↓
Permission
 ↓
Action
 ↓
Verification
```

This pattern can be useful when designing AI systems that interact with consequential business operations.

---

## 🧪 What Is Demonstrated vs. What Is Not

### Demonstrated

* merchant-signal analysis
* anomaly/problem identification
* financial-impact estimation
* scenario comparison
* policy-based action validation
* dashboard/application architecture
* separation between intelligence and authority
* prototype decision workflow

### Not demonstrated at production level

* validated predictive accuracy on historical merchant datasets
* causal estimation of intervention outcomes
* real-time payment-network optimization
* guaranteed revenue-loss prediction
* production-scale autonomous financial decisions
* statistically validated Digital Twin models
* production merchant deployment

Being explicit about this distinction is intentional.

---

## 💡 What We Learned

The most important lesson from Sentinel was not simply how to build an AI dashboard.

It was the importance of connecting:

**Prediction → Evidence → Financial impact → Decision → Policy → Verification**

A system becomes much more useful when it can explain not only:

> "Something is wrong."

but also:

> "This is what appears to be wrong, this is the estimated impact, these are the available responses, this is why one response is preferable, and these are the rules that determine whether it may be executed."

The project also exposed an important engineering lesson:

**A sophisticated product narrative must be matched by equally strong underlying evidence.**

Future versions of this concept would require real historical datasets, validated models, measured intervention outcomes, and substantially stronger evaluation methodology.

---

## 📌 Project Status

**Archived — Hackathon Prototype**

This repository is preserved as a record of the engineering work, product exploration, and lessons learned during development.

It is not intended to represent a production-ready financial or payment platform.

---

## 👤 Author

Built by **Navya** as an independent hackathon project.

---

## 📄 License

See [`LICENSE`](LICENSE).
