# Project Setup Guide

This guide will help you set up the Chaos development environment and get started with contributing to the project.

## Quick Start

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** 18.0.0 or higher
- **pnpm** 8.0.0 or higher
- **Rust** 1.75.0 or higher
- **Git** 2.30.0 or higher
- **Windows** (primary development platform)

### Installation Commands

```bash
# Install Node.js (if not already installed)
# Download from: https://nodejs.org/

# Install pnpm
npm install -g pnpm

# Install Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# Or download from: https://rustup.rs/

# Verify installations
node --version
pnpm --version
rustc --version
git --version
```

## Project Setup

### 1. Clone the Repository

```bash
# Clone the main repository
git clone https://github.com/bynwkyow/chaos-skin-manager.git
cd chaos-skin-manager

# Add upstream remote (if you're contributing)
git remote add upstream https://github.com/bynwkyow/chaos-skin-manager.git
```

### 2. Install Dependencies

```bash
# Install frontend dependencies
pnpm install

# Install Rust dependencies (if needed)
cd src-tauri
cargo build
cd ..
```

### 3. Environment Configuration

Create a `.env.local` file in the root directory:

```bash
# Copy the example environment file
cp .env.example .env.local

# Edit the file with your configuration
# .env.local
NEXT_PUBLIC_API_URL=http://localhost:3000
NEXT_PUBLIC_APP_NAME=Chaos Dev
```

### 4. Database Setup (if applicable)

```bash
# Set up local database
pnpm db:setup

# Run migrations
pnpm db:migrate

# Seed with sample data
pnpm db:seed
```

## Development Commands

### Frontend Development

```bash
# Start development server
pnpm dev

# Build for production
pnpm build

# Start production server
pnpm start

# Run linting
pnpm lint

# Run type checking
pnpm type-check

# Run tests (if available)
pnpm test
```

### Tauri Development

```bash
# Start Tauri development (requires admin privileges)
pnpm dev:admin

# Build Tauri app for Windows
pnpm build:win

# Build for all platforms
pnpm build:all

# Run Tauri commands
pnpm tauri dev
pnpm tauri build
```

### Code Quality

```bash
# Format code with Biome
pnpm format

# Check code quality
pnpm lint

# Fix auto-fixable issues
pnpm lint:fix

# Run security audit
pnpm audit
```

## Development Tools

### Recommended VS Code Extensions

```json
{
  "recommendations": [
    "rust-lang.rust-analyzer",
    "bradlc.vscode-tailwindcss",
    "ms-vscode.vscode-typescript-next",
    "esbenp.prettier-vscode",
    "biomejs.biome",
    "ms-vscode.vscode-json",
    "ms-vscode.vscode-css-peek",
    "formulahendry.auto-rename-tag",
    "christian-kohler.path-intellisense",
    "ms-vscode.vscode-eslint"
  ]
}
```

### VS Code Settings

Create `.vscode/settings.json`:

```json
{
  "typescript.preferences.importModuleSpecifier": "relative",
  "typescript.suggest.autoImports": true,
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "biomejs.biome",
  "editor.codeActionsOnSave": {
    "quickfix.biome": "explicit",
    "source.organizeImports.biome": "explicit"
  },
  "files.associations": {
    "*.rs": "rust"
  },
  "rust-analyzer.checkOnSave.command": "clippy"
}
```

## Project Structure

### Frontend Structure

```
src/
├── app/                    # Next.js app router
│   ├── admin/             # Admin panel
│   ├── api/               # API routes
│   ├── login/             # Authentication
│   └── page.tsx           # Home page
├── components/             # React components
│   ├── ui/                # Base UI components
│   ├── layout/            # Layout components
│   └── [feature]/         # Feature-specific components
├── lib/                    # Utilities and hooks
│   ├── hooks/             # Custom React hooks
│   ├── utils/              # Utility functions
│   └── store.ts           # State management
└── global.d.ts            # Global type definitions
```

