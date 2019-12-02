## TypeScript component templates for JetBrains PHPStorm IDE
Add this templates in your PHPStorm settings and create React components easily. 

### TypeScript simple component
#### Class style:
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
#### Functional style:
```typescript
import * as React from "react";

export default function ${NAME}(): JSX.Element {
    return <></>;
}

```

### TypeScript component with props
#### Class style:
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
#### Functional style:
```typescript
import * as React from "react";
import * as PropTypes from "prop-types";

export interface ${NAME}Props {}

${NAME}.propTypes = {

} as { [T in keyof ${NAME}Props]: PropTypes.Validator<any> };

export default function ${NAME}(props: ${NAME}Props): JSX.Element {
    return <></>;
}

```

### TypeScript component with state
#### Class style:
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
#### Functional style:
```typescript
import * as React from "react";

export default function ${NAME}(): JSX.Element {
    #if ($STATE != '')
    #set ($VARIABLES = $STATE.split(","))
    #set (${VARIABLE} = "")
    #foreach (${VARIABLE} in $VARIABLES)
    #set($FIRST_LETTER = $VARIABLE.substring(0, 1).toUpperCase())
    #set($REST = $VARIABLE.substring(1))
    const [${VARIABLE}, set${FIRST_LETTER}${REST}] = React.useState(null);
    #end
    #end

    return <></>;
}

```
Example of `STATE`: `collapse,id,run`. You will get:
```typescript
import * as React from "react";

export default function SomeComponent(): JSX.Element {
    const [collapse, setCollapse] = React.useState(null);
    const [id, setId] = React.useState(null);
    const [run, setRun] = React.useState(null);

    return <></>;
}

```

### TypeScript component with state and props
#### Class style:
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
#### Functional style:
```typescript
import * as React from "react";
import * as PropTypes from "prop-types";

export interface ${NAME}Props {}

${NAME}.propTypes = {} as { [T in keyof ${NAME}Props]: PropTypes.Validator<any> };

export default function ${NAME}(props: ${NAME}Props): JSX.Element {
    #if ($STATE != '')
    #set ($VARIABLES = $STATE.split(","))
    #set (${VARIABLE} = "")
    #foreach (${VARIABLE} in $VARIABLES)
    #set($FIRST_LETTER = $VARIABLE.substring(0, 1).toUpperCase())
    #set($REST = $VARIABLE.substring(1))
    const [${VARIABLE}, set${FIRST_LETTER}${REST}] = React.useState(null);
    #end
    #end

    return <></>;
}

```
Example of state same as for template `TypeScript component with state`
