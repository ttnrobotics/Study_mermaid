```mermaid
graph TD
    A[Start] --> B{Is it sunny?};
    B --> C[Go inside]
    B --> D[Go outside];
    C --> E[Have fun!];
    D --> E;
