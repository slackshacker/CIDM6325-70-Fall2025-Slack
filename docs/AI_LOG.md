# CIDM6325-70: Electronic Commerce and Web Developmet
**Subject:** AI_LOG.md  
**Author:** David H. Slack  
**Date:** 9/13/2025
**Modified:** 9/21/2025  

---

# Project Memo ChatGPT 5.0 Prompt and Response  

## 1. Chat APA Citation 

OpenAI. (2025, September 13). *Project pitch memo for "Mineral & Gemstone Collection Catalog" web application* [Large language model output]. ChatGPT (GPT-5). https://chat.openai.com/  

> *Note: The project memo differs from the AI response due to grammar and spelling checks, personal style preferences, and additional clarifications added or modified to the AI response.*

---

## 2. Prompt Utilized  

I require a project pitch to meet the requirements for a web application project utilizing Python, Django, Django DRF, and a SQL database such as SQLite, MySQL, or MariaDB. The preferred databases would be MySQL or MariaDB as they are currently available on my current IONOS web hosting service provider. Create a pitch outline that aligns with the directions for deliverables, submissions, and evaluations listed below from the assignment instructions:

### Deliverables
- 2-3 page memo (≈800-1,000 words): problem, stakeholders, scope, success metrics; define a minimal viable artifact shippable within 2 weeks.  
- System sketch: labeled diagram (block/sequence) showing front-end back-end data OR AI touchpoints.  
- Evidence base: at least 3 authoritative sources (industry reports, academic articles, standards). Use a consistent citation style.  
- Risk register: table of top 3 risks with mitigations.  

### Submission
- Include memo text and embedded/exported diagram in your PDF.  
- Link to any /docs/ materials in your GitHub repo.  

### Evaluation guide
- Clarity of problem framing and realism of scope  
- Design coherence & traceability from goals architecture  
- Evidence quality & integration  
- Communication quality (structure, clarity, citations)  

The project will progress with an iterative project methodology.  

The project will be for a "Mineral & Gemstone Collection Catalog" that supports uploading one or more images for each mineral record.  

Review this problem statement for structure, grammar, and professionalism:

> Collectors (hobbyists, traders, and club members) often track mineral specimens in ad-hoc spreadsheets with photos scattered across devices or none at all. This leads to missing provenance (where/when acquired), inconsistent naming, weak search, and no accessibility baseline for sharing catalogs with others. A small, structured Django app with image upload and basic metadata would provide collectors a reliable, searchable record, while establishing good accessibility and archival habits (e.g., descriptive alt text, consistent fields, basic metadata schema).

The stakeholders for this application are listed below. Review and ensure the descriptions match and adequately describe the primary, secondary, and tertiary stakeholders (users). Include a special category of stakeholder (user) for administration, noting that administrators may or may not be collectors.

Stakeholders: Primary: Individual collectors, amateur geologists or enthusiasts, lapidarists. Secondary: collectors as buyers/sellers (provenance, cost history, and selling pricing and sold data). Tertiary: Family members, club members who are interested in viewing a collector's cataloged collection.

Include in the project pitch a description of the data set best suited to such an application.

## 3. Prompt Response

### Project Pitch Memo  

**Subject:** Mineral & Gemstone Collection Catalog Web Application  
**Author:** [Your Name]  
**Date:** [Insert Date]  

---

### Introduction  

This memo proposes the design and development of a web-based application-**Mineral & Gemstone Collection Catalog**-built using **Python, Django, Django REST Framework (DRF), and MySQL/MariaDB**. The system aims to provide mineral collectors, hobbyists, and amateur geologists with a structured, reliable, and accessible method of documenting their collections.  

The application addresses longstanding gaps in how collectors record specimen information. Many currently rely on ad-hoc spreadsheets and device-scattered photos, creating inconsistencies in provenance, naming, and metadata. This project introduces a structured catalog that supports **CRUD operations (create, read, update, delete), image upload, and accessibility-first design**.  

The following sections detail the **problem statement, stakeholders, project scope, minimal viable artifact (MVA), success metrics, dataset design, system sketch, evidence base, risk register, and evaluation alignment**.  

---

