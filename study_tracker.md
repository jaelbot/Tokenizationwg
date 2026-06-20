# TWG Study Tracker — Summary

## Current Status

The TWG Study Tracker documents progress on seven problem statements (PS1–PS7) addressing tokenization in finance, with a working group convening scheduled for 25 June 2026 in Zurich.

**Priority Areas:**
- **Not yet studied:** PS1 (Swift standards bridge)
- **Needs deeper study:** PS2 (institutional settlement on public blockchains), PS5 (stablecoin cross-border recognition), PS6 (agentic payment governance)
- **Complete:** PS3 (FMI recalibration) and PS4 (stablecoin licensing architecture)
- **Updated (19 Jun 2026):** PS7 — reframed by Coinbase from DeFi governance to interoperability conditions for inclusive, cross-border asset access

## Key Findings

**PS4 highlights a structural regulatory gap:** The "stablecoin sandwich" requires three separate licenses across different jurisdictions, but issuers like Tether operate outside this framework entirely. The document notes that "licensing requirements price out operators serving EMDE corridors," pushing activity underground rather than creating visibility.

**PS5 urgency is escalating:** As agentic payments scale, demand for foreign stablecoins in emerging markets will outpace regulatory resolution. The framework needed is "conditional recognition"—permitting foreign stablecoins only if issuers meet reserve standards and reporting obligations.

**PS2 reframes the question:** Rather than asking whether regulated institutions can use public blockchains, the working group should ask "what institutional design makes compliant participation possible?" This shifts analysis from binary verdict to design requirements.

**PS7 reframed (19 Jun 2026):** Coinbase (Chad Harper, Head of Coinbase Institute) has reframed the Theme 3 problem statement. The core concern is no longer DeFi governance but the access gap — the absence of an interoperability and compliance framework connecting operational but siloed tokenised capital markets infrastructure. Presenter changed from Scott Bauguess to Chad Harper. Working group assignment moved from WG2 to WG1.

## Problem Statement Detail

### PS7 — Interoperability Conditions for Inclusive, Cross-Border Asset Access
**Presenter:** Chad Harper, Head of Coinbase Institute  
**Working Group:** WG1 (Interoperability and Infrastructure) — updated from WG2  
**Layers:** L1 + L2 + L3a (Interoperability Standards + Regulatory Architecture Alignment + FMI Integration)  
**Classification:** Coordination-contingent  
**Status:** Updated 19 June 2026 (reframed from previous DeFi governance framing, 15 June 2026)

**Core problem:** The fixed costs of traditional capital markets intermediation — brokerage, custody, clearing, layered KYC — exclude retail and EMDE investors from global asset markets. Tokenisation can collapse these costs, but only if the underlying interoperability and compliance conditions exist. The tokenised RWA market has reached approximately $27 billion on-chain, and infrastructure is increasingly operational: DTCC is moving to production tokenisation of institutional securities (July 2026, SEC No-Action Letter), the FCA's PS26/7 fund tokenisation rules permit public DLT networks and remove intermediary layers, Bermuda's DABA provides a lightweight licensing model, and the Coinbase–Centrifuge partnership has launched the first compliant tokenised S&P 500 index fund (deSPXA). These are operational realities, not pilots. But each operates within its own infrastructure perimeter. No interoperability or compliance framework connects them, and no retail investor in an emerging market can currently purchase a tokenised equity with portable KYC, settle atomically, and trade on secondary markets across jurisdictions.

**Key unresolved questions:**
- Token standards for regulated equities: ERC-3643 exists but lacks globally recognised cross-platform interoperability framework
- Portable KYC: technically demonstrable but not yet regulatory-recognised across borders
- FMI integration: how tokenised equities connect to existing clearing and custody frameworks
- Market structure: how to enable low-cost access without recreating fixed-cost gatekeeping in new form

**EMDE dimension:**
- Direct inclusion: EMDE retail investors face the highest access barriers; tokenised equities with portable KYC and fractional ownership can collapse them
- Issuer access: EMDE issuers can reach global investor pools without listing on traditional international exchanges
- Infrastructure leapfrog: jurisdictions adopting lightweight licensing (Bermuda DABA model) can attract tokenised capital markets activity without building full domestic market infrastructure

**DeFi governance — downstream implication, not core barrier:** Once tokenised assets trade on permissionless secondary markets at scale, the question of who bears responsibility on DAO-governed protocols becomes acute (ECB research: top 100 holders control 80%+ of governance tokens across major protocols; ~one-third of top voters cannot be publicly identified). The MiCA dual consultations are exploring this. But this governance gap is a consequence of scaling access, not the barrier to building it. Sequencing: get the market structure and interoperability conditions right first; DeFi governance follows.

**Evidence anchors:**
- DTCC DTC Tokenisation Service (SEC No-Action Letter Dec 2025; production trades July 2026; 50+ firms in working group incl. BlackRock, JPMorgan, Goldman Sachs)
- FCA Fund Tokenisation Rules PS26/7 (April 2026; 132 eligible firms; direct-to-fund dealing model; stablecoin settlement open)
- Bermuda DABA (Class F/M/T tiers; BMA proposal to remove dual-licensing friction, March 2026)
- Coinbase–Centrifuge partnership (May 2026; deSPXA launched; $1.66B TVL on Centrifuge)
- Tokenised RWA market: $27B on-chain (RWA.xyz via CoinDesk, May 2026)
- IOSCO Tokenisation Report (November 2025; 13 member authorities; legal uncertainty persists for tokenised instruments)
- ECB Working Paper 3208 (March 2026; DeFi governance concentration data)

## Dependency Chain

All seven problem statements form an implementation stack, with standards harmonization (PS1) foundational to institutional compliance (PS2), FMI finality (PS3), licensing architecture (PS4), cross-border recognition (PS5), agentic governance (PS6), and RWA capital markets access (PS7). PS7 is now classified under WG1 and sits across Layers 1, 2, and 3a simultaneously — making it the clearest illustration of how the three layers must work in concert.
