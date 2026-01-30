# FDE Super Team - Deployment Guide

> **Step-by-step guide to deploy the FDE Super Team agent network**

---

## 📋 Prerequisites

### Required
- Nebula AI platform account
- GitHub account (for version control)
- Basic understanding of AI agent concepts

### Recommended
- Familiarity with Forward Deployed Engineering workflows
- Experience with cloud platforms (AWS/Azure/GCP)
- Understanding of software development lifecycle

---

## 🚀 Quick Start (5 Minutes)

### Option 1: Deploy to Nebula (Recommended)

The FDE Super Team is already deployed and ready to use in this Nebula workspace!

**All agents are active:**
- ✅ 1 Strategic agent (Mission Commander)
- ✅ 17 Expert agents
- ✅ 6 Execution tool agents

**Start using immediately:**
```
"We need to migrate our legacy ERP system to the cloud"
→ Mission Commander will orchestrate the entire project
```

### Option 2: Clone and Customize

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/fde-super-team.git
cd fde-super-team

# 2. Review agent configurations
ls docs/

# 3. Customize for your organization
# - Edit agent descriptions in AGENT_CATALOG.md
# - Add industry-specific knowledge
# - Configure custom toolkits
```

---

## 📦 Full Deployment Process

### Step 1: Verify Agent Network

Check that all 24 agents are deployed and active:

```python
# List all FDE agents
from nebula import lookup_agents

agents = lookup_agents(query="FDE")
print(f"Total agents: {len(agents)}")

# Verify Mission Commander
commander = lookup_agents(query="Mission Commander")
print(f"Commander ID: {commander[0]['agent_id']}")
```

**Expected output:**
```
Total agents: 24
Commander ID: agt_0697c9f40dc2794280000f9c0ef4f8dc
```

### Step 2: Test Mission Commander

Run a validation test:

```python
from nebula import delegate

result = delegate(
    agent_id="agt_0697c9f40dc2794280000f9c0ef4f8dc",
    description="""
    Test Mission: A retail company wants to break up their monolithic 
    e-commerce platform into microservices. Current tech stack is Ruby 
    on Rails with PostgreSQL. Need to handle 10x traffic during Black Friday.
    """
)

# Verify response includes:
# - Mission classification
# - Expert team assembly
# - Execution plan
# - Deliverables list
```

### Step 3: Configure Organization-Specific Settings

#### A. Add Industry Knowledge

If your organization focuses on specific industries, enhance the Industry Domain Advisor:

```python
from nebula import manage_agents

# Add custom industry templates
manage_agents(
    action="update",
    agent_id="agt_0697cbea8a6c78258000359e1aadc02d",
    prompt_sections={
        "custom_sections": {
            "automotive_expertise": """
            Automotive industry specifics:
            - IATF 16949 quality management
            - Just-in-time manufacturing
            - Tier 1/2/3 supplier networks
            - Vehicle lifecycle management
            """
        }
    }
)
```

#### B. Configure Cloud Preferences

Set default cloud platform preferences:

```python
# Update Cloud Migration Strategist with org preferences
manage_agents(
    action="update",
    agent_id="agt_0697cc0abd6274a08000346fbedc4d9e",
    prompt_sections={
        "best_practices": [
            "Default to AWS for most projects (existing partnership)",
            "Use Azure for Microsoft-heavy environments",
            "Prefer multi-region over multi-cloud for simplicity",
            "Apply FinOps tagging standards from day 1"
        ]
    }
)
```

#### C. Add Security Policies

Configure organization security requirements:

```python
# Update Security Architect with company policies
manage_agents(
    action="update",
    agent_id="agt_0697c99cb9fb789780002cd1c80d9c80",
    prompt_sections={
        "tool_instructions": """
        Organization security requirements:
        - All data at rest must be encrypted (AES-256)
        - MFA required for all production access
        - SOC2 Type II compliance mandatory
        - Quarterly penetration testing
        - Zero trust network architecture
        """
    }
)
```

### Step 4: Set Up Monitoring

Track agent usage and performance:

```python
# Create monitoring dashboard
import pandas as pd
from datetime import datetime, timedelta

