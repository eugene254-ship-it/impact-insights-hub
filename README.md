# Atlas Sanctum — Impact Valuation Dashboards

> **Turn environmental impact into measurable, verifiable, and traceable value.**

The **Impact Valuation Dashboard Suite** is the asset intelligence layer of Atlas Sanctum.

It provides a structured interface for understanding the financial and ecological value created by environmental assets such as:

* carbon credits
* biodiversity units
* water credits
* other verified impact assets

The suite connects three critical workflows:

```text id="7psr1p"
Measure Impact
      ↓
Value Impact
      ↓
Register Asset
      ↓
Verify Asset
      ↓
Track Ownership
      ↓
Transfer / Retire
```

The objective is not simply to show environmental numbers.

It is to create a transparent bridge between:

> **impact → verification → valuation → asset lifecycle**

---

# 1. Product Suite

The Impact Valuation system consists of three primary dashboards:

### A. Impact Dashboard

Measures and values environmental impact.

### B. Asset Registry Dashboard

Tracks the lifecycle, ownership, and status of verified impact assets.

### C. Verification Interface

Allows authorized third parties to compare source data against computed impact and approve or reject asset creation.

Together they form a complete impact-asset workflow.

---

# 2. Core Product Questions

The suite should make it easy to answer:

> **How much impact was created?**

> **What is that impact worth?**

> **Which assets represent the impact?**

> **Who owns those assets?**

> **Has the impact been independently verified?**

> **Where is the asset in its lifecycle?**

These questions should be answerable without forcing users to navigate across disconnected systems.

---

# 3. A. Impact Dashboard

## Overview

The Impact Overview is the executive entry point.

The hero metric should be:

```text id="z8r5v4"
TOTAL IMPACT VALUE

$XX.XM
```

This represents the current estimated market value of verified impact assets represented within the selected scope.

### Breakdown

```text id="kyy1bb"
Carbon Credits       $X.XM
Biodiversity Units   $X.XM
Water Credits        $X.XM
Other Assets         $X.XM
```

Filters should support:

* date range
* asset type
* geography
* project
* owner
* verification status
* currency

---

# 4. Impact Value Over Time

The main overview chart should show how aggregate impact value changes over time.

Example:

```text id="ib3btx"
Impact Value

$M
│
│                     ╭──────
│                ╭────╯
│           ╭────╯
│      ╭────╯
│──────╯
└────────────────────────────
 Jan  Feb  Mar  Apr  May  Jun
```

Users should be able to switch between:

* total value
* volume
* price
* newly created assets
* verified assets
* retired assets

The graph should distinguish between **asset growth** and **market-price movement** where possible.

---

# 5. Impact Detail

Selecting an asset type opens a detailed valuation view.

Example:

### Carbon

```text id="gjgo57"
Tonnes CO₂e
125,000

Price / tonne
$42

Estimated Value
$5.25M
```

The detail view should show:

* total impact volume
* unit of measurement
* price per unit
* total valuation
* historical value
* historical price
* verification status
* geography
* underlying projects
* asset count
* ownership distribution

---

# 6. Valuation Methodology

Impact valuation should never be presented as an unexplained number.

The interface should expose how value was calculated.

Example:

```text id="5axf2a"
Impact Volume
125,000 tCO₂e

×
Market Price
$42 / tCO₂e

=
Estimated Asset Value
$5,250,000
```

Where multiple valuation methods exist, the UI should identify:

* valuation source
* market reference
* valuation timestamp
* currency
* pricing methodology
* assumptions
* confidence

This creates a clean distinction between:

**measured impact**

and

**estimated market value**.

---

# 7. Supported Impact Assets

The initial architecture should support:

## Carbon

Measured in units such as:

```text
tCO₂e
```

Potential metrics:

* tonnes avoided
* tonnes removed
* tonnes sequestered
* credit volume
* price per tonne
* total value

---

## Biodiversity

Potential units:

* biodiversity units
* habitat hectares
* ecosystem condition units
* species preservation metrics

The UI should support asset-specific methodologies rather than forcing biodiversity into a carbon-shaped model.

---

## Water

Potential units:

* cubic metres conserved
* watershed units
* water-quality improvement units
* verified water credits

Again, methodology must remain explicit.

---

# 8. B. Asset Registry Dashboard

The Asset Registry is the system of record for impact assets represented inside Atlas.

## Asset List

The main registry table should contain:

| Asset ID  | Type         | Owner          | Status   |
| --------- | ------------ | -------------- | -------- |
| CAR-00128 | Carbon       | Organization A | Verified |
| BIO-00917 | Biodiversity | Organization B | Pending  |
| WAT-00481 | Water        | Organization C | Sold     |

