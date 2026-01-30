# Contributing to FDE Super Team

Thank you for your interest in contributing to FDE Super Team! This document provides guidelines for contributing to the project.

## 🌟 How to Contribute

### Reporting Issues

If you encounter bugs or have feature requests:

1. **Search existing issues** to avoid duplicates
2. **Create a new issue** with:
   - Clear, descriptive title
   - Detailed description of the problem/feature
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Mission type and agents involved
   - Error messages or logs

### Suggesting New Agents

When proposing a new agent:

1. **Check for overlaps** - Review the [Agent Catalog](./docs/AGENT_CATALOG.md)
2. **Define clear scope** - What unique capabilities does it provide?
3. **Identify tier** - Strategic/Expert/Execution?
4. **Specify tools needed** - Code execution, web search, etc.
5. **Provide use cases** - When would users call this agent?

**Template for Agent Proposals:**
```markdown
## New Agent Proposal: [Agent Name]

**Tier:** Strategic / Expert / Execution
**Category:** Domain / Implementation / Management / Tool
**Non-overlapping with:** [List similar existing agents and how this differs]

### Purpose
[1-2 sentence description]

### Core Capabilities
- Capability 1
- Capability 2
- ...

### Key Deliverables
- Deliverable 1
- Deliverable 2
- ...

### Use Cases
1. Scenario 1
2. Scenario 2
3. ...

### Tools Required
- [ ] Code Execution
- [ ] File Operations
- [ ] Web Research
- [ ] Agent Management

### Integration Points
- Typically called by: [Which agents would delegate to this one]
- Delegates to: [Which agents this one would call]
```

### Adding Examples

To contribute usage examples:

1. **Use real scenarios** - Based on actual projects or realistic situations
2. **Show full context** - User request, agent team, execution plan, outputs
3. **Include code samples** - Generated configs, scripts, or architectures
4. **Document outcomes** - Business metrics, technical improvements

Place examples in `/examples/[category]/[example-name]/`

### Improving Documentation

- Fix typos and clarify language
- Add diagrams and visualizations
- Expand on under-documented areas
- Update outdated information

## 🔧 Development Guidelines

### Agent Design Principles

1. **Single Responsibility** - Each agent has one clear purpose
2. **No Overlap** - Capabilities should not duplicate existing agents
3. **Clear Boundaries** - Well-defined input/output contracts
4. **Composability** - Agents should work well together
5. **Production Focus** - Generate code/configs, not just advice

### Naming Conventions

- **Agent Names**: `[Role] [Specialization]` (e.g., "Cloud Migration Strategist")
- **Files**: `snake_case.md` or `kebab-case.md`
- **Branches**: `feature/agent-name` or `fix/issue-description`

### Code Quality

- Include inline comments for complex logic
- Follow language-specific style guides
- Add unit tests for generated code
- Validate configurations before committing

## 📝 Pull Request Process

### Before Submitting

1. **Test your changes** - Ensure agents work as expected
2. **Update documentation** - Reflect changes in README and Agent Catalog
3. **Run validation** - Check for broken links and formatting
4. **Write clear commits** - Descriptive commit messages

### PR Template

```markdown
## Description
[Brief description of changes]

## Type of Change
- [ ] New agent
- [ ] Bug fix
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Other (specify):

## Testing
- [ ] Tested with Mission Commander orchestration
- [ ] Validated outputs against expected deliverables
- [ ] Checked for agent overlaps
- [ ] Updated documentation

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No new warnings or errors
- [ ] Tests pass

## Related Issues
Closes #[issue number]
```

### Review Process

1. **Automated checks** run on all PRs
2. **Maintainer review** within 3-5 business days
3. **Address feedback** through discussions
4. **Merge** once approved

## 🧪 Testing Guidelines

### Manual Testing

Test new agents with:

1. **Simple scenarios** - Single, straightforward tasks
2. **Complex missions** - Multi-phase projects requiring orchestration
3. **Edge cases** - Unusual inputs, error conditions
4. **Integration** - Interaction with existing agents

### Validation Checklist

For new agents:
- [ ] Agent responds to natural language requests
- [ ] Outputs are production-ready (code/configs run successfully)
- [ ] Documentation is complete and accurate
- [ ] No capability overlap with existing agents
- [ ] Mission Commander can delegate to it appropriately

## 📚 Documentation Standards

### Markdown Formatting

- Use headers hierarchically (H1 → H2 → H3)
- Include code blocks with language hints
- Add tables for structured comparisons
- Link to related documents

### Writing Style

- **Be concise** - Clear and direct language
- **Use examples** - Show, don't just tell
- **Think production** - Focus on practical application
- **Assume knowledge** - Audience is technical FDEs

## 🏆 Recognition

Contributors will be:
- Listed in the project README
- Credited in release notes
- Acknowledged in agent descriptions (for new agents)

## 📞 Getting Help

- **Discussions**: Use GitHub Discussions for questions
- **Issues**: Tag with `question` for clarification
- **Email**: fde-super-team@example.com for private inquiries

## 📋 Development Roadmap

See [ROADMAP.md](./ROADMAP.md) for planned features and priorities.

## 🔐 Security

Report security vulnerabilities privately to: security@fde-super-team.example.com

Do not open public issues for security concerns.

## 📜 Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for all contributors.

### Expected Behavior

- Be respectful and considerate
- Welcome diverse perspectives
- Accept constructive criticism gracefully
- Focus on what's best for the community

### Unacceptable Behavior

- Harassment or discriminatory language
- Personal attacks or trolling
- Publishing private information
- Other unprofessional conduct

### Enforcement

Violations may result in:
1. Warning
2. Temporary ban
3. Permanent ban

Report incidents to: conduct@fde-super-team.example.com

## 🙏 Thank You

Your contributions make FDE Super Team better for everyone. We appreciate your time and effort!

---

**Questions?** Open a discussion or reach out to the maintainers.

**Ready to contribute?** Check out [good first issues](https://github.com/yourusername/fde-super-team/labels/good%20first%20issue)!
