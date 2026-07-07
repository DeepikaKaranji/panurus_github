# Panurus, an LF Decentralized Trust project.
<!--TODO: Add logo here> <-->
Panurus is an Apache 2.0 licensed, mature, production-grade framework for issuing, transferring, and managing tokens on permissioned blockchain networks. Active since 2021 with proven deployments in wholesale CBDC experiments (Banque de France DL3S, Bank of Canada Project Samara), the SDK provides comprehensive token infrastructure including fungible and non-fungible token support, multiple privacy levels (cleartext FabToken and privacy-preserving ZKAT-DLog with zero-knowledge proofs), and a complete service layer for transaction orchestration, identity management, auditing, and cross-chain atomic swaps. Its driver-based architecture enables network agnosticity across Hyperledger Fabric, FabricX, and other DLT platforms, allowing core application logic to remain portable while the SDK handles backend-specific integration. By standardizing token models and flows under vendor-neutral LFDT governance, the SDK reduces duplication across projects, strengthens security through collaborative review, and establishes a reusable tokenization layer for enterprise blockchain deployments handling real-world financial assets.

Panurus addresses three critical requirements fundamental to enterprise blockchain adoption: **Privacy** (protecting sensitive transaction data while enabling selective disclosure), **Performance** (achieving institutional-scale throughput without sacrificing decentralization), and **Compliance** (providing auditing and regulatory oversight capabilities).

## Architecture

Panurus is organized around a layered, modular architecture that separates token application logic from underlying blockchain infrastructure:

- **Application Services** — High-level APIs for issuing, transferring, redeeming, and auditing tokens across fungible and non-fungible asset types.
- **Token Transaction (TTX) Service** — Orchestrates end-to-end token transaction flows including UTXO selection, endorsement collection, and order/commit.
- **Identity & Wallet Layer** — Supports X.509, Idemix, multisig, and HTLC-based identities with wallet-based key management and configurable privacy levels.
- **Privacy Drivers** — Pluggable token drivers, including FabToken (cleartext transparency with X.509 identities) and ZKAT-DLog (Pedersen commitments and zero-knowledge proofs for owner anonymity, value confidentiality, and unlinkability).
- **Storage Layer** — SQL-backed state management (SQLite, PostgreSQL) with strategic UTxO caching to reduce redundant ledger queries.
- **Network Drivers** — A backend-agnostic driver layer that decouples token logic from the underlying DLT. Current implementations support Hyperledger Fabric and Hyperledger Fabric-X, with active work extending support to Ethereum and EVM-compatible chains.

Together, these layers enable token applications to be written once and deployed across multiple blockchain backends, with privacy, compliance, and performance characteristics configurable per deployment.

## What can Panurus be used for?

Panurus allows enterprises, financial institutions, and developers to:

- Issue and manage fungible tokens (divisible, interchangeable units) and non-fungible tokens (unique assets)
- Deploy privacy-preserving token flows using zero-knowledge proofs and Pedersen commitments
- Perform atomic cross-chain swaps via HTLC-based interledger protocols (Delivery versus Payment)
- Meet compliance and AML/KYC requirements through fine-grained auditor access to transaction data
- Achieve institutional-scale throughput via the UTXO model and Hyperledger Fabric-X (100K+ TPS)
- Build portable token applications that run across Hyperledger Fabric, Fabric-X, and EVM chains

Example use cases include:

- Wholesale central bank digital currencies (CBDC)
- Tokenized securities and bond settlement (DvP)
- Institutional digital asset management
- Carbon credit and environmental asset registries
- Supply chain asset tracking and provenance
- Loyalty and rewards programs
- Trade finance and invoice tokenization
- Cross-institutional settlement rails

## Resources

The following documents and links will help you understand Panurus' vision, architecture, specifications, and community.

