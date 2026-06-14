# TWG Study Tracker

Initiative: Tokenization in Finance — Evidence & Implementation Pathways
Working group convening: 25 June 2026, Point Zero Forum, Zurich

---

## Problem Statements — Study Progress

### Theme 1: Tokenized Bank Money & Institutional Settlement

- [x] **PS1 — Cross-Ledger Settlement & Interoperability Standards** (Kelvin Li)
  - Core gap: No multilateral standard for tokenized deposits to settle across different ledger stacks
  - Three-layer gap: data/metadata standards · settlement finality rules · regulatory recognition
  - Architecture debate: synchronisation operators vs. direct platform interoperability
  - Agorá (May 2026) validates synchronisation operator approach and confirms atomic settlement across 7 jurisdictions — but no production timeline, no EMDE coverage, governance of unifying ledger unresolved
  - Swift submission (June 2026): ISO 20022 ↔ ERC-20/ERC-3643 bridge prototype shown at Sibos 2025 — addresses data standards layer; doesn't touch finality or regulatory recognition
  - GL1 (MAS) = latent fourth option: convergence on one shared ledger rather than cross-ledger standards
  - Key ledger landscape: AntChain, Partior, JPM Kinexys, Corda, Fabric, Fnality (permissioned); mBridge, Agorá (central bank hybrid); Ethereum, Solana (public); RLN, GL1 (utility/shared)

- [x] **PS2 — Public Blockchain Compliance** (Toh Wee Kee)
  - Four issues: front-running · censorship/omission · unsolicited tokens · gas fees to sanctioned entities
  - Source: JPMorgan/MIT DCI paper; 6-layer solution framework
  - GBBC Risk Mitigation Framework (July 2025, with Oliver Wyman, DTCC, Euroclear, Clearstream, World Bank) tackles the same four issues from industry side — not regulatory guidance, but endorsed by Swift's CIO
  - Gap: practical regulatory guidelines still don't exist; EMDE institutions locked out by compliance cost
  - **EMDE/Malaysia angle (13 Jun 2026):** Malaysia's stake = tokenised sukuk (~60% global supply) on public blockchain rails requires Malaysian banks to be full institutional participants — PS2 compliance gaps are the specific blocker. Also: Islamic finance hub ambition, cross-border payment corridors (Project Nexus), ASEAN first-mover opportunity on public blockchain compliance guidance for Islamic finance
  - **Sukuk primer:** Shariah-compliant bond equivalent — represents ownership in an underlying asset (not a debt claim), so returns = asset performance (rent, profit share), not interest. SPV holds real asset; sukuk certificates = proportional ownership. Common structures: Ijara (lease), Murabaha (cost-plus), Musharaka (partnership). Tokenisation is structurally clean for sukuk — real asset, clear ownership, periodic cash flows
  - **Toh Wee Kee reframe:** Don't ask "can regulated institutions use public blockchains?" — ask "what institutional design makes compliant participation possible?" Shifts working group from verdict to design problem. The four issues are design requirements, not fundamental incompatibilities: MEV → market microstructure (private mempools); censorship → regulatory safe harbor; unsolicited tokens → clear BNM/MAS guidance; gas fees → de minimis thresholds + tracing standards. WG output should be a design requirements framework, not a yes/no verdict on public blockchains

- [x] **PS3 — FMI Regulation Recalibration** (Dr. Mark Staples)
  - FMI rules calibrated for sequential/centralised settlement; tokenisation redistributes risks
  - New risks: smart contract defects, oracle dependencies, platform heterogeneity, key management
  - Key evidence: eAUD pilot, Project Acacia, BoE DLT Innovation Challenge (May 2026)
  - Remaining gaps: settlement finality protections for smart-contract settlement, Basel capital treatment under-specified, no single DLT model delivers deterministic finality without trade-offs
  - IOSCO Nov 2025 report diagnoses same structural problems — monitoring mode only, no implementation output

### Theme 2: Stablecoins & Agentic Payments

