# Organization Roles and Information Flow

Notes on typical roles, teams, and information flows in a product/engineering organization (tech company context). Combines general practices with Scrum elements and higher-level strategy.

Each entity appears only once in the diagram. Tech Lead is a role within Engineering (not a separate entity). Product covers both day-to-day Product Management and Product Leadership.

In many teams (especially smaller or technical ones) there is no dedicated designer. The PM provides a rough sense of the desired UX; Engineering does the concrete design while building, because technical feasibility and constraints are often only clear during implementation.

## Key Roles

- **Market / Customers**: Source of needs, pain points, usage signals.
- **GTM (Sales / Marketing / Customer Success / Support)**: Collects market signals, competitive intel, feature requests; receives enablement on what was built.
- **Product**: Owns what and why; prioritizes problems and outcomes; filters inputs; sets product strategy and portfolio allocation; partners on execution. Includes PM and product leadership. Provides rough UX intent and acceptance criteria.
- **Engineering**: Builds the product; owns technical strategy, architecture, capacity, people, and delivery. Includes Engineers, Tech Lead (technical direction within the team), Engineering Manager (people & process), and Engineering Leadership (VP Eng / CTO). Often owns the concrete UI/interaction design because feasibility is discovered while building.
- **QA**: Verifies stability, correctness, regression; provides quality status.

## Information Flows (point form)

### Market inputs
- Market / Customers → GTM: needs, feedback, competitive info.
- GTM → Product: market signals, feature requests, win/loss, customer pain.

### Strategy formation
- Product ↔ Engineering: jointly form product + engineering strategy, capacity allocation (features vs platform vs debt), OKR alignment.

### Execution
- Product → Engineering / QA: prioritized problems, outcomes, rough UX intent, acceptance criteria.
- Engineering → Product / QA: feasibility, constraints, concrete design decisions, what was built, how it works, limitations.
- QA → Product / Engineering: stability, bugs, coverage, quality status.

### Scrum-related loops
- Backlog Refinement: Product + Engineering + QA clarify items, acceptance criteria, risks, and rough UX.
- Sprint Planning: Product proposes Sprint Goal; Engineering + QA commit and break down work.
- Daily Scrum: Engineering (+ QA) sync progress and blockers toward Sprint Goal.
- Sprint Review / Demo: Engineering shows Increment to Product (+ stakeholders including GTM); inspect if it matches intent; collect feedback.
- Sprint Retrospective: Product + Engineering + QA improve process, handoffs, quality.
- Definition of Done: shared checklist (code review, tests, QA verification, docs, Product acceptance).
- Increment: potentially releasable; basis for review and enablement.

### Outside Scrum (strategic / continuous)
- Product discovery & research (customer interviews, competitive analysis) runs in parallel; feeds backlog.
- Roadmap & release planning (quarterly): Product + Engineering capacity.
- Architecture & technical strategy: Engineering leadership; tech debt investment agreed with Product.
- Go-to-market & enablement: after Increment accepted — positioning, demo scripts, sales collateral (Product + Engineering → GTM).
- Metrics & outcome reviews: usage data, quality trends, revenue impact → adjust roadmap.
- Cross-team dependencies, security/compliance, incident management, hiring.
- Leadership alignment within Product and Engineering, plus cross-functional portfolio reviews.

### Enablement and feedback
- Engineering (+ Product) → GTM: how to use what was built, use cases, limitations, demo scripts.
- Usage + quality data from production → back to Product, Engineering, QA for next prioritization.

## Mermaid Diagram

Entities appear only once. Every arrow is labeled with the information that flows.

**Arrow colors:**
- **Red**: information from the market into the company
- **Light blue**: soft information (prioritized problems, outcomes, rough UX intent, acceptance criteria, positioning)
- **Blue**: hard information from the product and code (what was built, how it works, limitations, quality status, enablement)
- **Purple**: bidirectional joint strategy

```mermaid
flowchart TD
    Market["Market / Customers"]
    GTM["GTM\nSales / Marketing / CS / Support"]
    Product["Product\n(PM + Leadership)"]
    Engineering["Engineering\n(Engineers, Tech Lead, EM, Leadership)"]
    QA["QA"]

    Market -->|"needs, feedback,\ncompetitive info"| GTM
    GTM -->|"market signals,\nfeature requests,\nwin/loss"| Product

    Product <-->|"joint strategy,\ncapacity allocation,\nOKRs"| Engineering

    Product -->|"prioritized problems,\noutcomes, rough UX intent,\nacceptance criteria"| Engineering
    Product -->|"requirements,\nacceptance criteria"| QA

    Engineering -->|"feasibility, concrete design,\nwhat was built, how it works,\nlimitations"| Product
    Engineering -->|"what was built,\nhow it works,\ntest areas, limitations"| QA
    Engineering -->|"enablement:\nhow to use, demos,\nlimitations"| GTM

    QA -->|"stability, bugs,\nquality status"| Product
    QA -->|"stability, bugs,\nquality status"| Engineering

    Product -->|"positioning,\nlaunch readiness,\ncontext"| GTM

    %% Colors by information type
    %% 0-1: market into company
    linkStyle 0 stroke:#c62828,stroke-width:2px
    linkStyle 1 stroke:#c62828,stroke-width:2px
    %% 2: bidirectional strategy
    linkStyle 2 stroke:#6a1b9a,stroke-width:2px
    %% 3,4,10: soft info (light blue)
    linkStyle 3 stroke:#64b5f6,stroke-width:2px
    linkStyle 4 stroke:#64b5f6,stroke-width:2px
    linkStyle 10 stroke:#64b5f6,stroke-width:2px
    %% 5-9: hard info (blue)
    linkStyle 5 stroke:#1565c0,stroke-width:2px
    linkStyle 6 stroke:#1565c0,stroke-width:2px
    linkStyle 7 stroke:#1565c0,stroke-width:2px
    linkStyle 8 stroke:#1565c0,stroke-width:2px
    linkStyle 9 stroke:#1565c0,stroke-width:2px

    classDef external fill:#e1f5fe,stroke:#01579b
    classDef gtm fill:#fff3e0,stroke:#e65100
    classDef product fill:#e8f5e9,stroke:#1b5e20
    classDef eng fill:#f3e5f5,stroke:#4a148c
    classDef qa fill:#ffebee,stroke:#b71c1c

    class Market external
    class GTM gtm
    class Product product
    class Engineering eng
    class QA qa
```

## Notes

- Tech Lead is a role inside Engineering, not a separate entity.
- Product covers both individual Product Managers and Product Leadership (VP Product / CPO).
- Engineering covers individual Engineers, Tech Leads, Engineering Managers, and Engineering Leadership.
- No separate Design role is assumed. PM supplies rough UX direction; Engineering owns concrete design decisions because technical constraints surface during implementation.
- Flows are bidirectional in practice (partnership model); arrows show primary direction of key information and are all labeled.
- Higher-level strategy sits outside the sprint cadence; Scrum handles delivery inspection and adaptation.
- Arrow colors: red = market into the company; light blue = soft info (problems, intent, acceptance criteria, positioning); blue = hard info (what was built, how it works, quality, enablement); purple = bidirectional strategy.

---

*Generated from discussion on organization structure and information flow.*
