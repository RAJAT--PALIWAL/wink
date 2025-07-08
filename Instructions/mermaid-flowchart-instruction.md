# 🧠 Mermaid Flowchart Generation Instruction

This template provides a ready-to-use instruction for GitHub Copilot (or ChatGPT) to generate a **detailed Mermaid flowchart** for an API. Specifically designed for codebases where an <<API_NAME>> API is implemented, this instruction guides Copilot to scan the logic and return a clean, styled visual flow.

---

## 📋 Instruction for GitHub Copilot or ChatGPT

Paste the following comment block directly above your OCR API implementation or in a relevant Markdown file:

```md

Generate a detailed Mermaid flowchart for the <<API_NAME>> API by scanning the code and identifying the key functional calls involved in the input processing and output generation.

🎯 Requirements:
- Use `flowchart TD` layout
- Clearly show the **input entry point** and **final output**
- Include intermediate function calls such as:
  - Pre-processing
  - Post-processing
  - Result formatting
- Highlight **error handling blocks** separately, if present
- Use different node styles or colors to distinguish:
  - Input/Output (green)
  - Processing steps (blue)
  - External services (gray)
  - Decision/Error nodes (red/orange)
- Keep edges clean and readable; avoid overlap
- Output must be valid Mermaid syntax only

```

## 📝 Viewing the File
To view the generated flowchart, ensure you have Mermaid support in your Markdown viewer or use a Mermaid live editor. The flowchart will visually represent the <<API_NAME>> API's logic, making it easier to understand the data flow and processing steps.

Copy the Mermaid code output by Copilot or ChatGPT and paste it into a Markdown file or a Mermaid live editor.

## 🌟 Example Output on OCRmyPDF Github Repo (https://github.com/ocrmypdf/OCRmyPDF)

### Input to Copilot or ChatGPT:

```md
Generate a detailed Mermaid flowchart for OCRmyPDF by scanning the code and identifying the key functional calls involved in the input processing and output generation.

🎯 Requirements:
- Use `flowchart TD` layout
- Clearly show the **input entry point** and **final output**
- Include intermediate function calls.
- Highlight **error handling blocks** separately, if present
- Use different node styles or colors to distinguish:
  - Input/Output (green)
  - Processing steps (blue)
  - External services (gray)
  - Decision/Error nodes (red/orange)
- Keep edges clean and readable; avoid overlap
- Output must be valid Mermaid syntax only
```

### Output from Copilot or ChatGPT:

```mermaid
flowchart TD
    subgraph Input_Group[Input]
        direction TB
        A[Input PDF File]:::green
        B[Configuration Options]:::green
    end

    subgraph Processing_Group[Processing Steps]
        direction TB
        C[Validate Input File]:::blue --> D[Preprocess PDF]:::blue
        D --> E[Split PDF into Pages]:::blue
        E --> F[Image Extraction]:::blue
        F --> G[Apply OCR using Tesseract]:::blue
        G --> H[Generate PDF with Text Layer]:::blue
        H --> I[Metadata and Optimization]:::blue
        I --> J[Merge Pages and Generate Output PDF]:::blue
    end

    subgraph Decision_Group[Decision Points]
        direction TB
        K{Check Input Validity}:::red --> L{Check PDF/A Compliance}:::red
    end

    subgraph Error_Group[Error Handling]
        direction TB
        M[Handle Invalid Input Error]:::orange
        N[Handle Processing Errors]:::orange
        O[Handle PDF/A Conversion Errors]:::orange
    end

    subgraph Output_Group[Output]
        direction TB
        P[Final Output Searchable PDF File]:::green
    end

    A --> K
    K -- Invalid --> M
    K -- Valid --> C
    C --> L
    L -- Not Compliant --> O
    L -- Compliant --> P
    P -- Process Complete --> Q[Success]
    D --> N
    F --> N
    G --> N
    H --> N

    style A fill:#00ff00,stroke:#000,stroke-width:2px
    style P fill:#00ff00,stroke:#000,stroke-width:2px
    style C fill:#0000ff,stroke:#000,stroke-width:2px
    style D fill:#0000ff,stroke:#000,stroke-width:2px
    style E fill:#0000ff,stroke:#000,stroke-width:2px
    style F fill:#0000ff,stroke:#000,stroke-width:2px
    style G fill:#0000ff,stroke:#000,stroke-width:2px
    style H fill:#0000ff,stroke:#000,stroke-width:2px
    style I fill:#0000ff,stroke:#000,stroke-width:2px
    style J fill:#0000ff,stroke:#000,stroke-width:2px
    style K fill:#ff0000,stroke:#000,stroke-width:2px
    style L fill:#ff0000,stroke:#000,stroke-width:2px
    style M fill:#ffa500,stroke:#000,stroke-width:2px
    style N fill:#ffa500,stroke:#000,stroke-width:2px
    style O fill:#ffa500,stroke:#000,stroke-width:2px

```
### Mermaid Flowchart:

![Mermaid flowchart showing OCRmyPDF processing steps, decision points, and error handling.](./OCRmyPDF_workflow_mermaid.png)