### Backend Structure

```
src-tauri/
├── src/                    # Rust source code
│   ├── commands/          # Tauri commands
│   ├── injection/         # DLL injection logic
│   └── lib.rs             # Main library
├── cslol-tools/           # CSLOL integration
├── tauri.conf.json        # Tauri configuration
└── Cargo.toml             # Rust dependencies
```

## Debugging

### Frontend Debugging

```bash
# Enable debug logging
DEBUG=* pnpm dev

# Use React DevTools
# Install browser extension for React DevTools

# Use Next.js debugging
NODE_OPTIONS='--inspect' pnpm dev
```

### Tauri Debugging

```bash
# Enable Tauri logging
RUST_LOG=debug pnpm tauri dev

# Use Rust debugging
# Set breakpoints in VS Code with rust-analyzer

# Check Tauri logs
# Logs appear in the terminal running tauri dev
```

### Common Issues

```bash
# Clear all caches
pnpm clean

# Reset dependencies
rm -rf node_modules pnpm-lock.yaml
pnpm install

# Reset Rust cache
cd src-tauri
cargo clean
cd ..

# Check for port conflicts
netstat -ano | findstr :3000
```

## Testing

### Running Tests

```bash
# Frontend tests
pnpm test

# Backend tests
cd src-tauri
cargo test
cd ..

# E2E tests (if available)
pnpm test:e2e

# Coverage report
pnpm test:coverage
```

### Writing Tests

```typescript
// Example component test
import { render, screen } from '@testing-library/react'
import { ChampionCard } from '@/components/ChampionCard'

describe('ChampionCard', () => {
  it('renders champion information correctly', () => {
    const champion = {
      id: 266,
      name: 'Aatrox',
      title: 'the Darkin Blade'
    }
    
    render(<ChampionCard champion={champion} />)
    
    expect(screen.getByText('Aatrox')).toBeInTheDocument()
    expect(screen.getByText('the Darkin Blade')).toBeInTheDocument()
  })
})
```

## Deployment

### Development Deployment

```bash
# Build for development
pnpm build:dev

# Start development server
pnpm start:dev
```

### Production Deployment

```bash
# Build for production
pnpm build:prod

# Create production package
pnpm package:win

# Deploy to hosting service
pnpm deploy
```

## Additional Resources

### Documentation
- [Next.js Documentation](https://nextjs.org/docs)
- [Tauri Documentation](https://tauri.app/docs)
- [React Documentation](https://react.dev)
- [TypeScript Handbook](https://www.typescriptlang.org/docs)

### Community
- [GitHub Discussions](https://github.com/bynwkyow/chaos-skin-manager/discussions)
- [Discord Server](https://discord.gg/8HZNrYbaAC)
- [Contributing Guide](CONTRIBUTING.md)

### Tools
- [Biome](https://biomejs.dev) - Code formatting and linting
- [Tailwind CSS](https://tailwindcss.com) - CSS framework
- [Radix UI](https://www.radix-ui.com) - UI components
- [Zustand](https://zustand-demo.pmnd.rs) - State management

## Getting Help

### Before Asking for Help

1. **Check the documentation** - This guide and other docs
2. **Search existing issues** - GitHub issues and discussions
3. **Check the troubleshooting section** - Common solutions
4. **Try a clean setup** - Clear caches and reinstall

### When You Need Help

1. **Create a detailed issue** - Use the bug report template
2. **Provide context** - Environment, steps, error messages
3. **Include logs** - Console output, error traces
4. **Be specific** - What you tried, what you expected

### Contact Information

- **GitHub Issues**: [Create an issue](https://github.com/bynwkyow/chaos-skin-manager/issues)
- **Discord**: [Join our server](https://discord.gg/8HZNrYbaAC)
- **Email**: [8v0ky0@gmail.com](mailto:8v0ky0@gmail.com)

---

**Happy coding!**

If you have any questions or need clarification, don't hesitate to ask in our community channels.