- The [Panurus announcement blog post](https://www.lfdecentralizedtrust.org/blog/panurus-joins-lf-decentralized-trust-as-new-incubating-project) provides a thorough overview of the project's history, architecture, real-world deployments, and roadmap.
- The [panurus repository](https://github.com/LFDT-Panurus/panurus) contains the full SDK source code, driver implementations, and contribution guidelines.
- The [Panurus documentation](https://github.com/LFDT-Panurus/panurus/blob/main/docs/README.md) covers architecture, APIs, driver configuration, and service guides.
- The [Fabric Samples Token SDK](https://github.com/hyperledger/fabric-samples/tree/main/token-sdk) provides working end-to-end samples for getting started with Panurus on Hyperledger Fabric.
- The [project proposal](https://lf-decentralized-trust.github.io/project-proposals/proposals/incubation/hyperledger-token-sdk.html) describes the formal LFDT incubation proposal for Panurus.
- The [original Fabric Token SDK lab](https://github.com/hyperledger-labs/fabric-token-sdk) is the predecessor project from which Panurus was graduated.
- The [LFDT Meeting Calendar](https://zoom-lfx.platform.linuxfoundation.org/meetings/lf-decentralized-trust) lists all scheduled community calls, including Panurus community meetings.
- The [LFX mentorship project](https://mentorship.lfx.linuxfoundation.org/project/cf3aa0ed-f564-44fd-b11d-ef3fec61e798) describes the active mentorship initiative delivering a new privacy-preserving token driver for Panurus.
- The [Hyperledger Fabric-X roadmap blog](https://www.lfdecentralizedtrust.org/blog/the-hyperledger-fabric-x-roadmap) provides context for Panurus' high-performance backend integration.
- Our [Code of Conduct](https://www.lfdecentralizedtrust.org/code-of-conduct) describes expected behavior across the LFDT community.
- For security-related issues, please follow the security policy in the relevant repository. Do not post security-related content, issues, or discussions publicly in any repository.

## How to contribute

Panurus welcomes developers, financial engineers, privacy researchers, enterprise architects, and anyone interested in tokenization infrastructure for permissioned blockchain networks.

Good ways to get started:

1. Explore the [panurus repository](https://github.com/LFDT-Panurus/panurus) and review the architecture documentation.
2. Try the end-to-end [Fabric Samples Token SDK](https://github.com/hyperledger/fabric-samples/tree/main/token-sdk) to understand the developer experience.
3. Join community discussions on [LFDT Discord](https://discord.lfdecentralizedtrust.org). Channel: #fabric-token-sdk
4. Attend the monthly Panurus community calls. These meetings are open to everyone and are a good place to ask questions, discuss roadmap items, and learn how to contribute.

| Meeting | Calendar Link |
|---|---|
| Panurus Community Meeting | https://zoom-lfx.platform.linuxfoundation.org/meetings/lf-decentralized-trust |

Past meeting recordings and presentations can be accessed through:

- [LFX Individual Dashboard](https://openprofile.dev/)
- [LFDT Meeting Calendar](https://zoom-lfx.platform.linuxfoundation.org/meetings/lf-decentralized-trust)

For larger changes, please open an issue first so the community can discuss the design before implementation.

## Current Status

Panurus is an **incubating** LFDT project. It was accepted as a project in June 2026, graduating from the Hyperledger Labs incubator where it was developed as Fabric Token SDK since 2021.

The project has 39 contributors across organizations including IBM Research, Banque de France, Sign Global, and Offchain Labs, with active development (74 commits in the 30 days following graduation), 1,047 closed pull requests, and 425 closed issues.

The roadmap for the next 12–24 months includes:

- A v1.0 release with stable, versioned API guarantees
- Additional privacy-preserving token driver implementations
- Extended network backend support for Ethereum and EVM-compatible chains
- Growing production case studies and reference architectures
- Establishing a regular security audit cadence
- Building a diverse maintainer community across organizations

## License

Panurus code repositories are licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0), unless otherwise noted in a specific repository.