Additional useful columns:

* quantity
* valuation
* geography
* project
* verification date
* creation date
* retirement date
* current holder
* registry status

---

# 9. Asset Status

Recommended lifecycle states:

```text id="ezmx4v"
DRAFT
CREATED
PENDING VERIFICATION
VERIFIED
LISTED
TRANSFERRED
SOLD
RETIRED
REJECTED
CANCELLED
```

Status should be visually obvious and consistent throughout the product.

---

# 10. Asset Detail

Selecting an asset opens a complete lifecycle view.

Example:

```text id="v2p8dj"
Asset: CAR-00128

Carbon
100 tCO₂e

Status:
VERIFIED

Current Owner:
Organization A
```

---

# 11. Asset Lifecycle

The detail page should present the full lifecycle visually:

```text id="19v9t1"
Created
   ↓
Measured
   ↓
Verified
   ↓
Registered
   ↓
Transferred
   ↓
Sold
   ↓
Retired
```

Each event should include:

* timestamp
* actor
* status
* transaction reference
* evidence
* associated valuation
* relevant documentation

This creates a persistent audit trail.

---

# 12. Ownership Chain

The ownership history should use a blockchain-inspired visual model.

Example:

```text id="q3sf8c"
Project Owner
      │
      ↓
Verification Entity
      │
      ↓
Original Holder
      │
      ↓
Market Participant
      │
      ↓
Current Owner
```

Each ownership transition should expose:

* previous owner
* new owner
* timestamp
* quantity transferred
* transaction ID
* registry reference
* status

The visual should communicate provenance without requiring users to understand blockchain infrastructure.

---

# 13. Asset Detail Information Architecture

A complete asset page can be structured as:

```text id="u8mdy9"
Asset Header
│
├── Status
├── Quantity
├── Current Value
├── Current Owner
│
├── Lifecycle Timeline
├── Ownership Chain
├── Impact Measurements
├── Verification Evidence
├── Valuation History
├── Transactions
└── Documents
```

This creates a single source of truth for an asset's lifecycle.

---

# 14. C. Verification Interface

The Verification Interface is designed for independent third-party reviewers.

Its primary purpose is simple:

> **Does the computed impact accurately represent the underlying evidence?**

The interface should prioritize evidence over decoration.

---

# 15. Side-by-Side Verification

The central view should compare:

```text
┌───────────────────────┬───────────────────────┐
│ RAW SOURCE DATA       │ COMPUTED IMPACT       │
├───────────────────────┼───────────────────────┤
│ Measurements          │ Calculated volume     │
│ Source documents      │ Impact methodology    │
│ Sensor readings       │ Derived metrics       │
│ Field observations    │ Asset quantity        │
│ Geographic evidence   │ Valuation output      │
└───────────────────────┴───────────────────────┘
```

The reviewer should be able to trace:

```text
Source
  ↓
Measurement
  ↓
Calculation
  ↓
Impact
  ↓
Asset
```

---

# 16. Verification Actions

The core actions are:

```text id="n15h3w"
APPROVE

REJECT
```

But those actions should not exist without context.

Before approval, the reviewer should be able to inspect:

* source data
* calculation method
* assumptions
* impact quantity
* uncertainty
* evidence quality
* previous verification history

A rejection should support a reason.

Example:

```text id="1v2u2p"
REJECT ASSET

Reason:
Impact calculation cannot be reproduced
from submitted source data.

Issue:
Missing measurement period.
```

---

# 17. Verification States

```text id="9g6xci"
NOT SUBMITTED
UNDER REVIEW
MORE EVIDENCE REQUIRED
APPROVED
REJECTED
EXPIRED
REQUIRES REVALIDATION
```

Verification status should appear consistently across:

* asset registry
* impact dashboard
* asset detail
* reporting
* valuation views

---

# 18. Verification Evidence

The verifier should have access to evidence such as:

* raw measurements
* satellite observations
* sensor records
* field reports
* project documentation
* methodology version
* calculation logs
* geographic coordinates
* timestamps
* supporting media where available

The interface should clearly separate:

**submitted evidence**

from

**derived calculations**.

---

# 19. Verification Decision Panel

The reviewer should receive a concise summary:

```text id="0gj2j4"
ASSET VERIFICATION

Asset:
CAR-00128

Claimed impact:
100 tCO₂e

Evidence coverage:
94%

Calculation reproducibility:
PASS

Methodology:
Carbon Method v2.3

Data quality:
HIGH

Outstanding issues:
None
```

