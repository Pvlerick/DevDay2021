graph LR
    A(Appelant) --> |await| C{Task terminée?}
    C --> |Oui| D(Suite de l'execution)
    C --> |Non| F(Retour à l'appelant)
    F -.-> |Task terminée| E(Continuation)
    E --> D

