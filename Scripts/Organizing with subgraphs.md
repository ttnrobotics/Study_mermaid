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