Then:

```text id="qf9i7y"
[ APPROVE ]

[ REJECT ]
```

The final action should always be accompanied by an audit record.

---

# 20. Impact-to-Asset Flow

The complete experience should connect impact measurement to asset creation:

```text id="z5wjm5"
Environmental Activity
        ↓
Raw Measurements
        ↓
Impact Calculation
        ↓
Verification
        ↓
Asset Creation
        ↓
Valuation
        ↓
Registry
        ↓
Transfer / Sale
        ↓
Retirement
```

This is the central architecture of the Impact Valuation system.

---

# 21. Frontend Architecture

Recommended stack:

```text id="7c3svr"
Next.js
React
TypeScript
Tailwind CSS

TanStack Query
Zustand / Redux Toolkit

ECharts / Recharts / D3

React Table / TanStack Table

Mapbox / deck.gl
```

### Responsibilities

**Next.js / React**

Application structure and routing.

**TypeScript**

Strong impact and asset-domain contracts.

**Tailwind**

Reusable design system.

**TanStack Query**

Server state and cached registry data.

**Zustand / Redux Toolkit**

Shared filters, selected assets, valuation state, and verification state.

**ECharts / Recharts / D3**

Valuation trends and impact analytics.

**TanStack Table**

Large asset registry datasets.

**Mapbox / deck.gl**

Optional geospatial project and asset visualization.

---

# 22. Suggested Component Architecture

```text id="j2v8xk"
ImpactValuationDashboard
│
├── ImpactOverview
│   ├── TotalImpactValue
│   ├── ImpactBreakdown
│   └── ImpactValueChart
│
├── ImpactDetail
│   ├── AssetTypeSelector
│   ├── ImpactMetrics
│   ├── ValuationSummary
│   └── ValueHistory
│
├── AssetRegistry
│   ├── AssetFilters
│   ├── AssetTable
│   └── AssetStatusBadge
│
├── AssetDetail
│   ├── AssetHeader
│   ├── LifecycleTimeline
│   ├── OwnershipChain
│   ├── ImpactMeasurements
│   ├── ValuationHistory
│   └── TransactionHistory
│
└── VerificationInterface
    ├── EvidenceViewer
    ├── RawDataPanel
    ├── ComputedImpactPanel
    ├── VerificationSummary
    └── VerificationActions
```

---

# 23. Shared UI Primitives

Recommended reusable components:

```text id="7gdoaq"
ImpactValueCard
AssetTypeBadge
AssetStatusBadge
VerificationBadge
OwnershipNode
LifecycleStep
ValuationMetric
EvidenceQualityBadge
DataFreshnessChip
ApprovalButton
RejectionDialog
TransactionReference
ConfidenceIndicator
CurrencyValue
QuantityMetric
```

---

# 24. Data Model

## Impact Asset

```ts id="p4kz0b"
interface ImpactAsset {
  id: string;

  type:
    | "carbon"
    | "biodiversity"
    | "water";

  quantity: number;
  unit: string;

  ownerId: string;

  status:
    | "draft"
    | "created"
    | "pending_verification"
    | "verified"
    | "listed"
    | "transferred"
    | "sold"
    | "retired"
    | "rejected"
    | "cancelled";

  currentValue?: number;
  currency?: string;

  createdAt: string;
  verifiedAt?: string;
  retiredAt?: string;

  projectId?: string;

  evidenceRefs: string[];
}
```

---

## Impact Measurement

```ts id="6btz9h"
interface ImpactMeasurement {
  id: string;

  assetId: string;

  metric: string;
  value: number;
  unit: string;

  methodology: string;
  methodologyVersion: string;

  measuredAt: string;

  sourceRefs: string[];
}
```

---

## Valuation

```ts id="3zj3gm"
interface ImpactValuation {
  id: string;

  assetId: string;

  quantity: number;
  unitPrice: number;

  currency: string;

  totalValue: number;

  pricingSource: string;
  methodology: string;

  valuedAt: string;

  confidence?: number;
}
```

---

## Ownership Event

```ts id="7j7yl8"
interface OwnershipEvent {
  id: string;

  assetId: string;

  fromOwnerId?: string;
  toOwnerId: string;

  quantity: number;

  transactionId?: string;

  timestamp: string;

  type:
    | "creation"
    | "transfer"
    | "sale"
    | "retirement";
}
```

---

## Verification Record

