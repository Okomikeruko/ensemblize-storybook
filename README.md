# Design System Pipeline

A comprehensive design-to-development pipeline integrating Figma, Storybook, and React components through Jira project management.

## Overview

This repository contains our component library and design system pipeline. The system integrates:
- Figma for design and component specifications
- Storybook for component development and documentation
- React for component implementation
- Jira for project management and tracking

## Architecture

### Component Structure
```
src/
├── components/
│   ├── atoms/       # Basic building blocks
│   ├── molecules/   # Combinations of atoms
│   └── organisms/   # Complex components
└── tokens/          # Design tokens from Figma
```

Each component follows this structure:
```
ComponentName/
├── ComponentName.tsx
├── ComponentName.stories.tsx
├── ComponentName.test.tsx
└── index.ts
```

### Design Tokens
Design tokens are synchronized from Figma using Tokens Studio and stored in `tokens/` directory. These drive our theme variables and component styles.

## Setup

1. **Prerequisites**
   - Node.js (v16 or higher)
   - Yarn/npm
   - Figma account with admin access
   - Jira Cloud account
   - GitHub access

2. **Installation**
   ```bash
   # Clone the repository
   git clone [repository-url]
   
   # Install dependencies
   yarn install
   
   # Setup environment variables
   cp .env.example .env
   ```

3. **Environment Variables**
   ```
   FIGMA_ACCESS_TOKEN=
   JIRA_API_TOKEN=
   STORYBOOK_URL=
   ```

## Development Workflow

### 1. Design Phase (Figma)
- Components are designed in Figma following atomic design principles
- Design tokens are maintained using Tokens Studio
- Each component frame is organized by atomic level (atoms, molecules, organisms)
- Deep links to specific components are used in Jira tickets

### 2. Development Phase
- Create a new branch from main: `feature/[JIRA-TICKET]-component-name`
- Implement component following Figma specifications
- Create stories in Storybook with design integration
- Write tests for component functionality
- Document props and usage

### 3. Quality Assurance
- Visual regression testing via Chromatic
- Accessibility testing (WCAG compliance)
- Unit and integration tests
- Design review against Figma specs

## Integration Points

### Figma Integration
- **Location**: `.storybook/preview.js`
- Configure Figma addon for direct design reference
- Use design tokens from Tokens Studio

### Jira Integration
- Tickets follow the format: `[PROJECT]-[NUMBER] Component Name`
- Link Figma designs and Storybook stories in tickets
- Use labels to track component status

### Storybook Configuration
- **Location**: `.storybook/`
- Configured addons:
  - Figma (design references)
  - A11y (accessibility testing)
  - Controls (prop manipulation)
  - Docs (automatic documentation)

## Commands

```bash
# Start Storybook development server
yarn storybook

# Build static Storybook
yarn build-storybook

# Run tests
yarn test

# Update design tokens
yarn tokens:update

# Lint code
yarn lint
```

## Component Creation Checklist

- [ ] Figma design complete and reviewed
- [ ] Design tokens exported
- [ ] Component implemented
- [ ] Stories created and documented
- [ ] Tests written and passing
- [ ] Accessibility checks passed
- [ ] Visual regression tests added
- [ ] Documentation complete
- [ ] Design review approval
- [ ] PR created and linked to Jira ticket

## Best Practices

1. **Component Development**
   - Follow atomic design principles
   - Use design tokens for all visual properties
   - Implement responsive behavior
   - Include prop documentation
   - Add accessibility features

2. **Version Control**
   - Meaningful commit messages referencing Jira tickets
   - Branch naming: `feature/[JIRA-TICKET]-description`
   - PR template completion
   - Squash commits on merge

3. **Documentation**
   - Clear prop descriptions
   - Usage examples
   - Edge cases and limitations
   - Accessibility considerations

## Contributing

1. Create a new branch from `main`
2. Implement changes following our development workflow
3. Submit a PR with:
   - Linked Jira ticket
   - Completed checklist
   - Screenshot of Storybook story
   - Visual regression test results

## Support

- **Design System Team**: #design-system Slack channel
- **Documentation**: Internal Confluence space
- **Issues**: File via Jira project board

## License

[Your License Here]
