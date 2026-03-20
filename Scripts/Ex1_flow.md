```mermaid
graph TD
    A(Start)-->B[Check input]
    B-->C{Valid?}
    C-->|Yes| D[Continue]
    C-->|No| E[Show error]