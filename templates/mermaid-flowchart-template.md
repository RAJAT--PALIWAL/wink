# 🧩 Mermaid Flowchart Template – Wink

This template helps you generate **detailed, visually distinctive Mermaid flowchart** using GitHub Copilot, ChatGPT, or manually. It ensures clean design, consistent colors, and professional structure — ideal for documenting engineering workflows, decision trees, and architecture.

---

## ✍️ Prompt/Instruction to Generate via AI

> Generate a detailed Mermaid flowchart that clearly represents the following process:  
> [🔁 Replace this with your own process description]  
> - Use rectangular nodes for steps  
> - Use vibrant, contrasting background colors to distinguish node types (e.g., decision, action, start/end)  
> - Ensure edges are non-overlapping and directional  
> - Add comments to explain complex branches  
> - Use modern fonts and aim for a visually clean layout  

---

## 🌈 Recommended Color Convention

| Node Type        | Shape        | Background Color | Mermaid Tag                      |
|------------------|--------------|------------------|----------------------------------|
| Start / End      | Rounded      | Light green      | `style start fill:#c6f6d5`       |
| Action Step      | Rectangle    | Light blue       | `style step fill:#bee3f8`        |
| Decision Point   | Diamond      | Yellow-orange    | `style decision fill:#fbd38d`    |
| External System  | Parallelogram| Light gray       | `style external fill:#e2e8f0`    |
| Error/Exception  | Hexagon      | Light red        | `style error fill:#fed7d7`       |

---

## 📐 Example Flowchart (Mermaid Syntax)

```mermaid
flowchart TD
    start((Start))
    step1[Receive Request]
    decision1{Is Request Valid?}
    step2[Process Data]
    error1{{Return Error}}
    external1[/External API Call/]
    step3[Format Response]
    end((End))

    start --> step1 --> decision1
    decision1 -- Yes --> step2 --> external1 --> step3 --> end
    decision1 -- No --> error1 --> end

    %% Styling
    style start fill:#c6f6d5,stroke:#38a169
    style step1 fill:#bee3f8,stroke:#3182ce
    style step2 fill:#bee3f8,stroke:#3182ce
    style step3 fill:#bee3f8,stroke:#3182ce
    style decision1 fill:#fbd38d,stroke:#dd6b20
    style error1 fill:#fed7d7,stroke:#e53e3e
    style external1 fill:#e2e8f0,stroke:#4a5568
    style end fill:#c6f6d5,stroke:#38a169
