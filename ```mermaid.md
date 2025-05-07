```mermaid
flowchart TD
    %% States
    S0["[Period, EW congestion level, WE congestion level]"]
    S1["[Period, EW congestion level, WE congestion level]"]

    %% Actions
    A1["Allocate extra eastbound lane"]
    A2["Allocate extra westbound lane"]
    A3["Maintain current lane configuration"]

    %% Transitions from state to actions
    S0 -->|P(s' ∣ s,a)| A1
    S0 -->|P(s' ∣ s,a)| A2
    S0 -->|P(s' ∣ s,a)| A3

    %% Transitions from actions to next state with rewards
    A1 -->|R(s,a) = – total delay| S1
    A2 -->|R(s,a) = – total delay| S1
    A3 -->|R(s,a) = – total delay| S1
```