# Contributing to ShaMstack

Thank you for wanting to contribute! ShaMstack is built on the belief that marketing teams should have access to enterprise-grade AI tooling without enterprise complexity.

---

## How to Contribute

### 1. Report Bugs

Found a bug? Open an issue with:
- Clear description of the issue
- Steps to reproduce
- Expected vs actual behavior
- ShaMstack version
- Your marketing stack (CMS, analytics, etc.)

### 2. Suggest Features

Have an idea? Open an issue with:
- Problem you're solving
- Proposed solution
- Alternative approaches considered
- Use case examples

### 3. Submit Code

Ready to contribute code? Here's the process:

1. **Fork the repo**
2. **Create your feature branch** (`git checkout -b feature/amazing-feature`)
3. **Make your changes** (see Development Guidelines below)
4. **Test locally** (ensure all agent workflows work)
5. **Commit your changes** (`git commit -m 'Add amazing feature'`)
6. **Push to the branch** (`git push origin feature/amazing-feature`)
7. **Open a Pull Request**

---

## Development Guidelines

### Agent Specifications

When adding or modifying agents:

- Keep role boundaries clear (no overlap with other agents)
- Define specific KPIs for each agent
- Document handoffs (inputs and outputs)
- Include example interactions

### Code Style

- Follow existing patterns in the repo
- Comment complex logic
- Include type hints where applicable
- Write docstrings for functions

### Testing

Before submitting:

- Test the full workflow locally
- Ensure handoffs between agents work
- Verify integration points (if applicable)
- Check for edge cases

### Documentation

Update documentation when:

- Adding new agents
- Modifying workflows
- Changing integration requirements
- Adding configuration options

---

## Areas We Need Help

Priority areas for contribution:

1. **New Integrations**
   - Additional CMS platforms (Drupal, Joomla)
   - More social platforms (TikTok, Pinterest)
   - Email platforms (ActiveCampaign, Drip)
   - Analytics tools (Mixpanel, Amplitude)

2. **Agent Enhancements**
   - Improved AEO (Answer Engine Optimization)
   - Better brand voice detection
   - Multi-language support

3. **Workflow Automation**
   - Trigger-based workflows
   - Conditional logic improvements
   - Better tier handling

4. **Documentation**
   - Video tutorials
   - Case studies
   - Industry-specific guides

---

## Code of Conduct

- Be respectful and inclusive
- Focus on constructive feedback
- Assume good intent
- Help others learn

---

## Questions?

Open an issue or reach out to the maintainers. We're here to help!

---

**Thank you for making ShaMstack better for everyone.**