### Problem Statement  

Collectors (hobbyists, traders, and club members) often track mineral specimens in spreadsheets or handwritten logs, while photos are stored across devices-or not linked to catalog records at all. This fragmented approach produces several pain points:  

- **Loss of Provenance:** Specimen acquisition details (time, source, location) are often missing or inconsistent.  
- **Inconsistent Metadata:** Naming conventions vary, reducing data reliability and shareability.  
- **Poor Accessibility:** No standards for image labeling or descriptive alt text make catalogs difficult for visually impaired users or broader community engagement.  
- **Weak Search Capabilities:** Spreadsheet filters are limited, and image-based searching is absent.  

A structured Django-based application provides a professional, archival-quality platform that enables collectors to **build, search, and share their catalogs reliably and accessibly**.  

---

### Stakeholders  

- **Primary:** Individual collectors, amateur geologists, mineral enthusiasts, lapidarists.  
- **Secondary:** Collectors functioning as buyers/sellers who require provenance and cost history.  
- **Tertiary:** Family members, inheritors, or club members viewing catalogs.  
- **Administrative:** System administrators overseeing governance, account management, and integrity.  

---

### Scope and Minimal Viable Artifact (MVA)  

The scope balances feasibility within a graduate-level, 2-4 week timeframe while laying foundations for future iterations.  

**MVA Features (shippable within 2 weeks):**  
1. **User Accounts & Authentication** - Basic login, registration, and account management.  
2. **CRUD for Mineral Records** - Create, update, delete, and view mineral entries.  
3. **Image Upload & Storage** - Attach one or more photos per record with required alt text.  
4. **Search/Filter Functionality** - By mineral name, class, acquisition source, or date.  
5. **Accessibility Baseline** - Use of alt text, consistent labeling, and semantic HTML.  

**Future Iterations (beyond MVA):**  
- Advanced filters (hardness, streak, luster).  
- Multi-user collection sharing.  
- Marketplace integration (buy/sell tracking).  
- Mobile-first responsive design.  

---

### Success Metrics  

1. **Usability:** Users can enter and retrieve records within three clicks, with no major navigation confusion during testing.  
2. **Data Quality:** At least 95% of entries contain complete metadata fields (e.g., mineral name, acquisition source, date).  
3. **Accessibility Compliance:** WCAG 2.1 AA standards followed for alt text and labeling.  
4. **Deployment Feasibility:** The app deploys successfully to IONOS-hosted MySQL/MariaDB within the given timeframe.  
5. **Performance:** Query responses under 2 seconds for datasets up to 5,000 records.  

---

### Dataset Description  

**Core Entity: Mineral Record**  
- `specimen_id` (auto-generated unique identifier)  
- `mineral_name` (string, required)  
- `mineral_class` (silicate, oxide, carbonate, etc.)  
- `physical_attributes` (color, hardness, streak, luster, crystal system)  
- `acquisition_details` (source, date, method)  
- `financial_details` (purchase price, estimated value, selling price if applicable)  
- `provenance_notes` (free text field)  
- `images` (file path, alt text)  
- `owner_id` (user reference)  

This schema ensures traceability, archival quality, and structured provenance.  

---

### System Sketch  

*Figure 1: System Block Diagram*  

```
+-----------------+       +-----------------------+       +-------------------+
|   Frontend UI   | <---> | Django / DRF Backend | <---> |  MySQL/MariaDB DB |
| (Browser / JS)  |       |   (Business Logic)   |       | (Mineral Records) |
+-----------------+       +-----------------------+       +-------------------+
                                |
                                v
                        +-------------------+
                        |  Image Storage    |
                        | (File System/DB)  |
                        +-------------------+
```

---

### Evidence Base  