def get_agent_metrics(days=30):
    """Track agent invocations and success rates"""
    
    metrics = {
        'agent_name': [],
        'invocations': [],
        'success_rate': [],
        'avg_response_time': []
    }
    
    # Query usage data (implement based on your logging)
    # This is a template - adjust to your monitoring system
    
    return pd.DataFrame(metrics)

# Generate report
df = get_agent_metrics(days=30)
df.to_csv('agent_usage_report.csv')
```

---

## 🔧 Advanced Configuration

### Custom Agent Creation

Add organization-specific agents:

```python
from nebula import manage_agents

# Example: Create a custom compliance agent
manage_agents(
    action="create",
    name="GDPR Compliance Specialist",
    description="""
    Specializes in GDPR compliance for EU operations.
    
    Core Capabilities:
    - Data mapping and classification
    - DPIA (Data Protection Impact Assessment)
    - Consent management design
    - Right to erasure implementation
    - Cross-border transfer mechanisms
    
    Key Deliverables:
    - GDPR compliance checklist
    - Data processing agreements
    - Privacy policy templates
    - DPIA reports
    """,
    selected_toolkits=["Web Research", "File Operations"]
)
```

### Integration with CI/CD

Automate agent deployment in your CI/CD pipeline:

```yaml
# .github/workflows/deploy-agents.yml
name: Deploy FDE Agents

on:
  push:
    branches: [main]
    paths:
      - 'agents/**'

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.11'
      
      - name: Install dependencies
        run: |
          pip install nebula-cli
      
      - name: Deploy agents
        env:
          NEBULA_API_KEY: ${{ secrets.NEBULA_API_KEY }}
        run: |
          python scripts/deploy_agents.py
      
      - name: Run validation tests
        run: |
          python tests/validate_deployment.py
```

### Environment-Specific Configurations

Manage different configurations for dev/staging/prod:

```python
# config/environments.py
ENVIRONMENTS = {
    'development': {
        'mission_commander_id': 'agt_dev_xxx',
        'auto_delegation': True,
        'require_approval': False,  # Fast iteration
        'log_level': 'DEBUG'
    },
    'staging': {
        'mission_commander_id': 'agt_staging_xxx',
        'auto_delegation': True,
        'require_approval': True,  # Review before execution
        'log_level': 'INFO'
    },
    'production': {
        'mission_commander_id': 'agt_0697c9f40dc2794280000f9c0ef4f8dc',
        'auto_delegation': True,
        'require_approval': True,
        'log_level': 'WARNING'
    }
}
```

---

## 🧪 Testing & Validation

### Validation Test Suite

Run the complete validation suite:

```python
# tests/validate_deployment.py
import pytest
from nebula import delegate, lookup_agents

def test_all_agents_deployed():
    """Verify all 24 agents are active"""
    agents = lookup_agents(query="all")
    fde_agents = [a for a in agents if 'FDE' in a['name'] or 
                  a['agent_id'] in EXPECTED_AGENT_IDS]
    assert len(fde_agents) >= 24, f"Expected 24+ agents, found {len(fde_agents)}"

def test_mission_commander_orchestration():
    """Test Mission Commander with a complex scenario"""
    result = delegate(
        agent_id="agt_0697c9f40dc2794280000f9c0ef4f8dc",
        description="Migrate a 10-year-old Oracle ERP to SAP S/4HANA Cloud"
    )
    
    assert 'mission_classification' in result
    assert 'expert_team' in result
    assert 'execution_plan' in result
    assert len(result['expert_team']) >= 5

def test_expert_agent_responses():
    """Test individual expert agents"""
    # Test Cloud Migration Strategist
    result = delegate(
        agent_id="agt_0697cc0abd6274a08000346fbedc4d9e",
        description="Design AWS landing zone for financial services"
    )
    assert 'architecture' in result.lower()
    assert 'security' in result.lower()

if __name__ == '__main__':
    pytest.main([__file__, '-v'])
```

Run tests:
```bash
pytest tests/validate_deployment.py -v
```

### Performance Benchmarks

Measure agent response times:

```python
# tests/benchmark_agents.py
import time
from nebula import delegate