- [x] **PS4 — Stablecoin Sandwich Licensing** (Tang Wei)
  - Architecture: Leg 1 (fiat→stablecoin, on-ramp) · Leg 2 (stablecoin transfer, the rail) · Leg 3 (stablecoin→fiat, off-ramp)
  - Triple-licence problem: Leg 1 = payments licence in Country A; Leg 2 = separate digital asset authorisation (or gap); Leg 3 = payments licence in Country B — three independent regulatory buckets, not designed to interlock
  - Supervisory paradox: requiring full licensing to get regulatory visibility prices out the operators actually serving EMDE corridors, pushing flows underground — the enforcement mechanism degrades its own coverage
  - Tether exposes the structural hole: issuer can grow to $140B+ by not doing the fiat legs — the licensed exchange operators in Legs 1 and 3 are supervised; the stablecoin issuer (BVI, no licence) floats above the perimeter entirely. Functional equivalence principle can't reach Tether because Tether is technically not performing a payment service — it's issuing an instrument.
  - Tether / MiCA: chose not to seek MiCA compliance; EU exchanges (Coinbase EU, Bitstamp) delisted USDT; USDT still flows via non-EU exchanges — enforcement is at the exchange layer, not the issuer layer, which is the weakness
  - Tether / GENIUS Act (US): foreign issuers must register if serving US customers; Tether argues it doesn't onboard US retail directly; unresolved
  - MAS BLOOM (Oct 2025, Borderless Liquid Open Online Multi-currency): three workstreams — (1) Distribution & Clearing [Circle, DBS, OCBC, Partior, Stripe, UOB] = Legs 1+3; (2) Programmable Compliance Controls [Ant International, StraitsX] = embed AML/sanctions logic in token/transaction so compliance travels with the payment; (3) Agentic Payments [Coinbase, DBS] = PS6 territory. Builds on Project Orchid + Project Guardian + GL1.
  - BLOOM solves: validates three-leg architecture with licensed institutions; programmable compliance reframes supervisory visibility from licensing → technical standards; implicitly defines "well-regulated" as MAS SCS-licensed (Circle/USDC, StraitsX/XSGD)
  - BLOOM doesn't solve: "well-regulated" has no portable cross-border definition; BLOOM is a trial framework not a regulatory instrument; receiving-jurisdiction (Leg 3) regulators outside Singapore get no recognition mechanism; USDT (70% of global stablecoin volume) excluded; programmable compliance as substitute for licensed intermediary has no legal basis yet in any jurisdiction
  - GDF/GBBC Stablecoin Regulatory Playbook (Jan 2026, 10 areas): proportionality + functional equivalence framing is the right design principle — voluntary guidance only, cannot create the binding multilateral mechanism PS4 needs
  - PS4 and PS5 are sequential: PS4 = can you legally move a stablecoin out of Country A? PS5 = does the stablecoin have legal status when it arrives in Country B? You can solve PS4 and still have PS5 fail.

- [x] **PS5 — Cross-Jurisdictional Stablecoin Recognition** (Sunayna Tuteja)
  - Foreign stablecoins circulating as de facto monetary instruments in EMDEs, host regulators have no tools
  - Host regulator binary today: ban (Nigeria tried 2021, reversed 2023 because demand went underground) or tolerate (default — zero visibility). Neither is a regulatory framework.
  - What's needed: conditional recognition — host regulator recognises foreign stablecoin as permitted settlement instrument IF: (a) issuer meets minimum reserve/attestation/redemption standards; (b) supervisory cooperation channel exists between home and host regulator; (c) issuer agrees to local reporting obligations. Equivalent to "equivalence" decisions in securities law (MiFID II model) but no such framework exists for stablecoins.
  - FSB Recs 7 & 8: call for bilateral/multilateral arrangements — only 9/29 jurisdictions have stablecoin legislation; recs largely unimplemented; FSB enforcement = peer review + G20 reporting + reputational pressure only, no hard mechanism
  - GENIUS Act dependency: if US enacts GENIUS, it creates a home-country standard that bilateral equivalence arrangements could be built on top of ("GENIUS-compliant issuers recognised in [jurisdiction] subject to reporting") — but this requires GENIUS enactment AND other jurisdictions choosing to build on US law, neither guaranteed
  - PS5 urgency is tied to PS6: as agentic payments scale, AI agents default to stablecoins for structural reasons (24/7, programmable, cheap) — volume of unrecognised foreign stablecoins in EMDE jurisdictions will explode faster than PS5 can be resolved
  - GDF/GBBC Playbook areas 9–10 (cross-border recognition + reciprocity): voluntary guidance only

