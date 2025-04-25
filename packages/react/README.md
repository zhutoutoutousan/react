# React Core Package

The `react` package is the core of React's implementation, providing the fundamental APIs and functionality that make React work.

## Architecture

```mermaid
graph TD
    subgraph Core
        A[React Core] --> B[Component System]
        A --> C[Hooks System]
        A --> D[Reconciliation]
        A --> E[Event System]
    end
    
    subgraph Runtime
        F[JSX Runtime] --> G[Element Creation]
        F --> H[Component Creation]
        F --> I[Fragment Support]
    end
    
    subgraph Build Variants
        J[Development] --> K[Error Messages]
        J --> L[Warnings]
        M[Production] --> N[Optimized Code]
        M --> O[Minified]
    end
```

## Key Components

### 1. Core React APIs
- `createElement` - Creates React elements
- `Component` - Base class for class components
- `PureComponent` - Optimized component class
- `memo` - Memoization for function components
- `forwardRef` - Forward refs through components

### 2. Hooks System
```mermaid
graph LR
    A[useState] --> B[State Management]
    C[useEffect] --> D[Side Effects]
    E[useContext] --> F[Context]
    G[useReducer] --> H[Complex State]
    I[useCallback] --> J[Function Memoization]
    K[useMemo] --> L[Value Memoization]
```

### 3. JSX Runtime
- `jsx-runtime.js` - Production JSX transform
- `jsx-dev-runtime.js` - Development JSX transform
- `react-server.js` - Server-side JSX support

## Build Variants

```mermaid
graph TD
    A[Build Variants] --> B[Development]
    A --> C[Production]
    A --> D[Experimental]
    A --> E[Stable]
    A --> F[Facebook Internal]
```

1. **Development Builds**
   - `index.development.js`
   - `index.stable.development.js`
   - `index.experimental.development.js`

2. **Production Builds**
   - `index.js`
   - `index.stable.js`
   - `index.experimental.js`

3. **Special Builds**
   - `index.fb.js` - Facebook internal build
   - `react.react-server.js` - Server components support

## Usage

### Basic Usage
```javascript
import React from 'react';

function MyComponent() {
  return <div>Hello World</div>;
}
```

### With Hooks
```javascript
import { useState, useEffect } from 'react';

function Counter() {
  const [count, setCount] = useState(0);
  
  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);
  
  return (
    <button onClick={() => setCount(c => c + 1)}>
      Count: {count}
    </button>
  );
}
```

## Development

### Building
```bash
# Build all variants
yarn build

# Build specific variant
yarn build --variant=development
```

### Testing
```bash
# Run all tests
yarn test

# Test specific feature
yarn test --pattern="hooks"
```

## Architecture Details

### Component System
```mermaid
graph TD
    A[ReactElement] --> B[Class Component]
    A --> C[Function Component]
    B --> D[Lifecycle Methods]
    C --> E[Hooks]
    D --> F[State Management]
    E --> F
```

### Event System
```mermaid
graph LR
    A[Event] --> B[SyntheticEvent]
    B --> C[Event Pooling]
    B --> D[Event Delegation]
    B --> E[Cross-browser]
```

## Contributing

When contributing to the React core:

1. Follow the [Contributing Guide](../CONTRIBUTING.md)
2. Add tests for new features
3. Update documentation
4. Consider performance implications
5. Maintain backward compatibility

## Stability

- 🟢 **Stable**: Core APIs and features
- 🟡 **Experimental**: New features in development
- 🔴 **Internal**: Facebook-specific features

## Documentation

- [React Documentation](https://react.dev/docs)
- [API Reference](https://react.dev/reference)
- [Hooks Reference](https://react.dev/reference/hooks)
