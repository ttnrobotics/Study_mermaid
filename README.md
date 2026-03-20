Mermaid is a text-based diagram language. You write simple code like this:

```mermaid
graph TD
    A[Start] --> B[Do work]
    B --> C[Finish]
```

That creates a flowchart:
Start → Do work → Finish

## A simple way to study Mermaid

Focus on these 4 things first:

### 1. Basic flowchart structure

Use:

```mermaid
graph TD
    A --> B
```

* `graph TD` = top to bottom
* `graph LR` = left to right
* `A --> B` = arrow from A to B

Example:

```mermaid
graph LR
    A[Login] --> B[Dashboard]
    B --> C[Settings]
```

### 2. Node shapes

Different brackets create different shapes:

```mermaid
graph TD
    A[Process]
    B(Start)
    C{Decision}
    D((Database))
```

* `[Text]` = rectangle
* `(Text)` = rounded
* `{Text}` = decision diamond
* `((Text))` = circle/database-like

Example:

```mermaid
graph TD
    A(Start) --> B[Check input]
    B --> C{Valid?}
    C -->|Yes| D[Continue]
    C -->|No| E[Show error]
```

### 3. Labels on arrows

You can label branches:

```mermaid
graph TD
    A{Paid?} -->|Yes| B[Ship order]
    A -->|No| C[Request payment]
```

This makes decision flows much clearer.

### 4. Organizing with subgraphs

Use `subgraph` to group parts:

```mermaid
graph TD
    subgraph Frontend
        A[Login Page]
        B[Dashboard]
    end

    subgraph Backend
        C[API]
        D[(Database)]
    end

    A --> C
    B --> C
    C --> D
```

## A good study path

Practice in this order:

1. **Simple arrows**
2. **Shapes**
3. **Decision branches**
4. **Subgraphs**
5. **Styling**
6. **Other diagram types** like sequence diagrams

## Example: bad vs improved diagram

Basic version:

```mermaid
graph TD
    A --> B
    B --> C
    B --> D
```

Improved version:

```mermaid
graph TD
    A(Start) --> B[Validate Form]
    B --> C{Input OK?}
    C -->|Yes| D[Submit Data]
    C -->|No| E[Show Error]
    D --> F((Database))
```

Why it is better:

* clearer node names
* proper decision shape
* labeled logic
* meaningful final target

## Tips to improve your Mermaid drawings

* Use **short labels**
* Use **consistent shapes**
* Use `{}` for decisions
* Prefer `LR` for wide processes and `TD` for step-by-step flows
* Break large diagrams into **subgraphs**
* Do not connect too many lines to one node unless necessary

## 3 useful Mermaid examples

### Flowchart

```mermaid
graph TD
    A(Start) --> B[Read file]
    B --> C{File exists?}
    C -->|Yes| D[Process file]
    C -->|No| E[Show message]
```

### Sequence diagram

```mermaid
sequenceDiagram
    participant U as User
    participant S as System
    U->>S: Login request
    S-->>U: Login success
```

### State diagram

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Running
    Running --> Finished
    Finished --> [*]
```

## Practice exercise

Try turning this process into Mermaid:

* User opens app
* App checks login
* If logged in, show dashboard
* If not logged in, show login page

Answer:

```mermaid
graph TD
    A[Open App] --> B{Logged in?}
    B -->|Yes| C[Show Dashboard]
    B -->|No| D[Show Login Page]
```

## A simple template you can reuse

```mermaid
graph TD
    A(Start) --> B[Step 1]
    B --> C{Decision?}
    C -->|Yes| D[Action A]
    C -->|No| E[Action B]
    D --> F(End)
    E --> F
```

