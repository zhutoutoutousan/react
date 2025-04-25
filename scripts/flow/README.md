# React Flow Configuration

This directory contains the Flow type checking configuration and utilities for the React project. It ensures type safety and helps catch potential type-related errors early in development.

## Architecture

```mermaid
graph TD
    A[flow/] --> B[runFlow.js]
    A --> C[environment.js]
    A --> D[createFlowConfigs.js]
    A --> E[config/]
    A --> F[react-native-host-hooks.js]
    A --> G[react-devtools.js]
    
    B --> H[Flow Runner]
    C --> I[Environment Setup]
    D --> J[Config Generator]
    E --> K[Flow Configs]
    F --> L[React Native]
    G --> M[DevTools]
```

## Type System

```mermaid
graph LR
    A[Flow Types] --> B[React Types]
    A --> C[DOM Types]
    A --> D[Platform Types]
    A --> E[Utility Types]
    A --> F[Custom Types]
```

## Key Components

### 1. Flow Runner (`runFlow.js`)
- Type checking execution
- Error reporting
- Configuration loading
- Performance optimization

### 2. Environment Setup (`environment.js`)
- Type definitions
- Global types
- Platform-specific types
- Development tools

### 3. Config Generator (`createFlowConfigs.js`)
- Configuration templates
- Platform-specific configs
- Build-time configs
- Development configs

### 4. React Native Integration (`react-native-host-hooks.js`)
- React Native types
- Native module types
- Platform APIs
- Bridge types

## Type Checking Process

```mermaid
sequenceDiagram
    participant Dev
    participant Flow
    participant Types
    participant Report
    
    Dev->>Flow: Run type check
    Flow->>Types: Check types
    Types->>Report: Generate report
    Report->>Dev: Show errors
```

## Usage

### Running Flow

```bash
# Run Flow type checking
yarn flow

# Run with specific config
yarn flow --config=config/development

# Run in CI mode
yarn flow --ci

# Run with watch mode
yarn flow --watch
```

### Configuration Options

Flow can be configured through:

- `.flowconfig` files
- Command line options
- Environment variables
- Platform-specific configs

## Type Categories

1. **React Types**
   - Component types
   - Props types
   - State types
   - Context types

2. **DOM Types**
   - Element types
   - Event types
   - Style types
   - Attribute types

3. **Platform Types**
   - React Native types
   - Web types
   - Server types
   - Test types

## Contributing

When adding new types:

1. Follow Flow best practices
2. Add proper documentation
3. Include test cases
4. Update configuration 