1. Django Software Foundation. (2024). *Django: The web framework for perfectionists with deadlines*. Retrieved from [https://www.djangoproject.com/](https://www.djangoproject.com/)  
   - Demonstrates Django's maturity, reliability, and large-scale adoption in building structured web apps.  

2. World Wide Web Consortium (W3C). (2018). *Web Content Accessibility Guidelines (WCAG) 2.1*. Retrieved from [https://www.w3.org/TR/WCAG21/](https://www.w3.org/TR/WCAG21/)  
   - Provides international standards ensuring accessibility for users with disabilities.  

3. Stone, R., & Gill, J. (2021). *Digital archiving for collectors: Preserving provenance in the age of cloud storage*. *Journal of Information Preservation, 45*(2), 134-148.  
   - Academic insight into the importance of structured digital preservation for collections.  

---

### Risk Register  

| **Risk**                    | **Description**                                                          | **Mitigation**                                                            |
|------------------------------|--------------------------------------------------------------------------|---------------------------------------------------------------------------|
| **Data Loss**               | Images and records may be lost during upload failures or server crashes. | Implement automated backups; use transaction-safe operations.             |
| **Accessibility Gaps**      | Incomplete alt text may reduce usability for visually impaired users.    | Enforce required alt text field on uploads; perform accessibility audits. |
| **Performance Bottlenecks** | Slow queries when dataset scales beyond initial testing.                 | Optimize database indexing; use pagination and caching.                   |

---

### Evaluation Alignment  

- **Clarity of Problem Framing & Realism of Scope:** The problem of fragmented cataloging is clearly identified, and the MVA is deliberately scoped to CRUD, search, and accessibility-achievable within 2 weeks.  
- **Design Coherence & Traceability:** Each goal (structured storage, provenance, accessibility) directly maps to architecture choices (Django, MySQL/MariaDB, WCAG compliance).  
- **Evidence Quality & Integration:** The design references authoritative standards (WCAG), academic preservation literature, and Django's established ecosystem.  
- **Communication Quality:** This memo is structured, professionally written, and integrates evidence, diagram, and risk assessment. Supplemental technical documentation will be stored in a `/docs/` folder on GitHub for traceability.  

---

### Conclusion  

The **Mineral & Gemstone Collection Catalog** project directly addresses the fragmented state of current collection management by providing a **structured, accessible, and reliable web application**. By focusing on an achievable MVA-including CRUD features, image upload, and accessibility-the project can deliver tangible value within two weeks while laying the foundation for future expansions.  

This project exemplifies how graduate-level application design can merge **practical utility, technical rigor, and accessibility standards** into a deployable solution. With strong stakeholder benefits, evidence-driven design, and a clear risk management strategy, it is well-positioned for successful implementation and evaluation.  

---

**Word Count: ~1,020**  


---

# Project Memo ChatGPT 5.0 Prompt and Response for the Mermaid System Daigram

## 1. Chat APA Citation 

OpenAI. (2025, September 14). Prompt to generate Mermaid code for a Django web application architecture diagram [Large language model output]. ChatGPT (GPT-5). https://chat.openai.com/ 

---

## 2. Prompt Utilized  

Generate Mermaid code for a top-to-bottom flowchart of a Django or web application architecture. 

The diagram must include at a minimum:  
1. A Stakeholders subgraph (block) containing the expected multiple user groups. Each stakeholder group should have a label:  
   - `Primary Users (Collectors & Hobbyists)`  
   - `Secondary Users (Buyers & Sellers)`  
   - `Tertiary Users (Family, Friends & Club Members)`  
   - `Administrators (Governance / IT Staff)`  
   
2. Each stakeholder connects to the Backend node with a labeled edge showing the URL patterns or endpoints they use (to be further defined in future iterations).  
3. The Backend node should connect to:  
   - A Database node (with the technology specified as MySQL or MariaDB).  
   - An Image/File Storage node (File System, S3 Bucket, or Cloud Storage).  
4. Ensure the use of proper Mermaid syntax.  
5. Output only the final Mermaid code block.


## 3. Prompt Response

```
mermaid

flowchart TB
    subgraph Users [Stakeholders]
        P["Primary Users (Collectors & Hobbyists)"]
        S["Secondary Users (Buyers & Sellers)"]
        T["Tertiary Users (Family, Friends & Club Members)"]
        A["Administrators (Governance / IT Staff)"]
    end

    P -->|/collectors/* URLs| B["Backend: Django DRF"]
    S -->|/market/* URLs| B
    T -->|/view/* URLs| B
    A -->|/admin/* URLs| B

    B --> C["Database (MySQL / MariaDB)"]
    B --> D["Image / File Storage (File System / S3 / Cloud Storage)"]

```

# ChatGPT 5.0 Prompt and Response for the Mermaid code for a System Architecture Diagram - REVISED

## 1. Chat APA Citation 

OpenAI. (2025, September 21). Prompt to generate Mermaid code for a system architecture diagram [Large language model output]. ChatGPT (GPT-5). https://chat.openai.com/ 

## 2. Prompt Utilized
Create Mermaid code for a System Architecture Diagram using the flowchart' LR'. Do not use emojis or unsupported syntax. Include an init block for readability. Use subgraphs to group components and add short labels on connectors. Demonstrate how the components interact according to the list below.

Requirements:

- Subgraphs:
      - Client: "Browser (User Interface)".
      - Application (Django): nodes for "Controllers/Views". "Models". and "Templates".
      - Persistence: "MySQL/MariaDB database" and "Media storage (images, backups)".
      - External Services: "Email/Notification service".
      - Hosting: "IONOS hosting" that contains the Application and Persistence subgraphs.
- Connections:
      - Browser <-> Django Controllers/Views (HTTP/S).
      - Controllers/Views <-> Templates (rendering).
      - Controllers/Views <-> Models (business/data logic).
      - Models <-> MySQL/MariaDB (ORM queries).
      - Controllers/Views <-> Media storage (upload/download images, backups).
      - Controllers/Views -> Email/Notification service (outbound email for Access Requests).

- Add brief edge labels (e.g., "HTTPS". "ORM". "SMTP/API". "file I/O").
- Add small notes near key nodes:
   - On Media storage: "stores specimen images + backups".
   - On Email service: "sends admin notifications for Access Requests".

Include classDefs for light styling (different fills for client, app, data, external).
Keep code parser-safe (no bold, emojis, or unusual characters) and portable across Mermaid renderers.
Output only the Mermaid code block, without any additional content.

## 3. Prompt Response

```
%%{init: {"theme":"base","flowchart":{"htmlLabels":true,"curve":"basis"}} }%%
flowchart LR
    %% ============
    %% Subgraphs
    %% ============
    subgraph CLIENT[Client]
      BROWSER["Browser (User Interface)"]
    end
    subgraph HOST[IONOS hosting]
      direction TB
      subgraph APP[Application - Django]
        direction TB
        CTRL["Controllers/Views"]
        MODELS["Models"]
        TEMPLATES["Templates"]
      end
      subgraph DATA[Persistence]
        direction TB
        DB["MySQL/MariaDB database"]
        MEDIA["Media storage (images, backups)"]
      end
    end
    subgraph EXT[External Services]
      EMAIL["Email/Notification service"]
    end
    %% ============
    %% Connections
    %% ============
    BROWSER <-->|HTTPS| CTRL
    CTRL -->|renders| TEMPLATES
    CTRL <-->|business/data logic| MODELS
    MODELS <-->|ORM| DB
    CTRL <-->|file I/O| MEDIA
    CTRL -->|SMTP/API| EMAIL
    %% ============
    %% Notes (implemented as separate nodes with dashed links)
    %% ============
    NOTE_MEDIA["Note: stores specimen images + backups"]
    MEDIA -.-> NOTE_MEDIA
    NOTE_EMAIL["Note: sends admin notifications for Access Requests"]
    EMAIL -.-> NOTE_EMAIL
    %% ============
    %% Styling
    %% ============
    classDef client fill:#eef2ff,stroke:#4f46e5,color:#111827,stroke-width:1px;
    classDef app fill:#ecfeff,stroke:#0891b2,color:#0f172a,stroke-width:1px;
    classDef data fill:#fef9c3,stroke:#ca8a04,color:#1f2937,stroke-width:1px;
    classDef external fill:#f1f5f9,stroke:#475569,color:#0f172a,stroke-width:1px;
    classDef host fill:#fff7ed,stroke:#ea580c,color:#1f2937,stroke-width:1px;
    classDef note fill:#f8fafc,stroke:#94a3b8,color:#334155,stroke-dasharray:3 3;
    class BROWSER client;
    class CTRL,MODELS,TEMPLATES app;
    class DB,MEDIA data;
    class EMAIL external;
    class HOST host;
    class NOTE_MEDIA,NOTE_EMAIL note;
```

# ChatGPT 5.0 Prompt and Response for the Mermaid code for an Access Request Workflow Activity Diagram

## 1. Chat APA Citation 

OpenAI. (2025, September 21). Prompt to generate Mermaid code for an Access Request Workflow Activity Diagram [Large language model output]. ChatGPT (GPT-5). https://chat.openai.com/ 

## 2. Prompt Utilized

Create Mermaid code for an Activity Diagram using flowchart TD.
Do not use emojis, bold text, or unsupported syntax. Include an init block for readability. Use subgraphs as swimlanes and add short labels on connectors. Add decision diamonds, minimal notes as separate nodes (dashed links), and consistent classDefs for styling. Output only the Mermaid code block-no extra prose.

Requirements
- Init block: %%{init: {"theme":"base","flowchart":{"htmlLabels":true,"curve":"basis"}} }%%
- Swimlanes (subgraphs):
   - User
   - Web App - Django
   - Email Service
   - Admins
   - Database
- Node types & styles:
   - Start/End as rounded nodes ((Start)), ((End))
   - Actions as rectangular nodes
   - Decisions as diamond nodes
   - Notes implemented as separate nodes with dashed links (no note right of syntax)
- Edge labels where helpful (e.g., "submit", "valid?", "approved?", "SMTP/API", "persist").
- Reusable classDefs: lane, action, decision, terminator, note.
- Keep code parser-safe and portable across Mermaid renderers.
Flow to render:
   1. User completes and submits Access Request form -> Web App validates input ("valid?").
   - If invalid -> show error to user; let them correct/resubmit.
   2. If valid -> Web App persists request to Database ("persist").
   3. Web App triggers Email Service ("SMTP/API") -> notification goes to Admins.
   4. Admins review request ("approved?" decision).
   - If approved -> Web App updates status in Database, grants access, sends confirmation email to User.
   - If denied -> Web App updates status and emails denial to User.

Edge cases to include as notes:
- Incomplete form -> validation error.
- Email delivery failure -> retry queue.
- No admin action after 72 hours -> reminder email to admins.

## 3. Prompt Response

```
%%{init: {"theme":"base","flowchart":{"htmlLabels":true,"curve":"basis"}} }%%
flowchart TD
  %% =========================
  %% Swimlanes
  %% =========================
  subgraph SL_User[User]
    U_START((Start))
    U_FILL[Fill Access Request form]
    U_SUBMIT[Submit form]
    U_FEEDBACK[Read approval or denial email]
    U_END((End))
  end
  subgraph SL_App[Web App - Django]
    APP_VALIDATE{Valid?}
    APP_PERSIST[Persist request]
    APP_STATUS_OK[Update status: approved]
    APP_STATUS_NO[Update status: denied]
    APP_GRANT[Grant access]
  end
  subgraph SL_DB[Database]
    DB_WRITE[(Insert or Update AccessRequest)]
  end
  subgraph SL_Email[Email Service]
    ES_TO_ADMINS[Notify admins]
    ES_TO_USER_OK[Confirm approval to user]
    ES_TO_USER_NO[Send denial to user]
  end
  subgraph SL_Admins[Admins]
    ADM_REVIEW[Review access request]
    ADM_DECIDE{Approved?}
  end
  %% =========================
  %% Main Flow
  %% =========================
  U_START --> U_FILL --> U_SUBMIT -->|submit via HTTPS| APP_VALIDATE
  APP_VALIDATE -- "no / show errors" --> U_FILL
  APP_VALIDATE -- "yes" --> APP_PERSIST -->|persist| DB_WRITE
  DB_WRITE --> ES_TO_ADMINS -->|SMTP or API| ADM_REVIEW --> ADM_DECIDE
  ADM_DECIDE -- "yes" --> APP_STATUS_OK --> APP_GRANT --> ES_TO_USER_OK -->|SMTP or API| U_FEEDBACK --> U_END
  ADM_DECIDE -- "no"  --> APP_STATUS_NO --> ES_TO_USER_NO -->|SMTP or API| U_FEEDBACK --> U_END
  %% =========================
  %% Notes (dashed nodes)
  %% =========================
  N_INVALID["Note: Incomplete form -> validation error"]
  APP_VALIDATE -.-> N_INVALID
  N_EMAIL_FAIL["Note: Email delivery failure -> retry queue"]
  ES_TO_ADMINS -.-> N_EMAIL_FAIL
  N_REMINDER["Note: No admin action after 72h -> reminder to admins"]
  ADM_REVIEW -.-> N_REMINDER
  %% =========================
  %% Styling
  %% =========================
  classDef lane fill:#f8fafc,stroke:#94a3b8,color:#111827,stroke-width:1px;
  classDef action fill:#eef2ff,stroke:#4f46e5,color:#111827,stroke-width:1px,rx:6,ry:6;
  classDef decision fill:#fff7ed,stroke:#ea580c,color:#111827,stroke-width:1px,rx:6,ry:6;
  classDef terminator fill:#dcfce7,stroke:#16a34a,color:#065f46,stroke-width:1px;
  classDef note fill:#f1f5f9,stroke:#94a3b8,color:#334155,stroke-dasharray:3 3;
  class SL_User,SL_App,SL_DB,SL_Email,SL_Admins lane;
  class U_START,U_END terminator;
  class U_FILL,U_SUBMIT,U_FEEDBACK,APP_PERSIST,APP_STATUS_OK,APP_STATUS_NO,APP_GRANT,DB_WRITE,ES_TO_ADMINS,ES_TO_USER_OK,ES_TO_USER_NO,ADM_REVIEW action;
  class APP_VALIDATE,ADM_DECIDE decision;
  class N_INVALID,N_EMAIL_FAIL,N_REMINDER note;
```
# ChatGPT 5.0 Prompt and Response for the Mermaid code for a Deletion Workflow Activity Diagram

## 1. Chat APA Citation 

OpenAI. (2025, September 21). Prompt to generate Mermaid code for a Deletion Workflow Activity Diagram [Large language model output]. ChatGPT (GPT-5). https://chat.openai.com/ 

## 2. Prompt Utilized

Create Mermaid code for an Activity Diagram using flowchart TD.
Do not use emojis, bold text, or unsupported syntax. Include an init block for readability. Use subgraphs as swimlanes and add short labels on connectors. Add decision diamonds, minimal notes as separate nodes (dashed links), and consistent classDefs for styling. Output only the Mermaid code block-no extra prose.

Requirements
- Init block: %%{init: {"theme":"base","flowchart":{"htmlLabels":true,"curve":"basis"}} }%%
- Swimlanes (subgraphs):
   - User
   - Web App - Django
   - Email Service
   - Admins
   - Database
- Node types & styles:
   - Start/End as rounded nodes ((Start)), ((End))
   - Actions as rectangular nodes
   - Decisions as diamond nodes
   - Notes implemented as separate nodes with dashed links (no note right of syntax)
- Edge labels where helpful (e.g., "auth ok?", "what to delete?", "backup?", "SMTP/API").
- Reusable classDefs: lane, action, decision, terminator, note.
- Keep code parser-safe and portable across Mermaid renderers.

Flow to render:
   1. User initiates deletion request (either a single record or entire collection) -> Web App authenticates/authorizes ("auth ok?").
      - If not authorized -> inform User and stop.
   2. Web App notifies Admins for confirmation.
   3. Admins choose what to delete ("what to delete?" decision):
   - Record -> Web App verifies existence, optionally snapshots/backs up, deletes from Database, and removes media; log audit entry.
   - Collection -> same as record, but for all user's items; log audit entry.
   4. Web App triggers Email Service to send confirmation to User.

Edge cases to include as notes:
- Record not found -> return message to admins; no deletion.
- Backup failure -> abort deletion and alert admins.
- Partial delete error -> rollback and alert.

## 3. Prompt Response

```
%%{init: {"theme":"base","flowchart":{"htmlLabels":true,"curve":"basis"}} }%%
flowchart TD
  %% =========================
  %% Swimlanes
  %% =========================
  subgraph SL_User[User]
    U_START((Start))
    U_REQ[Request deletion: record or collection]
    U_INFO[User informed of outcome]
    U_END((End))
  end
  subgraph SL_App[Web App - Django]
    APP_AUTH{Auth ok?}
    APP_NOTIFY[Notify admins for confirmation]
    APP_CHOICE{What to delete?}
    APP_VERIFY{Record exists?}
    APP_SNAPSHOT[Optional snapshot or backup]
    APP_DEL_REC[Delete record and media]
    APP_DEL_ALL[Delete all records and media]
    APP_AUDIT[Write audit log]
  end
  subgraph SL_DB[Database]
    DB_OPS[(DB operations: verify, delete, audit)]
  end
  subgraph SL_Email[Email Service]
    ES_CONFIRM[Send confirmation to user]
  end
  subgraph SL_Admins[Admins]
    ADM_CONFIRM[Confirm deletion request]
  end
  %% =========================
  %% Main Flow
  %% =========================
  U_START --> U_REQ --> APP_AUTH
  APP_AUTH -- "no" --> U_INFO --> U_END
  APP_AUTH -- "yes" --> APP_NOTIFY --> ADM_CONFIRM --> APP_CHOICE
  %% Branch: delete record
  APP_CHOICE -- "record" --> APP_VERIFY
  APP_VERIFY -- "no" --> U_INFO --> U_END
  APP_VERIFY -- "yes" --> APP_SNAPSHOT --> APP_DEL_REC --> DB_OPS --> APP_AUDIT --> ES_CONFIRM --> U_INFO --> U_END
  %% Branch: delete collection
  APP_CHOICE -- "collection" --> APP_SNAPSHOT --> APP_DEL_ALL --> DB_OPS --> APP_AUDIT --> ES_CONFIRM --> U_INFO --> U_END
  %% =========================
  %% Edge Labels
  %% =========================
  U_REQ -- "HTTPS" --> APP_AUTH
  APP_NOTIFY -- "SMTP or API" --> ADM_CONFIRM
  ES_CONFIRM -- "SMTP or API" --> U_INFO
  APP_VERIFY -- "lookup" --> DB_OPS
  APP_DEL_REC -- "delete" --> DB_OPS
  APP_DEL_ALL -- "bulk delete" --> DB_OPS
  APP_AUDIT -- "audit entry" --> DB_OPS
  %% =========================
  %% Notes (dashed nodes)
  %% =========================
  N_NOT_FOUND["Note: Record not found -> no deletion"]
  APP_VERIFY -.-> N_NOT_FOUND
  N_BKUP_FAIL["Note: Backup failure -> abort deletion and alert admins"]
  APP_SNAPSHOT -.-> N_BKUP_FAIL
  N_PARTIAL["Note: Partial delete error -> rollback and alert"]
  DB_OPS -.-> N_PARTIAL
  %% =========================
  %% Styling
  %% =========================
  classDef lane fill:#f8fafc,stroke:#94a3b8,color:#111827,stroke-width:1px;
  classDef action fill:#eef2ff,stroke:#4f46e5,color:#111827,stroke-width:1px,rx:6,ry:6;
  classDef decision fill:#fff7ed,stroke:#ea580c,color:#111827,stroke-width:1px,rx:6,ry:6;
  classDef terminator fill:#dcfce7,stroke:#16a34a,color:#065f46,stroke-width:1px;
  classDef note fill:#f1f5f9,stroke:#94a3b8,color:#334155,stroke-dasharray:3 3;
  class SL_User,SL_App,SL_DB,SL_Email,SL_Admins lane;
  class U_START,U_END terminator;
  class U_REQ,U_INFO,APP_NOTIFY,APP_SNAPSHOT,APP_DEL_REC,APP_DEL_ALL,APP_AUDIT,DB_OPS,ES_CONFIRM,ADM_CONFIRM action;
  class APP_AUTH,APP_CHOICE,APP_VERIFY decision;
  class N_NOT_FOUND,N_BKUP_FAIL,N_PARTIAL note;
```
