# Contributing to Chaos

Thank you for your interest in contributing to Chaos! This document provides guidelines and information for contributors.

## What We're Looking For

We welcome contributions in the following areas:

### Open Source Components
- **UI/UX Improvements**: Better user experience, accessibility, and visual design
- **Performance Optimizations**: Faster loading, better memory usage, smoother animations
- **Bug Fixes**: Issues that affect the open-source components
- **Documentation**: Code comments, README updates, and technical documentation
- **Testing**: Unit tests, integration tests, and quality assurance

### What's Not Open Source
- **Core Application Logic**: The main skin management and game integration features
- **Proprietary Tools**: Advanced modding tools and premium features
- **Commercial Components**: Monetized features and premium content

## Development Setup

### Prerequisites
- Node.js 18+ and pnpm
- Rust toolchain (for Tauri development)
- Windows development environment
- Git

### Getting Started

1. **Fork the repository**
   ```bash
   git clone https://github.com/bynwkyow/chaos-skin-manager.git
   cd chaos-skin-manager
   ```

2. **Install dependencies**
   ```bash
   pnpm install
   ```

3. **Set up development environment**
   ```bash
   # Frontend development
   pnpm dev
   
   # Tauri development (requires admin)
   pnpm dev:admin
   ```

## Development Guidelines

### Code Style

- **TypeScript**: Use strict mode and proper typing
- **Formatting**: Use Biome for code formatting and linting
- **Naming**: Use descriptive names for variables, functions, and components
- **Comments**: Add JSDoc comments for complex functions

### Commit Messages

Follow conventional commit format:
```
type(scope): description

[optional body]

[optional footer]
```

Examples:
- `feat(ui): add dark mode toggle`
- `fix(search): resolve filter not working`
- `docs(readme): update installation instructions`

### Pull Request Process

1. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes**
   - Follow the coding guidelines
   - Add tests if applicable
   - Update documentation

3. **Test your changes**
   ```bash
   pnpm lint
   pnpm build
   pnpm test  # if tests exist
   ```

4. **Submit a PR**
   - Use the PR template
   - Describe your changes clearly
   - Link related issues

## Testing

### Running Tests
```bash
# Lint and format check
pnpm lint

# Type checking
pnpm type-check

# Build verification
pnpm build
```

### Test Coverage
- Aim for high test coverage on new features
- Include edge cases and error scenarios
- Test both success and failure paths

## Documentation

### Code Documentation
- Use JSDoc for function documentation
- Include examples for complex APIs
- Document any non-obvious implementation details

### User Documentation
- Update README.md for user-facing changes
- Add inline comments for complex logic
- Create guides for new features

## Bug Reports

### Before Reporting
- Check existing issues
- Try to reproduce the problem
- Check if it's a known limitation

### Bug Report Template
```markdown
**Description**
Brief description of the issue

**Steps to Reproduce**
1. Step one
2. Step two
3. Step three

**Expected Behavior**
What should happen

**Actual Behavior**
What actually happens

**Environment**
- OS: [e.g., Windows 11]
- Version: [e.g., 1.1.4]
- Browser: [if applicable]

**Additional Information**
Screenshots, logs, or other relevant details
```

## Feature Requests

### Before Requesting
- Check if the feature already exists
- Consider if it fits the project scope
- Think about implementation complexity

### Feature Request Template
```markdown
**Feature Description**
Clear description of the requested feature

**Use Case**
Why this feature would be useful

**Proposed Implementation**
How you think it could be implemented

**Alternatives Considered**
Other approaches you've considered

**Additional Context**
Any other relevant information
```

## Security

### Reporting Security Issues
- **DO NOT** create public issues for security vulnerabilities
- Email security reports to: [8v0ky0@gmail.com](mailto:8v0ky0@gmail.com)
- Include detailed reproduction steps
- Allow time for investigation and fix

### Security Guidelines
- Never commit sensitive information
- Use environment variables for secrets
- Follow secure coding practices
- Validate all user inputs

## Issue Labels

We use the following labels to categorize issues:

- `bug`: Something isn't working
- `enhancement`: New feature or request
- `documentation`: Improvements or additions to documentation
- `good first issue`: Good for newcomers
- `help wanted`: Extra attention is needed
- `invalid`: Something that's wrong
- `question`: Further information is requested
- `wontfix`: This will not be worked on

## Recognition

### Contributors
- All contributors are listed in the README
- Significant contributions get special recognition
- Contributors are mentioned in release notes

### Hall of Fame
- Top contributors get special badges
- Long-term contributors get maintainer status
- Exceptional contributions get special mentions

## Getting Help

### Community Support
- **GitHub Discussions**: For questions and general help
- **GitHub Issues**: For bug reports and feature requests
- **Discord**: [https://discord.gg/8HZNrYbaAC](https://discord.gg/8HZNrYbaAC)

### Maintainer Contact
- **Email**: [8v0ky0@gmail.com](mailto:8v0ky0@gmail.com)
- **GitHub**: [@bynwkyow](https://github.com/bynwkyow)

## License

By contributing to Chaos, you agree that your contributions will be licensed under the same license as the project (MIT License).

## Thank You

Thank you for contributing to Chaos! Every contribution, no matter how small, helps make this project better for everyone.

---

**Remember**: This is a collaborative effort. Be respectful, helpful, and constructive in all interactions.
