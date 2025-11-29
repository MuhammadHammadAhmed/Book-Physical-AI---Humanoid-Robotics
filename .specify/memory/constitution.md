# Project Constitution: AI-Powered Interactive Book

## Preamble

This constitution outlines the principles and technical directives for the "AI-Powered Interactive Book" hackathon project. Our mission is to create a seamless, interactive learning experience by unifying AI-generated book content with an intelligent, context-aware chatbot, all driven by a spec-first methodology.

---

### **Article I: Core Principles**

1.  **Spec-Driven Development (SDD):** All development, for both the book and the chatbot, must begin with a clear and approved specification. The `spec-kit-plus` methodology (`/sp.specify`, `/sp.plan`, `/sp.tasks`) is mandatory to ensure clarity, alignment, and structured execution.
2.  **AI-Assisted Content Generation:** Claude Code shall be the primary tool for generating all book content. This ensures a consistent voice, accelerates the writing process, and aligns with the project's AI-first nature.
3.  **Modular and API-First Architecture:** The system will be architected with a clean separation of concerns. The chatbot backend will be a distinct FastAPI application, communicating with the frontend via a well-defined API.
4.  **Continuous Deployment:** The project will leverage automation for deployment. The Docusaurus book will be automatically deployed to GitHub Pages upon merges to the `main` branch.

---

### **Article II: Book Development & Deployment**

1.  **Framework:** Docusaurus is the sole and exclusive framework for building the book's structure, user interface, and reading experience.
2.  **Content Source:** All primary book chapters and sections will be generated as Markdown files by Claude Code, guided by specifications created with `spec-kit-plus`.
3.  **Deployment Target:** The final, published book will be hosted on GitHub Pages, deployed via GitHub Actions.
4.  **Styling:** The book will adhere to Docusaurus's standard theme (Infima) to maintain a clean, accessible, and readable interface. Customization will be minimal and purposeful.

---

### **Article III: RAG Chatbot Development**

1.  **Backend Framework:** The chatbot's backend API will be built exclusively using FastAPI.
2.  **AI and Orchestration:** The core chatbot logic, including agentic capabilities and tool usage, will be implemented using the **OpenAI Agents SDK** and **ChatKit SDK**.
3.  **Vector Storage:** **Qdrant Cloud (Free Tier)** is the designated vector database. All book content must be chunked, embedded, and indexed in a Qdrant collection to power the RAG functionality.
4.  **Relational Data (If required):** If any relational data persistence is needed (e.g., for conversation history, user profiles), **Neon Serverless Postgres** is the approved database.
5.  **Core Functionality:** The chatbot must fulfill two primary functions:
    *   **Global Q&A:** Answer user questions based on the entire knowledge base of the book.
    *   **Contextual Q&A:** Answer user questions based *only* on a specific snippet of text that the user has selected within the book's interface.

---

### **Article IV: Approved Technology Stack**

To ensure focus and interoperability, the project will be limited to the following technologies:

-   **Book Framework:** Docusaurus
-   **Content Generation:** Claude Code
-   **Development Methodology:** Spec-Kit Plus
-   **Deployment:** GitHub Pages (for book), Vercel/Render (for backend)
-   **Chatbot Backend:** FastAPI
-   **Chatbot SDKs:** OpenAI Agents SDK, ChatKit SDK
-   **Vector Database:** Qdrant Cloud (Free Tier)
-   **Relational Database:** Neon Serverless Postgres

---

### **Article V: Integration and Quality Standards**

1.  **Chatbot Integration:** The chatbot's user interface must be embedded as a React component within the Docusaurus application, providing a non-intrusive and seamless user experience.
2.  **Content Quality:** All AI-generated content must be reviewed for technical accuracy, coherence, and readability before being committed. The final book should be professional and polished.
3.  **Chatbot Performance:** The chatbot must provide accurate, relevant, and low-latency responses. It must gracefully handle queries that are outside its knowledge base, clearly indicating the limits of its context.
4.  **End-to-End Testing:** The final deliverable must pass end-to-end tests verifying that on the live GitHub Pages site, a user can:
    *   Open and interact with the chatbot.
    *   Receive accurate answers to general questions about the book.
    *   Select a paragraph of text and receive an accurate answer based only on that selection.