```ts id="9yy0h4"
interface VerificationRecord {
  id: string;

  assetId: string;

  verifierId: string;

  status:
    | "pending"
    | "approved"
    | "rejected"
    | "requires_more_evidence";

  claimedImpact: number;
  verifiedImpact?: number;

  evidenceCoverage: number;
  calculationReproducibility?: number;

  decisionReason?: string;

  createdAt: string;
  decidedAt?: string;
}
```

---

# 25. Valuation Architecture

Impact value should be derived from explicit components.

```text id="w93t3n"
Impact Quantity
       ×
Unit Price
       =
Gross Impact Value
```

For example:

```text id="o3hvpn"
125,000 tCO₂e
×
$42 / tCO₂e
=
$5,250,000
```

The UI should make each component independently inspectable.

Where applicable, additional valuation factors can be exposed:

* asset quality
* verification status
* methodology
* vintage
* market
* location
* pricing source
* liquidity
* discount / premium assumptions

---

# 26. Value vs Impact

The dashboard must clearly distinguish:

### Impact

The environmental or ecological quantity measured.

Example:

```text
125,000 tCO₂e
```

### Value

The monetary representation assigned to that quantity.

Example:

```text
$5.25M
```

These are related but not interchangeable.

The product should never imply that environmental value is fully captured by market price.

---

# 27. Ownership & Provenance

The Asset Registry should provide strong provenance.

A user should be able to answer:

> Where did this asset originate?

> Who verified it?

> Who owned it?

> Who transferred it?

> When was it sold?

> Has it been retired?

The ownership chain should be chronological and auditable.

---

# 28. Blockchain-Inspired UX

The interface may use blockchain-style visual language:

```text id="0a7jca"
┌─────────────┐
│ Asset Mint  │
└──────┬──────┘
       ↓
┌─────────────┐
│ Verification│
└──────┬──────┘
       ↓
┌─────────────┐
│ Owner A     │
└──────┬──────┘
       ↓
┌─────────────┐
│ Owner B     │
└──────┬──────┘
       ↓
┌─────────────┐
│ Retired     │
└─────────────┘
```

However, the UX should remain understandable to users who know nothing about blockchains.

---

# 29. Verification Integrity

The verification interface should minimize ambiguity.

A verifier should be able to determine:

```text id="0byxmz"
What was measured?
        ↓
How was it calculated?
        ↓
What assumptions were used?
        ↓
Can the calculation be reproduced?
        ↓
Does the evidence support the claim?
        ↓
Approve / Reject
```

Approval should create a durable verification event.

Rejection should preserve:

* reviewer
* timestamp
* reason
* evidence issue
* submitted impact
* verification state

---

# 30. Empty States

## No Assets

```text id="1i9r7o"
NO IMPACT ASSETS

No registered impact assets match
the current filters.

Try widening:
• date range
• asset type
• geography
```

## No Valuation

```text id="hcrl82"
VALUATION UNAVAILABLE

Impact has been verified, but no current
market valuation is available.

Measured impact:
42,000 units
```

The system must not fabricate monetary value when pricing data is unavailable.

---

# 31. Loading States

Loading states should identify what is happening:

```text id="bqgx5g"
Loading impact valuations

Loading asset registry

Resolving ownership history

Retrieving verification evidence

Calculating portfolio value
```

For large registries, use:

* skeleton rows
* progressive loading
* virtualized tables

---

# 32. Error States

Errors should be operationally meaningful.

Example:

```text id="9jh0jz"
VALUATION SOURCE UNAVAILABLE

Current market pricing could not be retrieved.

Last successful valuation:
14:32 EAT

Displayed values may be stale.
```

For verification:

```text id="rihx3f"
EVIDENCE SOURCE UNAVAILABLE

One referenced data source could not be loaded.

Verification cannot be completed
until the evidence is available.
```

---

# 33. Data Freshness

Important metrics should show update timestamps.

Examples:

```text id="h3s76h"
Impact measurement
Updated 2 hours ago

Market valuation
Updated 11 minutes ago

Ownership registry
Updated 43 seconds ago

Verification record
Updated 3 days ago
```

Stale valuation data must not look identical to live market data.

---

# 34. Access & Roles

Different dashboard functions may require different privileges.

Suggested roles:

### Viewer

Can inspect:

* impact
* asset details
* ownership
* verification status

### Asset Manager

Can:

* create assets
* manage metadata
* initiate verification

### Verifier

Can:

* inspect evidence
* approve
* reject
* request additional evidence

### Administrator

Can:

* manage registry
* configure methodologies
* manage roles
* review audit records

The frontend should clearly communicate restricted actions.

---

# 35. Auditability

Every meaningful registry action should leave an audit trail.

Track:

