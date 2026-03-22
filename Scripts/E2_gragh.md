```mermaid
graph LR
    A[Desired Trajectory] -->|q_r, dq_r| B((+<br/>-))
    B --> |e, de| C[Sliding Mode Surface]
    C --> |s| D[Reaching Control Law]
    B --> |e, de| E[Equivalent Control Law]
    D --> F((+/+))
    E --> F
    F --> |tau| G[Robot Manipulator]
    G --> |q, dq| B
    A --> |ddq_r| E