def benchmark_agent(agent_id, description, runs=5):
    """Measure average response time"""
    times = []
    
    for i in range(runs):
        start = time.time()
        delegate(agent_id=agent_id, description=description)
        elapsed = time.time() - start
        times.append(elapsed)
    
    return {
        'agent_id': agent_id,
        'avg_time': sum(times) / len(times),
        'min_time': min(times),
        'max_time': max(times)
    }

# Run benchmarks
results = [
    benchmark_agent(
        "agt_0697c9f40dc2794280000f9c0ef4f8dc",
        "Classify this project: migrate CRM to cloud"
    ),
    benchmark_agent(
        "agt_0697cc0abd6274a08000346fbedc4d9e",
        "Design AWS architecture for e-commerce platform"
    )
]

print("Benchmark Results:")
for r in results:
    print(f"Agent {r['agent_id']}: {r['avg_time']:.2f}s avg")
```

---

## 📊 Monitoring & Observability

### Usage Analytics

Track which agents are most valuable:

```python
# analytics/agent_usage.py
from collections import Counter
import json

def analyze_agent_usage(log_file='agent_calls.jsonl'):
    """Analyze agent usage patterns"""
    
    agent_counts = Counter()
    mission_types = Counter()
    
    with open(log_file) as f:
        for line in f:
            event = json.loads(line)
            agent_counts[event['agent_id']] += 1
            if 'mission_type' in event:
                mission_types[event['mission_type']] += 1
    
    print("Top 10 Most Used Agents:")
    for agent_id, count in agent_counts.most_common(10):
        print(f"  {agent_id}: {count} calls")
    
    print("\nMission Type Distribution:")
    for mission_type, count in mission_types.most_common():
        print(f"  {mission_type}: {count} projects")

analyze_agent_usage()
```

### Health Checks

Automated health monitoring:

```python
# monitoring/health_check.py
from nebula import lookup_agents, delegate
import smtplib
from email.message import EmailMessage

def check_agent_health():
    """Verify all agents are responsive"""
    
    critical_agents = [
        "agt_0697c9f40dc2794280000f9c0ef4f8dc",  # Mission Commander
        "agt_0697cc0abd6274a08000346fbedc4d9e",  # Cloud Strategist
        "agt_0697cc02196d72ef8000197ccdc48543",  # Legacy Expert
    ]
    
    failures = []
    
    for agent_id in critical_agents:
        try:
            result = delegate(
                agent_id=agent_id,
                description="Health check ping",
                timeout=30
            )
            if not result:
                failures.append(agent_id)
        except Exception as e:
            failures.append((agent_id, str(e)))
    
    if failures:
        send_alert(f"Agent health check failures: {failures}")
    
    return len(failures) == 0

def send_alert(message):
    """Send alert email"""
    msg = EmailMessage()
    msg.set_content(message)
    msg['Subject'] = 'FDE Agent Health Check Alert'
    msg['From'] = 'alerts@fde-super-team.com'
    msg['To'] = 'ops-team@yourcompany.com'
    
    # Configure your SMTP server
    # smtplib.SMTP('smtp.yourcompany.com').send_message(msg)

# Run every hour
if __name__ == '__main__':
    check_agent_health()
```

---

## 🔐 Security Best Practices

### 1. API Key Management

```python
# Use environment variables, never hardcode
import os

NEBULA_API_KEY = os.getenv('NEBULA_API_KEY')
if not NEBULA_API_KEY:
    raise ValueError("NEBULA_API_KEY environment variable not set")
```

### 2. Access Control

Configure role-based access:

```python
# config/access_control.py
ROLE_PERMISSIONS = {
    'fde_engineer': {
        'can_call_agents': True,
        'can_create_agents': False,
        'can_modify_agents': False,
        'can_delete_agents': False
    },
    'fde_lead': {
        'can_call_agents': True,
        'can_create_agents': True,
        'can_modify_agents': True,
        'can_delete_agents': False
    },
    'admin': {
        'can_call_agents': True,
        'can_create_agents': True,
        'can_modify_agents': True,
        'can_delete_agents': True
    }
}
```

### 3. Audit Logging

Track all agent interactions:

```python
# monitoring/audit_log.py
import json
from datetime import datetime