* asset creation
* verification
* ownership changes
* valuation changes
* transfers
* sales
* retirement
* revalidation
* rejection

Example:

```text id="td2jcs"
CAR-00128

09:14 — Created
10:03 — Submitted for verification
12:41 — Verified by Entity X
14:22 — Transferred to Entity Y
16:07 — Sold
```

---

# 36. Performance Strategy

The registry may eventually contain millions of assets.

Plan for:

* server-side pagination
* virtualized tables
* indexed filters
* cursor-based navigation
* cached asset details
* lazy-loaded lifecycle data
* background valuation refresh
* progressive ownership history loading

Never render an entire asset registry into the browser.

---

# 37. Accessibility

The interface must remain usable without color dependency.

Status should be communicated through:

* labels
* icons
* patterns
* semantic HTML
* accessible focus states

For example:

```text id="8wbhx1"
VERIFIED ✓

REQUIRES REVIEW ⚠

REJECTED ×
```

not simply colored badges.

---

# 38. Security Considerations

Impact assets can represent financial and environmental value.

Frontend flows should therefore assume:

* authenticated users
* role-based permissions
* signed verification actions
* immutable audit events
* protected ownership information
* secure transaction references

Destructive actions should require deliberate confirmation.

---

# 39. MVP

The first release should focus on the complete asset lifecycle.

### Impact Dashboard

* total impact value
* carbon / biodiversity / water breakdown
* value-over-time chart
* asset-type detail
* quantity × price valuation

### Asset Registry

* asset list
* filtering
* asset detail
* lifecycle timeline
* ownership chain
* verification status

### Verification

* raw-data view
* computed-impact view
* methodology
* evidence summary
* approve
* reject
* rejection reason

This creates a complete vertical slice:

```text id="8ygs5x"
Measure
→ Calculate
→ Verify
→ Register
→ Value
→ Transfer
```

---

# 40. Future Expansion

Potential V1+ features:

* portfolio analytics
* real-time market valuation
* geospatial impact maps
* retirement tracking
* impact certificates
* external registry synchronization
* institutional reporting
* project-level dashboards
* scenario valuation
* impact-quality scoring
* automated anomaly detection
* marketplace interfaces
* API integrations
* advanced provenance visualization

---

# 41. Example End-to-End Scenario

A project produces verified environmental impact.

```text id="a7w9c2"
Project Activity
      ↓
Impact Measurement
      ↓
125,000 tCO₂e
      ↓
Third-Party Verification
      ↓
APPROVED
      ↓
Asset Created
      ↓
125,000 Carbon Units
      ↓
Market Price
$42 / tonne
      ↓
Estimated Value
$5.25M
      ↓
Asset Transferred
      ↓
Asset Sold
      ↓
Retired
```

At every stage, the user can inspect the evidence and lifecycle state.

---

# 42. Success Criteria

The Impact Valuation Dashboard should allow users to answer:

### What impact exists?

Measured environmental quantities.

### What is it worth?

Transparent valuation methodology.

### Which assets represent it?

Registry and asset identifiers.

### Who owns those assets?

Current and historical ownership.

### Has the impact been verified?

Third-party verification state.

### Can we trace the lifecycle?

Complete event history.

### Can the calculation be audited?

Evidence and methodology lineage.

---

# 43. Final Product Philosophy

The environmental economy needs more than numbers.

It needs **traceability**.

A credible impact system should connect:

```text id="e0u4fw"
Impact
   ↓
Evidence
   ↓
Verification
   ↓
Asset
   ↓
Value
   ↓
Ownership
   ↓
Transaction
   ↓
Retirement
```

Atlas Sanctum's Impact Valuation Dashboards turn that lifecycle into an understandable interface.

---

# 44. Final Product Framing

### Primary

> **Atlas turns measurable environmental impact into verifiable, traceable, and valuation-ready assets.**

### Short

> **Measure impact. Verify it. Value it. Trace it.**

### Operational

> **From environmental evidence to auditable impact assets.**

### Core principle

> **No impact value without a traceable path from measurement to verification.**

---

# 45. North Star

A conventional environmental dashboard says:

> **"We created 125,000 tonnes of impact."**

Atlas should go further:

> **"Here is the measured impact, here is the methodology, here is the evidence, here is the independent verification, here is the asset representing it, here is what it is currently valued at, and here is the complete ownership history."**

That is the **Impact Valuation Dashboard Suite**.

Not just an ESG dashboard.

Not just an asset registry.

Not just a marketplace view.

A unified interface connecting **environmental impact, verification, valuation, provenance, and asset lifecycle**.
