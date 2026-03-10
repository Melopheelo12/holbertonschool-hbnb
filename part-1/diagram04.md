## Sequence Diagram – Review Submission

```mermaid
sequenceDiagram
participant User
participant API
participant BusinessLogic
participant Database

User->>API: POST /reviews
API->>BusinessLogic: createReview()
BusinessLogic->>Database: saveReview()
Database-->>BusinessLogic: reviewStored
BusinessLogic-->>API: reviewCreated
API-->>User: 201 Created
```