- [x] **PS6 — Programmable & Agentic Payment Governance** (Amira Karim)
  - Core: AI agents making financial decisions autonomously using stablecoins and tokenised assets — the governance framework doesn't exist
  - Three legal gaps: (1) delegation mandates not legally recognised — API key / smart contract authorisation is not a legally valid power of attorney in most jurisdictions; (2) agent authentication undefined — no standard for "this agent is authorised by a licensed entity to make payments up to $X for purpose Y"; (3) liability unallocated — if agent makes an erroneous payment, the liability chain (principal / AI provider / payment institution / receiving institution) is unlegislated anywhere
  - Oracle dependency connects to PS3: agentic payments often trigger on oracle feeds (pay when GPS confirms delivery) — if oracle is wrong, payment goes out incorrectly; PS3's open question on oracle liability is a direct upstream dependency for PS6's liability allocation problem
  - BLOOM Workstream 3 (Coinbase + DBS, agentic payments) is building the trial infrastructure PS6 needs to govern
  - EMDE angles: delegation as inclusion tool (trusted intermediary authorised to transact on behalf of individuals who can't operate wallets); trust substitution (reputable agent enables transactions in low-trust environments); regulatory vacuum risk (EMDE regulators watching agentic payments emerge with no framework — risk of ad hoc rules fragmenting the market)
  - ECB evidence: Digital Euro Prototyping with Amazon (2022-23) tested conditional payments (pay on delivery confirmation); ECB Pioneer Partnership (2024) extended to more complex programmable scenarios — both early-stage, controlled environment only

- [ ] **PS7 — DeFi-Native Equity Market Structure & Tokenised Capital Markets Governance** (Scott Bauguess, Coinbase) [PROPOSED — not yet formally adopted]
  - **Problem title:** Tokenised Equity Markets on DeFi Infrastructure: Market Structure, Social Governance, and the Competition Imperative
  - **Core gap:** No jurisdiction has a regulatory framework that enables compliant, institutionally-accessible tokenised equity markets on DeFi trading infrastructure. Traditional market structure regulation (exchange licences, broker-dealer obligations, CCP clearing, CSD settlement) was designed for centralised intermediaries — it does not map onto AMM liquidity pools, DEX protocols, or DAO-governed market infrastructure. The result: DeFi-native capital markets activity is either driven offshore, operates in grey zones, or doesn't happen at all — while the underlying technical infrastructure is mature enough for institutional use.
  - **The competition forcing function (Bauguess angle):** As the US enables tokenised equity markets domestically (SEC and CFTC shift post-2024; Coinbase working paper with SEC/CFTC — confirm acronym), US markets become more attractive to global issuers. Other jurisdictions face a three-way choice: (1) build domestic tokenised equity market infrastructure to compete; (2) create equivalence frameworks for US-tokenised equities to adapt; (3) lose issuers, investors, and price discovery to US markets. This is the urgency argument — not a theoretical future problem.
  - **Bermuda proof of concept:** Coinbase International Exchange (BMA-licensed under DABA) is the operating evidence base. BMA's risk-tiered Digital Asset Business Act = replicable model for jurisdictions wanting to host compliant tokenised capital markets activity without starting from scratch. The PS7 output should reference Bermuda as a worked example.
  - **DeFi-native trading governance:** When tokenised equities trade on DEX protocols governed by DAOs (token holders vote on protocol parameters, fees, upgrades), the governing body of the market is a smart contract + token vote — not a licensed exchange operator. No financial regulator anywhere recognises DAO governance as a legally valid market governance mechanism. Key sub-problems: AML/KYC in permissionless liquidity pools; MEV/front-running in tokenised securities (securities law implications, not just market quality); settlement finality without CCP clearing; who is the regulated entity when the market operator is a protocol.
  - **Social governance:** On-chain, participatory governance of financial market infrastructure. The novel question: what standards apply to DAO governance when the DAO operates capital markets infrastructure? This potentially democratises financial governance — but creates regulatory vacuum if unaddressed.
  - **EMDE framing (critical for GFTN fit):** The competition dynamics argument is an advanced-economy concern; the EMDE angle is the inclusion promise. Tokenised equity markets with fractional ownership + DeFi-native distribution can reduce minimum investment thresholds from $100,000 to $10, making equity stakes in global companies accessible to EMDE retail investors for the first time. The same DeFi infrastructure enabling US institutional tokenised equities also enables an Indonesian smallholder to hold fractional Apple or Unilever stock. PS7 must make this argument explicitly or it reads as a developed-market problem wearing GFTN clothing. Secondary EMDE angle: EMDE jurisdictions adopting Bermuda-model frameworks can position as regional tokenised capital markets hubs rather than losing activity to US/EU.
  - **Dependency links:** sits above PS1 (rails), PS2 (public chain compliance — MEV is acute for tokenised securities), PS3 (DVP finality without CCP), PS4/PS5 (stablecoin payment leg of every equity trade), PS6 (algorithmic/agentic trading on DEXs) + RWA layer (securities regulation for tokenised equities, investor accreditation rules)
  - **Expected output:** A framework for DeFi-native capital markets governance covering: (1) conditions under which a DEX protocol qualifies as a regulated market operator; (2) standards for DAO governance of financial market infrastructure; (3) model jurisdiction framework (BMA/DABA as template); (4) EMDE fractional ownership access mechanism
  - **Open question:** Confirm whether Coinbase working paper is with CFTC or SEC — affects which regulatory body's jurisdiction the US-side framing sits in

---

## External Landscape — Study Progress

- [x] **Project Agorá** (BIS/IIF) — May 2026 exploratory phase report
  - Two-layer architecture: unifying ledger (commercial bank deposits) + jurisdictional ledgers (central bank reserves)
  - Validates synchronisation operator pattern over direct interoperability
  - Achieved: atomic settlement confirmed, finality legally achievable across 7 jurisdictions, privacy protections, 9 friction points addressed
  - Gaps: no real-value testing yet, AML/sanctions compliance features need regulatory frameworks, data sharing frameworks unresolved, unifying ledger governance undefined, no EMDE participants
  - Distinction from mBridge: Agorá keeps CB money on sovereign ledgers; mBridge puts CBDC on shared ledger

- [x] **mBridge** (BIS/HKMA/PBoC/BoT/UAE/SAMA)
  - BIS withdrew late 2024 — official: "reached maturity"; real: sanctions evasion concerns, PBoC architecture influence, non-Western alignment
  - Remaining participants continuing independently — now explicitly non-Western alternative rails

- [x] **Swift Digital Assets Standards** — Sibos 2025 prototype
  - ISO 20022 ↔ ERC-20/ERC-3643 bridge; addresses PS1 data standards layer

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

- [x] **GBBC + GDF** (merged May 2022 — now one organisation)
  - GBBC Risk Mitigation Framework (July 2025): non-financial risks of public blockchains → maps to PS2
  - GDF Global Stablecoin Regulatory Playbook (Jan 2026): 10 areas → maps to PS4 + PS5
  - GSMI tokenization report: custody, settlement, secondary markets landscape mapping
  - GBBC + GDF are both named GFTN WG participants

- [x] **Simon Taylor / Fintech Brainfood — 24x7 Money Loop**
  - Tokenized deposits (rests) + stablecoins (moves) = always-on cross-border settlement
  - SoFi: first US national bank to issue stablecoin (Ethereum + Solana, reserves at Fed 1:1) — straddles multiple ledgers in production
  - Coastal Community Bank: replacing correspondent banking with stablecoins now
  - JPM Kinexys: $3T cumulative since 2020 — works at scale but closed ecosystem only
  - Demand side moving faster than the PS1 supply-side standards it depends on

- [ ] **Partior** (DBS/JPMorgan/Temasek)
- [ ] **EU DLT Pilot Regime** — mentioned in Theme 3 (tokenized securities)
- [ ] **IMF April 2026 Tokenized Finance Note**
- [ ] **Theme 3 — Tokenized RWA problem statements** (not in main deck)

---

## Cross-Cutting Themes to Revisit

- [ ] PS1 + PS4/PS5 dependency chain: standards → licensing → recognition (no layer works without the one below)
- [ ] Why none of the existing frameworks address EMDE contexts specifically — the GFTN differentiator
- [ ] Agentic payments (PS6) as a forcing function for all other PS urgency
- [ ] Synchronisation operator pattern — how it appears in Agorá, Project Acacia, and PS1 architecture debate
