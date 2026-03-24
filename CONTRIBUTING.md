# Contributing to LangChain Multi-Agent Example

Thank you for your interest in contributing! This repository serves as a learning resource, so clarity and educational value are top priorities.

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- npm, yarn, or pnpm
- Git
- API keys (OpenAI/Anthropic) for testing

### Development Setup

1. Fork and clone the repository
2. Install dependencies:

```bash
npm install
```

3. Copy environment template:

```bash
cp .env.example .env
```

4. Add your API keys to `.env`

5. Create a feature branch:

```bash
git checkout -b feature/your-feature-name
```

## 📝 Contribution Guidelines

### Types of Contributions

We welcome:

- **New Examples**: Additional agent patterns and use cases
- **Documentation**: Improved explanations and guides
- **Bug Fixes**: Correcting errors in examples
- **Tests**: Increasing test coverage
- **Performance**: Optimizing existing code

### Adding New Examples

When adding a new example:

1. **Place in appropriate directory**:
   - `examples/01-08/` for tutorial progression
   - `real-world/` for production use cases
   - `advanced/` for complex patterns

2. **Follow naming convention**:
   ```
   [number]-[descriptive-name].ts
   ```

3. **Include comprehensive comments**:

```typescript
/**
 * Example: Multi-Agent Research System
 *
 * This example demonstrates how to create a team of agents
 * that collaborate to research a topic and produce a report.
 *
 * Architecture:
 * 1. Research Agent - Gathers information
 * 2. Analysis Agent - Analyzes findings
 * 3. Writer Agent - Creates report
 *
 * Run: npm run research-example
 */

import { AgentExecutor } from "langchain/agents";

// Step 1: Define each agent's role
// ...
```

4. **Add JSDoc comments** to all functions:

```typescript
/**
 * Coordinates multiple agents to complete a research task
 * @param topic - The research topic
 * @param depth - Research depth (basic | detailed | comprehensive)
 * @returns Promise with research results
 */
async function conductResearch(topic: string, depth: string) {
  // Implementation
}
```

5. **Create a runner script** in `package.json`:

```json
{
  "scripts": {
    "your-example": "ts-node examples/your-example.ts"
  }
}
```

6. **Add tests** in `tests/examples/`:

```typescript
describe('Your Example', () => {
  it('should execute successfully', async () => {
    const result = await yourExampleFunction();
    expect(result).toBeDefined();
  });
});
```

7. **Update README** with your example

### Code Style

- Use TypeScript for all new code
- Follow existing formatting (Prettier)
- Use functional patterns where appropriate
- Add error handling
- Include type definitions

```typescript
// Good
interface AgentConfig {
  name: string;
  tools: Tool[];
  temperature?: number;
}

async function createAgent(config: AgentConfig): Promise<AgentExecutor> {
  try {
    // Implementation
  } catch (error) {
    throw new AgentError(`Failed to create agent: ${error.message}`);
  }
}
```

### Documentation Standards

- **README updates**: Add your example to appropriate section
- **Inline comments**: Explain "why" not just "what"
- **Code examples**: Show usage before and after
- **Architecture diagrams**: Include for complex patterns
- **Edge cases**: Document and handle

### Testing Requirements

All contributions must include:

1. **Unit tests** for individual functions
2. **Integration tests** for multi-agent flows
3. **Error case testing**
4. >80% code coverage

```typescript
describe('Agent Coordination', () => {
  it('should handle agent failures gracefully', async () => {
    const failingAgent = createMockAgent();
    const result = await coordinateAgents([failingAgent]);

    expect(result.success).toBe(false);
    expect(result.error).toBeDefined();
  });

  it('should retry failed agents up to max attempts', async () => {
    // Test retry logic
  });
});
```

## 📤 Submitting Changes

### Commit Messages

Use conventional commits:

```
feat(examples): add multi-agent debate example

- Implements AgentDebate class
- Adds debate pattern documentation
- Includes comprehensive tests
- Updates README with new example

Closes #123
```

### Pull Request Process

1. **Update documentation**
2. **Ensure all tests pass**: `npm test`
3. **Run linter**: `npm run lint`
4. **Update CHANGELOG.md**
5. **Submit PR** with:

```markdown
## Description
Brief description of changes

## Type
- [ ] New example
- [ ] Documentation
- [ ] Bug fix
- [ ] Test improvement

## Changes
- List of changes made

## Testing
- [ ] Tests added/updated
- [ ] All tests passing

## Documentation
- [ ] README updated
- [ ] Comments added
- [ ] Example runnable

## Checklist
- [ ] Code follows style guide
- [ ] Self-review completed
- [ ] No new warnings
```

## 🐛 Reporting Issues

### Bug Report Template

```markdown
## Bug Description
Clear description of the issue

## Location
Which example/file has the bug?

## Steps to Reproduce
1. Step one
2. Step two
3. See error

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Environment
- Node version:
- Package version:
- OS:

## Code/Logs
```typescript
// Code that causes the issue
```
```

## 💡 Example Contributions Ideas

Looking to contribute? Here are some ideas:

- Add real-world examples (healthcare, finance, education)
- Implement additional agent patterns (negotiation, voting)
- Create visualization tools for agent communication
- Add performance benchmarks
- Write advanced tutorials (deployment, scaling)
- Create video tutorials
- Translate examples to other languages
- Add integration tests with external APIs

## 🤝 Community Guidelines

- Be respectful and constructive
- Focus on what is best for the community
- Show empathy towards other community members
- Welcome newcomers and help them learn

## 📜 License

By contributing, you agree that your contributions will be licensed under the MIT License.

## 🆘 Getting Help

- Open a discussion for questions
- Check existing issues first
- Join our Discord community
- Read LangChain docs

---

Thank you for helping make this resource better for everyone!
