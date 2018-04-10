## TypeScript component templates for JetBrains PHPStorm IDE
Add this templates in your PHPStorm settings and create React components easily. 


### TypeScript simple component
```typescript
import * as React from "react";

export class ${NAME} extends React.Component {
    public render() {
        return (
            null
        );
    }
}

```

### TypeScript component with props
```typescript
import * as React from "react";
import * as PropTypes from "prop-types";

export interface ${NAME}Props {
    
}

export const ${NAME}PropTypes: {[T in keyof ${NAME}Props]: PropTypes.Validator<any>} = {
    
};

export class ${NAME} extends React.Component<${NAME}Props> {
    public static readonly propTypes = ${NAME}PropTypes;

    public render() {
        return (
            null
        );
    }
}

```

### TypeScript component with state
```typescript
import * as React from "react";

export interface ${NAME}State {
    
}

export class ${NAME} extends React.Component<{}, ${NAME}State> {
    public readonly state: ${NAME}State = {};

    public render() {
        return (
            null
        );
    }
}

```

### TypeScript component with state and props
```typescript
import * as React from "react";
import * as PropTypes from "prop-types";

export interface ${NAME}Props {
    
}

export const ${NAME}PropTypes: {[T in keyof ${NAME}Props]: PropTypes.Validator<any>} = {
    
};

export interface ${NAME}State {
    
}

export class ${NAME} extends React.Component<${NAME}Props, ${NAME}State> {
    public static readonly propTypes = ${NAME}PropTypes;

    public readonly state: ${NAME}State = {};

    public render() {
        return (
            null
        );
    }
}

```