graph TB
    A(await M) --> B
    B(Execution de M<br /> jusqu'au premier await) --> C
    C{Task déjà<br />terminée?}
    C --> |Oui| D
    D(Suite de l'execution de M)
    C --> |Non| E
    E(Attachement de continuation,<br />retour à l'appelant) -.-> |Task terminée| D

graph TB
    A("await new TAwaitable()") --> B
    B("TAwaitable.GetAwaiter()") --> C
    C{TAwaiter.IsCompleted}
    C --> |Oui| D
    D("TAwaiter.GetResult()")
    C --> |Non| E
    E("TAwaiter.OnCompleted()") -.-> D