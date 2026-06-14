# TWG Study Tracker

Initiative: Tokenization in Finance — Evidence & Implementation Pathways
Working group convening: 25 June 2026, Point Zero Forum, Zurich

---

## Study Priority

- **[PRIORITY — not yet studied]:** PS1 (Swift), PS7 (Coinbase/RWA)
- **[NEEDS DEEPER STUDY]:** PS2 (Institutional Settlement + Public Blockchain), PS5 (Stablecoin Recognition), PS6 (Agentic Governance)
- **[COMPLETE]:** PS3 (FMI), PS4 (Stablecoin Sandwich)

---

## Problem Statements — Study Progress

### Theme 1: Stablecoins & Agentic Payments

- [x] **PS4 — Stablecoin Sandwich Licensing** (Tang Wei / Stripe)
  - Architecture: Leg 1 (fiat→stablecoin, on-ramp) · Leg 2 (stablecoin transfer, the rail) · Leg 3 (stablecoin→fiat, off-ramp)
  - Triple-licence problem: Leg 1 = payments licence in Country A; Leg 2 = separate digital asset authorisation (or gap); Leg 3 = payments licence in Country B — three independent regulatory buckets, not designed to interlock
  - Supervisory paradox: requiring full licensing to get regulatory visibility prices out the operators actually serving EMDE corridors, pushing flows underground — the enforcement mechanism degrades its own coverage
  - Tether exposes the structural hole: issuer can grow to $140B+ by not doing the fiat legs — the licensed exchange operators in Legs 1 and 3 are supervised; the stablecoin issuer (BVI, no licence) floats above the perimeter entirely. Functional equivalence principle can't reach Tether because Tether is technically not performing a payment service — it's issuing an instrument.
  - Tether / MiCA: chose not to seek MiCA compliance; EU exchanges (Coinbase EU, Bitstamp) delisted USDT; USDT still flows via non-EU exchanges — enforcement is at the exchange layer, not the issuer layer, which is the weakness
  - Tether / GENIUS Act (US): foreign issuers must register if serving US customers; Tether argues it doesn't onboard US retail directly; unresolved
  - MAS BLOOM (Oct 2025, Borderless Liquid Open Online Multi-currency): three workstreams — (1) Distribution & Clearing [Circle, DBS, OCBC, Partior, Stripe, UOB] = Legs 1+3; (2) Programmable Compliance Controls [Ant International, StraitsX] = embed AML/sanctions logic in token/transaction so compliance travels with the payment; (3) Agentic Payments [Coinbase, DBS] = PS6 territory. Builds on Project Orchid + Project Guardian + GL1.
  - BLOOM solves: validates three-leg architecture with licensed institutions; programmable compliance reframes supervisory visibility from licensing → technical standards; implicitly defines "well-regulated" as MAS SCS-licensed (Circle/USDC, StraitsX/XSGD)
  - BLOOM doesn't solve: "well-regulated" has no portable cross-border definition; BLOOM is a trial framework not a regulatory instrument; receiving-jurisdiction (Leg 3) regulators outside Singapore get no recognition mechanism; USDT (70% of global stablecoin volume) excluded; programmable compliance as substitute for licensed intermediary has no legal basis yet in any jurisdiction
  - GDF Stablecoin Regulatory Playbook (Jan 2026, 10 areas): proportionality + functional equivalence framing is the right design principle — voluntary guidance only, cannot create the binding multilateral mechanism PS4 needs
  - PS4 and PS5 are sequential: PS4 = can you legally move a stablecoin out of Country A? PS5 = does the stablecoin have legal status when it arrives in Country B? You can solve PS4 and still have PS5 fail.

