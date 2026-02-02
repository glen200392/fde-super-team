# 📖 Team Playbook - FDE Super Team

**Master the Find → Diagnose → Execute methodology for operational excellence**

---

## Table of Contents

- [The FDE Methodology](#the-fde-methodology)
- [Team Coordination Patterns](#team-coordination-patterns)
- [Playbook by Situation](#playbook-by-situation)
- [Cross-Functional Workflows](#cross-functional-workflows)
- [Metrics & Success Tracking](#metrics--success-tracking)

---

## The FDE Methodology

### What is FDE?

**F**ind → **D**iagnose → **E**xecute

A systematic approach to operational improvement:

1. **FIND** - Identify bottlenecks, inefficiencies, waste
2. **DIAGNOSE** - Root cause analysis, quantify impact
3. **EXECUTE** - Implement solutions, measure results

### Why FDE Works

- ✅ **Data-Driven:** Decisions based on metrics, not opinions
- ✅ **Systematic:** Repeatable process for any problem
- ✅ **ROI-Focused:** Every action has financial justification
- ✅ **Measurable:** Clear before/after metrics

---

## Team Coordination Patterns

### Pattern 1: Sequential Deep Dive

**Use when:** Single complex problem needing comprehensive solution

```
┌─────────────────────────────────────────────────────────┐
│ Step 1: FIND THE BOTTLENECK                             │
│ @Process-Bottleneck-Diagnostics                         │
│ Output: Bottleneck identified, quantified impact        │
└─────────────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────────────┐
│ Step 2: DIAGNOSE ROOT CAUSE                             │
│ Same agent or specialist (e.g., Performance Optimizer)  │
│ Output: Root cause analysis, solution options           │
└─────────────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────────────┐
│ Step 3: JUSTIFY INVESTMENT                              │
│ @ROI-Analysis-Expert                                    │
│ Output: Financial model, NPV, payback period            │
└─────────────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────────────┐
│ Step 4: EXECUTE SOLUTION                                │
│ Specialist agent (Performance/Cost/SRE)                 │
│ Output: Implementation plan, code, configurations       │
└─────────────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────────────┐
│ Step 5: MONITOR & VALIDATE                              │
│ @Production-SRE-Operations or @LLMOps-Governance        │
│ Output: Monitoring dashboards, success metrics          │
└─────────────────────────────────────────────────────────┘
```

**Example:**
```
Problem: API latency degrading

Step 1: @Process-Bottleneck-Diagnostics
"Our API latency has increased from 300ms to 2.5s over 3 months.
Analyze and identify the bottleneck."

Step 2: @Performance-Engineering-Optimizer
"Based on the bottleneck analysis, provide detailed root cause
and optimization solutions."

Step 3: @ROI-Analysis-Expert
"Calculate ROI for the proposed optimizations.
Current impact: 500 support tickets/month due to slow performance."

Step 4: @Performance-Engineering-Optimizer
"Implement the approved optimizations. Provide code, config, deployment plan."

Step 5: @Production-SRE-Operations
"Set up monitoring for the optimized system with alerts for regressions."
```

---

### Pattern 2: Parallel Workstreams

**Use when:** Multiple independent problems to solve simultaneously

```
Thread 1: Cost Optimization              Thread 2: Performance Fix
    @Cost-Optimization-Analyst    |    @Performance-Engineering-Optimizer
              ↓                   |                   ↓
    @ROI-Analysis-Expert          |    @Production-SRE-Operations
              ↓                   |                   ↓
    Implementation                |    Implementation
              ↓                   |                   ↓
    @LLMOps-Governance-Monitoring |    @Production-SRE-Operations
              ↓                               ↓
              └──────────────┬────────────────┘
                             ↓
                    Combined Results Review
```

**Example:**
```
Situation: Budget cuts require both cost reduction AND performance improvement

Thread 1 (Cost):
@Cost-Optimization-Analyst
"Reduce our $50K/month cloud spend by 30%"

Thread 2 (Performance):
@Performance-Engineering-Optimizer  
"Improve API latency from 2s to <500ms"

Combine outputs:
@ROI-Analysis-Expert
"Analyze combined ROI of both initiatives and prioritize implementation order"
```

---

### Pattern 3: Crisis Response

**Use when:** Production incident or urgent issue

```
┌─────────────────────────────────────────┐
│ IMMEDIATE: Triage & Stabilize           │
│ @Production-SRE-Operations              │
│ ⏱️  Time: 5-15 minutes                  │
└─────────────────────────────────────────┘
                  ↓
┌─────────────────────────────────────────┐
│ URGENT: Root Cause Analysis             │
│ Specialist agent based on issue type    │
│ ⏱️  Time: 15-30 minutes                 │
└─────────────────────────────────────────┘
                  ↓
┌─────────────────────────────────────────┐
│ SHORT-TERM: Implement Fix               │
│ Same specialist + SRE for deployment    │
│ ⏱️  Time: 1-4 hours                     │
└─────────────────────────────────────────┘
                  ↓
┌─────────────────────────────────────────┐
│ FOLLOW-UP: Postmortem & Prevention      │
│ @Production-SRE-Operations +            │
│ @Process-Bottleneck-Diagnostics         │
│ ⏱️  Time: 1-2 days                      │
└─────────────────────────────────────────┘
```

**Example:**
```
Crisis: Production API down, 500 errors

IMMEDIATE:
@Production-SRE-Operations
"Production API returning 500 errors. 
Logs show: [paste error logs]
Triage and provide emergency mitigation."

URGENT:
@Performance-Engineering-Optimizer
"Root cause of database connection pool exhaustion.
Analyze and provide fix."

SHORT-TERM:
@Performance-Engineering-Optimizer
"Implement connection pool fix and deploy."

FOLLOW-UP:
@Production-SRE-Operations
"Create postmortem and prevention plan to avoid recurrence."
```

---

### Pattern 4: Strategic Initiative

**Use when:** Large multi-month improvement program

```
Phase 1: Discovery (Week 1-2)
├── @Process-Bottleneck-Diagnostics: Map current state
├── Multiple specialists: Deep-dive analysis
└── @ROI-Analysis-Expert: Opportunity sizing

Phase 2: Planning (Week 3-4)
├── Prioritize initiatives by ROI
├── Create implementation roadmap
└── Resource allocation planning

Phase 3: Quick Wins (Month 2)
├── Execute high-ROI, low-effort improvements
└── Build momentum and credibility

Phase 4: Major Initiatives (Month 3-6)
├── Parallel execution of major improvements
├── Weekly progress reviews
└── Continuous monitoring

Phase 5: Sustain (Ongoing)
├── @Production-SRE-Operations: Monitoring
├── @LLMOps-Governance-Monitoring: Compliance
└── Quarterly optimization reviews
```

---

## Playbook by Situation

### 🚨 Situation 1: System Outage

**Symptoms:** Service down, users impacted, revenue loss

**Team Activation:**
```
MINUTE 0-15: Immediate Response
@Production-SRE-Operations
"Production outage: [symptoms]. Start incident response."

Expected: Triage, immediate mitigation, incident timeline

MINUTE 15-30: Root Cause
Specialist based on failure type:
- Database issues → @Performance-Engineering-Optimizer
- Cost/rate limits → @Cost-Optimization-Analyst  
- LLM API issues → @LLMOps-Governance-Monitoring

HOUR 1-4: Fix Implementation
Execute fix with specialist guidance

DAY 1-2: Postmortem
@Production-SRE-Operations
"Create blameless postmortem with prevention plan"
```

**Success Criteria:**
- ✅ MTTR < 4 hours
- ✅ Root cause identified
- ✅ Prevention measures documented
- ✅ Monitoring improved

---

### 💸 Situation 2: Budget Overrun

**Symptoms:** Costs exceeding budget, CFO asking questions

**Team Activation:**
```
WEEK 1: Discovery
@Cost-Optimization-Analyst
"Analyze $50K/month spend. Identify waste and optimization opportunities."

Expected: Cost breakdown, savings opportunities (quick wins + major initiatives)

WEEK 1: Justification
@ROI-Analysis-Expert
"Calculate ROI for each optimization. Prioritize by payback period."

Expected: Financial model, prioritized list, executive summary

WEEK 2-3: Quick Wins
Implement top 3 quick wins (no-code or low-effort)
Monitor with @LLMOps-Governance-Monitoring

MONTH 2-3: Major Initiatives
Execute larger optimizations in priority order
Track savings weekly

ONGOING: Governance
@LLMOps-Governance-Monitoring
"Set up budget monitoring with alerts for anomalies"
```

**Success Criteria:**
- ✅ 20-40% cost reduction
- ✅ < 3 month payback
- ✅ No performance degradation
- ✅ Continuous monitoring in place

---

### ⚡ Situation 3: Performance Degradation

**Symptoms:** Latency increasing, throughput decreasing, user complaints

**Team Activation:**
```
DAY 1: Identify Bottleneck
@Process-Bottleneck-Diagnostics
"API latency increased from 300ms to 2.5s p95 over 3 months.
Current: [metrics]. Stack: [tech]. Analyze bottleneck."

Expected: Bottleneck identification, quantified impact

DAY 2: Deep Diagnosis
@Performance-Engineering-Optimizer
"Provide detailed root cause analysis and optimization plan for [bottleneck]."

Expected: Profiling, root cause, solution options, code examples

DAY 2: ROI Analysis
@ROI-Analysis-Expert
"Calculate business impact of current slow performance and ROI of fixes."

Expected: Financial justification for engineering time

WEEK 2: Implementation
@Performance-Engineering-Optimizer
"Implement approved optimizations with deployment plan."

Expected: Code, config, testing plan, rollback procedure

WEEK 3+: Monitoring
@Production-SRE-Operations
"Set up performance monitoring with SLO alerts and capacity forecasting."

Expected: Dashboards, alerts, runbooks
```

**Success Criteria:**
- ✅ Latency reduced to target
- ✅ No increase in error rate
- ✅ Monitoring prevents regression
- ✅ Documented for future reference

---

### 🔄 Situation 4: Process Inefficiency

**Symptoms:** Team velocity low, manual toil high, frustration

**Team Activation:**
```
WEEK 1: Process Mapping
@Process-Bottleneck-Diagnostics
"Map our deployment process end-to-end. Current: 4 hours, 3x/day, 5 engineers.
Identify bottlenecks and automation opportunities."

Expected: Process flow diagram, bottleneck analysis, improvement opportunities

WEEK 2: Solution Design
Depends on bottleneck type:
- Manual testing → Automation recommendations
- Long builds → @Performance-Engineering-Optimizer
- Approval delays → Workflow redesign

WEEK 2: Business Case
@ROI-Analysis-Expert
"Calculate ROI: 5 engineers × 4 hours × 3 deploys/day × $100/hour = $6K/day waste.
Implementation cost: [from solution design]. Calculate payback."

WEEK 3-6: Implementation
Execute improvements in phases:
Phase 1: Quick wins (week 3)
Phase 2: Major automation (week 4-5)
Phase 3: Refinement (week 6)

WEEK 7+: Continuous Improvement
@Process-Bottleneck-Diagnostics
"Monthly review: measure improvement, identify new bottlenecks"
```

**Success Criteria:**
- ✅ 50%+ time reduction
- ✅ < 6 month payback
- ✅ Team satisfaction improved
- ✅ Scalable for growth

---

## Cross-Functional Workflows

### Workflow A: Cloud Migration Cost Optimization

**Participants:** Cost Analyst + Performance Optimizer + SRE

```
Stage 1: Pre-Migration Analysis
@Cost-Optimization-Analyst: "Analyze current on-prem costs vs. cloud TCO"
@Performance-Engineering-Optimizer: "Benchmark performance requirements"

Stage 2: Architecture Design
Select cloud services based on cost + performance tradeoffs

Stage 3: Migration Execution
Migrate in waves, optimize each wave

Stage 4: Post-Migration Optimization
@Cost-Optimization-Analyst: "Analyze actual vs. projected costs"
@Performance-Engineering-Optimizer: "Fine-tune performance"
@Production-SRE-Operations: "Establish monitoring and SLOs"
```

---

### Workflow B: LLM Cost & Governance

**Participants:** LLMOps Governance + Cost Analyst + ROI Expert

```
Stage 1: Baseline Assessment
@LLMOps-Governance-Monitoring: "Audit current LLM usage, PII exposure, costs"
@Cost-Optimization-Analyst: "Analyze token usage patterns and costs"

Stage 2: Governance Design
@LLMOps-Governance-Monitoring: "Design PII masking, RBAC, budget controls"

Stage 3: Cost Optimization
@Cost-Optimization-Analyst: "Implement prompt optimization, caching, model routing"

Stage 4: ROI Tracking
@ROI-Analysis-Expert: "Create LLM ROI dashboard tracking cost vs. value"

Stage 5: Continuous Monitoring
@LLMOps-Governance-Monitoring: "Monitor compliance, costs, and policy violations"
```

---

## Metrics & Success Tracking

### Key Performance Indicators

Track these metrics before and after interventions:

#### Performance Metrics
- Latency (p50, p95, p99)
- Throughput (QPS, RPS)
- Error rate (%)
- Availability (%)

#### Cost Metrics
- Monthly operational cost
- Cost per transaction
- Cost per user
- Infrastructure utilization (%)

#### Process Metrics
- Cycle time (end-to-end)
- Lead time (request to delivery)
- Queue depth
- Throughput (items/day)

#### Business Metrics
- Revenue impact ($)
- Customer satisfaction (CSAT, NPS)
- Employee productivity (items/hour)
- Time to market (days)

### Measurement Framework

```
Before (Baseline):
- Metric 1: [current value]
- Metric 2: [current value]
- Business impact: $[annual cost]

Intervention:
- What: [description]
- Cost: $[implementation cost]
- Timeline: [duration]

After (Results):
- Metric 1: [new value] ([% improvement])
- Metric 2: [new value] ([% improvement])
- Business impact: $[annual savings]

ROI:
- Annual savings: $[amount]
- Implementation cost: $[amount]
- Payback period: [months]
- NPV (5yr): $[amount]
- IRR: [%]
```

### Dashboard Template

```
┌────────────────────────────────────────────────────────┐
│ FDE Initiative Dashboard                                │
├────────────────────────────────────────────────────────┤
│ Initiative: [Name]                                      │
│ Status: [In Progress/Completed]                         │
│ Owner: [Team/Person]                                    │
├────────────────────────────────────────────────────────┤
│ Key Metrics:                                            │
│ • Baseline: [value]                                     │
│ • Current: [value] ([% change])                         │
│ • Target: [value]                                       │
│ • On Track: [Yes/No/At Risk]                            │
├────────────────────────────────────────────────────────┤
│ Financial:                                              │
│ • Investment: $[amount]                                 │
│ • Savings to Date: $[amount]                            │
│ • Projected Annual: $[amount]                           │
│ • Payback: [months] ([status vs. plan])                 │
└────────────────────────────────────────────────────────┘
```

---

## Best Practices

### ✅ DO:
1. **Start with metrics** - Always establish baseline before intervention
2. **Quantify impact** - Express problems in business terms ($, time, users affected)
3. **Prioritize by ROI** - Do high-impact, low-effort items first
4. **Monitor continuously** - Prevent regressions with dashboards and alerts
5. **Document learnings** - Create runbooks and playbooks for future reference

### ❌ DON'T:
1. **Skip ROI analysis** - Always justify the effort
2. **Optimize prematurely** - Measure first, optimize second
3. **Ignore quick wins** - Build momentum with easy victories
4. **Neglect monitoring** - What gets measured gets managed
5. **Forget stakeholders** - Communicate progress and wins

---

## Playbook Cheat Sheet

| Situation | First Agent | Key Focus | Timeline |
|-----------|-------------|-----------|----------|
| 🚨 Outage | SRE Operations | MTTR | Hours |
| 💸 Budget Overrun | Cost Analyst | Quick wins | Weeks |
| ⚡ Performance | Process Diagnostics | Bottleneck ID | Days |
| 🔄 Process Inefficiency | Process Diagnostics | Automation | Weeks |
| 🎯 Strategic Initiative | ROI Expert | Opportunity sizing | Months |
| 🔐 LLM Governance | LLMOps Governance | Compliance | Weeks |

---

**Ready to execute?** Pick a playbook and start your FDE journey! 🚀

**Next:** [USE_CASES.md](USE_CASES.md) for detailed examples