def log_agent_call(user_id, agent_id, description, result):
    """Log every agent interaction"""
    
    log_entry = {
        'timestamp': datetime.utcnow().isoformat(),
        'user_id': user_id,
        'agent_id': agent_id,
        'description': description,
        'success': result.get('success', False),
        'duration_ms': result.get('duration_ms', 0)
    }
    
    with open('audit.jsonl', 'a') as f:
        f.write(json.dumps(log_entry) + '\n')
```

---

## 🆘 Troubleshooting

### Common Issues

#### Issue 1: Agent Not Responding

**Symptoms:** Timeout or no response from agent

**Solutions:**
```python
# Check agent status
agent = lookup_agents(agent_id="agt_xxx")[0]
print(f"Status: {agent['status']}")

# Verify tools are configured
print(f"Tools: {agent['tools']}")

# Test with simple request
result = delegate(agent_id="agt_xxx", description="Hello, are you working?")
```

#### Issue 2: Mission Commander Not Delegating

**Symptoms:** Mission Commander returns advice instead of delegating

**Solutions:**
- Ensure your request is complex enough (multi-phase project)
- Be specific about requirements and constraints
- Check that expert agents are deployed

#### Issue 3: Inconsistent Outputs

**Symptoms:** Different results for similar requests

**Solutions:**
- Add more context to your requests
- Use Mission Commander for consistency
- Review agent prompts for clarity

### Getting Help

1. **Check documentation** - README, Agent Catalog, Examples
2. **Search issues** - GitHub Issues for similar problems
3. **Enable debug logging** - Set `log_level='DEBUG'`
4. **Contact support** - fde-super-team@example.com

---

## 📈 Scaling Considerations

### High-Volume Usage

For organizations with >100 FDE projects/month:

1. **Implement caching** - Cache common agent responses
2. **Load balancing** - Distribute across multiple agent instances
3. **Async processing** - Queue long-running missions
4. **Resource limits** - Set timeouts and retry policies

### Multi-Region Deployment

Deploy agents across regions for global teams:

```yaml
# config/regions.yaml
regions:
  us-east-1:
    mission_commander: agt_us_east_xxx
    latency_threshold_ms: 100
  eu-west-1:
    mission_commander: agt_eu_west_xxx
    latency_threshold_ms: 100
  ap-southeast-1:
    mission_commander: agt_ap_xxx
    latency_threshold_ms: 150
```

---

## ✅ Deployment Checklist

Before going to production:

- [ ] All 24 agents deployed and verified
- [ ] Mission Commander tested with 3+ complex scenarios
- [ ] Organization-specific configurations applied
- [ ] Monitoring and alerting set up
- [ ] Access control configured
- [ ] Audit logging enabled
- [ ] Backup and disaster recovery plan in place
- [ ] Team trained on agent usage
- [ ] Documentation reviewed and updated
- [ ] Emergency contacts documented

---

## 🎓 Training Resources

### For FDE Engineers

1. **Quick Start Guide** - 30 minutes
   - Understanding the three-tier architecture
   - When to use Mission Commander vs direct agents
   - Reading agent outputs

2. **Hands-On Workshop** - 2 hours
   - Practice with 5 real scenarios
   - Customizing agent prompts
   - Troubleshooting common issues

3. **Advanced Topics** - 4 hours
   - Creating custom agents
   - Integration with existing tools
   - Performance optimization

### For Management

1. **Executive Overview** - 45 minutes
   - ROI and business value
   - Success metrics
   - Risk mitigation

---

## 📞 Support

- **Documentation**: https://github.com/yourusername/fde-super-team
- **Issues**: https://github.com/yourusername/fde-super-team/issues
- **Discussions**: https://github.com/yourusername/fde-super-team/discussions
- **Email**: support@fde-super-team.example.com

---

**Ready to deploy? Start with Step 1: Verify Agent Network**