- [x] **PS5 — Cross-Jurisdictional Stablecoin Recognition** (Sunayna Tuteja) [NEEDS DEEPER STUDY]
  - Foreign stablecoins circulating as de facto monetary instruments in EMDEs, host regulators have no tools
  - Host regulator binary today: ban (Nigeria tried 2021, reversed 2023 because demand went underground) or tolerate (default — zero visibility). Neither is a regulatory framework.
  - What's needed: conditional recognition — host regulator recognises foreign stablecoin as permitted settlement instrument IF: (a) issuer meets minimum reserve/attestation/redemption standards; (b) supervisory cooperation channel exists between home and host regulator; (c) issuer agrees to local reporting obligations. Equivalent to "equivalence" decisions in securities law (MiFID II model) but no such framework exists for stablecoins.
  - FSB Recs 7 & 8: call for bilateral/multilateral arrangements — only 9/29 jurisdictions have stablecoin legislation; recs largely unimplemented; FSB enforcement = peer review + G20 reporting + reputational pressure only, no hard mechanism
  - GENIUS Act dependency: if US enacts GENIUS, it creates a home-country standard that bilateral equivalence arrangements could be built on top of ("GENIUS-compliant issuers recognised in [jurisdiction] subject to reporting") — but this requires GENIUS enactment AND other jurisdictions choosing to build on US law, neither guaranteed
  - PS5 urgency is tied to PS6: as agentic payments scale, AI agents default to stablecoins for structural reasons (24/7, programmable, cheap) — volume of unrecognised foreign stablecoins in EMDE jurisdictions will explode faster than PS5 can be resolved
  - GDF Playbook areas 9–10 (cross-border recognition + reciprocity): voluntary guidance only
  - DEEPER STUDY NEEDED: specific existing bilateral/multilateral arrangements to review; Tuteja's Fed experience and what it brings; interaction with GENIUS Act timeline

- [x] **PS6 — Programmable & Agentic Payment Governance** (Amira Karim / Amazon) [NEEDS DEEPER STUDY]
  - Core: AI agents making financial decisions autonomously using stablecoins and tokenised assets — the governance framework doesn't exist
  - Three legal gaps: (1) delegation mandates not legally recognised — API key / smart contract authorisation is not a legally valid power of attorney in most jurisdictions; (2) agent authentication undefined — no standard for "this agent is authorised by a licensed entity to make payments up to $X for purpose Y"; (3) liability unallocated — if agent makes an erroneous payment, the liability chain (principal / AI provider / payment institution / receiving institution) is unlegislated anywhere
  - Oracle dependency connects to PS3: agentic payments often trigger on oracle feeds (pay when GPS confirms delivery) — if oracle is wrong, payment goes out incorrectly; PS3's open question on oracle liability is a direct upstream dependency for PS6's liability allocation problem
  - BLOOM Workstream 3 (Coinbase + DBS, agentic payments) is building the trial infrastructure PS6 needs to govern
  - EMDE angles: delegation as inclusion tool (trusted intermediary authorised to transact on behalf of individuals who can't operate wallets); trust substitution (reputable agent enables transactions in low-trust environments); regulatory vacuum risk (EMDE regulators watching agentic payments emerge with no framework — risk of ad hoc rules fragmenting the market)
  - ECB evidence: Digital Euro Prototyping with Amazon (2022-23) tested conditional payments (pay on delivery confirmation); ECB Pioneer Partnership (2024) extended to more complex programmable scenarios — both early-stage, controlled environment only
  - Amazon is lead organisation (Amira Karim + Arena Fernandez); tier: PD (Policy Discussion — requires policy intervention before commercial deployment)
  - DEEPER STUDY NEEDED: Arena Fernandez's specific angle; Amazon's CBDC governance submission content; what "delegation mandates" look like in practice across different legal systems

---

### Theme 2: Tokenised Bank Money & Institutional Settlement

- [ ] **PS1 — Bridging Financial Standards and DLT-Native Protocols** (Swift — Shriyanka Hore, Pallavi Thakur, Charifa El Otmani) [PRIORITY — NOT YET STUDIED]
  - Core gap: No harmonised standards bridge traditional financial messaging (ISO 20022) with blockchain-native token protocols (ERC-20, ERC-3643) — fragmented platforms, inconsistent asset representations, duplicated compliance processes, high integration costs across institutions and jurisdictions
  - Tier: Coordination-contingent — no single institution can bridge TradFi and DLT standards alone; requires coordinated action across regulators, standard-setting bodies (ISO, Swift, blockchain protocol groups), market infrastructure providers, and industry participants
  - Evidence: Swift Digital Assets Standards prototype, Sibos 2025 — modular framework extending ISO 20022 to support multi-blockchain asset issuance across ERC-20 and ERC-3643; demonstrates the bridge is technically achievable but requires coordinated adoption
  - EMDE angle: EMDEs simultaneously modernising legacy infrastructure and exploring DLT face the full fragmentation cost twice; a common cross-domain standard would lower integration barriers, accelerate digital market development, and improve access to global financial networks
  - Implementation experience: ERC-20 standardised within-chain fungible tokens; ERC-3643 added regulated-asset features — neither bridges to ISO 20022. Breakdown at the interoperability layer: no globally recognised cross-domain standard limits scalable adoption across market infrastructure and multiple blockchain networks
  - GL1 (MAS) = latent alternative approach: convergence on one shared ledger rather than cross-ledger standards — PS1 must engage this architecture choice
  - Key ledger landscape: Partior, JPM Kinexys, Corda, Fabric, Fnality (permissioned); mBridge, Agorá (central bank hybrid); Ethereum, Solana (public); RLN, GL1 (utility/shared)

- [x] **PS2 — Institutional Tokenised Settlement and Public-Blockchain Compliance** (Toh Wee Kee / JPMorgan Kinexys) [NEEDS DEEPER STUDY]
  - Scope: two linked problems — how regulated institutions participate in tokenised settlement infrastructure (including on public networks), AND the compliance framework for doing so on public blockchains. JPMC/Kinexys brings both the operational settlement evidence ($3T cumulative on Kinexys Digital Payments) and the MIT DCI joint paper on public blockchain compliance.
  - Tier: PD (public blockchain compliance) + CC (institutional settlement) — hybrid
  - **Institutional tokenised settlement dimension:** Regulated banks need operational, legal, and regulatory frameworks for participating in DLT-based settlement — covering both permissioned (Kinexys, Partior, Corda) and public networks. The gap: existing settlement frameworks assume CSD/CCP intermediation; DLT-native settlement redistributes these roles with no clear regulatory mapping.
  - **Public blockchain compliance dimension — four issues:** front-running/MEV · censorship/omission · unsolicited tokens · gas fees to sanctioned entities
  - Source: JPMorgan/MIT DCI paper; 6-layer solution framework. GBBC Risk Mitigation Framework (July 2025, with Oliver Wyman, DTCC, Euroclear, Clearstream, World Bank) tackles same four issues from industry side — now in discussion with Basel Committee and 100+ regulatory authorities
  - Gap: practical regulatory guidelines still don't exist; EMDE institutions locked out by compliance cost
  - **EMDE/Malaysia angle (13 Jun 2026):** Malaysia's stake = tokenised sukuk (~60% global supply) on public blockchain rails requires Malaysian banks to be full institutional participants — PS2 compliance gaps are the specific blocker. Also: Islamic finance hub ambition, cross-border payment corridors (Project Nexus), ASEAN first-mover opportunity on public blockchain compliance guidance for Islamic finance
  - **Sukuk primer:** Shariah-compliant bond equivalent — represents ownership in an underlying asset (not a debt claim), so returns = asset performance (rent, profit share), not interest. SPV holds real asset; sukuk certificates = proportional ownership. Common structures: Ijara (lease), Murabaha (cost-plus), Musharaka (partnership). Tokenisation is structurally clean for sukuk — real asset, clear ownership, periodic cash flows
  - **Toh Wee Kee reframe:** Don't ask "can regulated institutions use public blockchains?" — ask "what institutional design makes compliant participation possible?" Shifts working group from verdict to design problem. The four issues are design requirements, not fundamental incompatibilities: MEV → market microstructure (private mempools); censorship → regulatory safe harbor; unsolicited tokens → clear BNM/MAS guidance; gas fees → de minimis thresholds + tracing standards. WG output should be a design requirements framework, not a yes/no verdict on public blockchains
  - DEEPER STUDY NEEDED: how Kinexys's permissioned settlement experience informs the public blockchain compliance design; the 6-layer MIT DCI solution framework in detail; interaction between PS2 and PS1 (standards bridge as prerequisite for compliant public chain participation)

- [x] **PS3 — FMI Regulation Recalibration** (Dr. Mark Staples / DFCRC)
  - FMI rules calibrated for sequential/centralised settlement; tokenisation redistributes risks
  - New risks: smart contract defects, oracle dependencies, platform heterogeneity, key management
  - Key evidence: eAUD pilot, Project Acacia, BoE DLT Innovation Challenge (May 2026)
  - Remaining gaps: settlement finality protections for smart-contract settlement, Basel capital treatment under-specified, no single DLT model delivers deterministic finality without trade-offs
  - IOSCO Nov 2025 report diagnoses same structural problems — monitoring mode only, no implementation output

---

### Theme 3: Tokenised Real-World Assets

- [ ] **PS7 — Tokenised Real-World Assets** (Scott Bauguess / Coinbase) [PRIORITY — PENDING COINBASE SUBMISSION]
  - Status: placeholder — Coinbase submission outstanding; confirmed as Theme 3 lead in internal mapping
  - Scope: all tokenised RWA (equities, bonds, real estate, commodities, private credit) — crosses WG1 (infrastructure/settlement) and WG2 (regulation/trust)
  - **Bauguess angle — competition as forcing function:** As US enables tokenised equity markets (SEC/CFTC shift post-2024), US markets become more attractive to global issuers. Other jurisdictions face: (1) build domestic tokenised capital markets infrastructure to compete; (2) create equivalence frameworks for US-tokenised assets to adapt; (3) lose issuers and investors to US markets. Urgency argument — not theoretical.
  - **Bermuda proof of concept:** Coinbase International Exchange (BMA-licensed under DABA) is the operating evidence base. BMA's risk-tiered Digital Asset Business Act = replicable model for jurisdictions wanting to host compliant tokenised capital markets activity. Coinbase working paper with SEC/CFTC (confirm acronym) on DeFi-native capital markets — technical problem is solved; governance framework is the bottleneck.
  - **DeFi-native trading and social governance:** When tokenised assets trade on DEX protocols governed by DAOs, the governing body of the market is a smart contract + token vote — not a licensed exchange operator. No financial regulator anywhere recognises DAO governance as a legally valid market governance mechanism. Sub-problems: AML/KYC in permissionless pools; MEV in tokenised securities (securities law implications); settlement finality without CCP; regulated entity when market operator is a protocol.
  - **EMDE framing (critical for GFTN fit):** DeFi-native distribution reduces minimum investment thresholds from $100,000 to $10 — making equity and bond exposure in global companies accessible to EMDE retail investors. Same infrastructure enabling US institutional tokenised equities enables fractional ownership for EMDE populations. Secondary angle: EMDE jurisdictions adopting Bermuda-model frameworks can position as regional tokenised capital markets hubs.
  - **Dependency links:** sits above PS1 (standards bridge), PS2 (public chain compliance — MEV acute for tokenised securities), PS3 (DVP finality without CCP), PS4/PS5 (stablecoin payment leg of every RWA transaction), PS6 (agentic portfolio management of tokenised assets)
  - **Open question:** Confirm whether Coinbase working paper is with CFTC or SEC

---

## External Landscape — Study Progress

- [x] **Project Agorá** (BIS/IIF)
  - Phase 1: May 2026 exploratory phase report published
  - Two-layer architecture: unifying ledger (commercial bank deposits) + jurisdictional ledgers (central bank reserves)
  - Validates synchronisation operator pattern over direct interoperability
  - Phase 1 achieved: atomic settlement confirmed, finality legally achievable across 7 jurisdictions, privacy protections, 9 friction points addressed
  - Phase 2 (announced 27 May 2026): BIS confirmed Agorá advances to real-value testing; Bank of Canada joining as new participant
  - Remaining gaps: AML/sanctions compliance features need regulatory frameworks, data sharing frameworks unresolved, unifying ledger governance undefined, no EMDE participants
  - Distinction from mBridge: Agorá keeps CB money on sovereign ledgers; mBridge puts CBDC on shared ledger

- [x] **mBridge** (BIS/HKMA/PBoC/BoT/UAE/SAMA)
  - BIS withdrew late 2024 — official: "reached maturity"; real: sanctions evasion concerns, PBoC architecture influence, non-Western alignment
  - Remaining participants continuing independently — now explicitly non-Western alternative rails

- [x] **Swift Digital Assets Standards** — Sibos 2025 prototype
  - ISO 20022 ↔ ERC-20/ERC-3643 bridge; addresses PS1 standards layer directly; Swift is PS1 lead

- [x] **GL1 (Global Layer One)** — MAS + DBS, JPMorgan, HSBC, StanChart
  - Shared utility-grade permissioned blockchain for tokenized assets broadly
  - Implicit answer to PS1: convergence on one ledger vs. cross-ledger interoperability standards

- [x] **RLN (Regulated Liability Network)**
  - Consortium utility (Citi, HSBC, BNY, Wells Fargo, Mastercard, Swift + others)
  - US PoC 2022–23 (NY Fed Innovation Center); UK PoC 2023 (UK Finance + BoE observer)
  - Remains at PoC stage — no production entity, no formal operator constituted

- [x] **IOSCO** — Nov 2025 Final Report on Tokenisation
  - Diagnoses PS1 and PS3 problems; "same activities, same risks, same regulatory outcomes" stance
  - Monitoring mode for 2026 — no new working group outputs

- [x] **FSB** — Oct 2025 Thematic Review
  - Only 9/29 jurisdictions with stablecoin legislation; Recs 7 & 8 unimplemented
  - 2026 priority: stablecoins; still no hard enforcement mechanism

- [x] **GBBC** (Global Blockchain Business Council) — GFTN WG2 participant
  - GBBC Risk Mitigation Framework (July 2025, with Oliver Wyman, DTCC, Euroclear, Clearstream, World Bank): non-financial risks of public blockchain infrastructure; now in discussion with the Basel Committee and 100+ regulatory authorities; maps to PS2 and PS3
  - GSMI tokenization report: custody, settlement, secondary markets landscape mapping
  - Sandra Ro (GBBC) confirmed WG2 participant

- [ ] **GDF** (Global Digital Finance) — referenced as evidence only; not a GFTN WG member
  - GDF Global Stablecoin Regulatory Playbook (Jan 2026, 10 areas): proportionality + functional equivalence framing — voluntary guidance only; referenced as evidence base for PS4 and PS5
  - Note: GDF and GBBC are separate entities; GDF work is drawn on as evidence in the implementation guide but GDF is not a participating organisation

- [x] **Simon Taylor / Fintech Brainfood — 24x7 Money Loop**
  - Tokenized deposits (rests) + stablecoins (moves) = always-on cross-border settlement
  - SoFi: first US national bank to issue stablecoin (Ethereum + Solana, reserves at Fed 1:1) — straddles multiple ledgers in production
  - Coastal Community Bank: replacing correspondent banking with stablecoins now
  - JPM Kinexys: $3T cumulative since 2020 — works at scale but closed ecosystem only
  - Demand side moving faster than the PS1 supply-side standards it depends on

- [ ] **Partior** (DBS/JPMorgan/Temasek)
- [ ] **EU DLT Pilot Regime** — mentioned in Theme 3 (tokenized securities)
- [ ] **IMF April 2026 Tokenized Finance Note**
- [ ] **Coinbase / Bermuda BMA DABA framework** — evidence base for PS7

---

## Cross-Cutting Themes to Revisit

- [ ] Full dependency stack: PS1 (standards) → PS2 (institutional compliance) → PS3 (FMI finality) → PS4 (licensing) → PS5 (recognition) → PS6 (agentic governance) → PS7 (RWA capital markets)
- [ ] Why none of the existing frameworks address EMDE contexts specifically — the GFTN differentiator
- [ ] Agentic payments (PS6) as a forcing function for all other PS urgency
- [ ] Synchronisation operator pattern — how it appears in Agorá, Project Acacia, and PS1 architecture debate
- [ ] Competition dynamics (PS7/Bauguess): US innovation as forcing function vs. GFTN's harmonisation mandate — how to frame
