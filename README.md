# Evolution of Mobile Networks: 1G to 6G

> A research-oriented guide to cellular network generations, their technologies, architectures, and evolution.

## Contents

- [Overview](#overview)
- [Visual timeline: 1G to 6G](#visual-timeline-1g-to-6g)
- [Comparison at a glance](#comparison-at-a-glance)
- [Common architecture concepts](#common-architecture-concepts)
- [1G — Analog cellular](#1g--analog-cellular)
- [2G — Digital cellular](#2g--digital-cellular)
- [3G — Mobile internet](#3g--mobile-internet)
- [4G — All-IP broadband](#4g--all-ip-broadband)
- [5G — Service-based architecture](#5g--service-based-architecture)
- [6G — IMT-2030 research](#6g--imt-2030-research)
- [Architecture evolution](#architecture-evolution)
- [Research directions](#research-directions)
- [References](#references)

## Overview

The **G** in 1G–6G stands for **generation**. Each new generation changes wireless radio technology, the types of services networks support, and often the design of the radio access network (RAN) and core network.

- **1G:** Analog mobile voice.
- **2G:** Digital voice, SMS, and later packet data.
- **3G:** More practical mobile internet and multimedia.
- **4G:** High-speed, all-IP mobile broadband.
- **5G:** Enhanced broadband, low-latency capabilities, massive IoT, and service-based core networking.
- **6G:** A future generation under development, with research into AI integration, sensing, and ubiquitous connectivity.

> **Status note (October 2026):** 1G–5G are historical or deployed generations. 6G is not yet a finalized commercial cellular architecture. The diagrams below distinguish standardized implementations from proposed research concepts.

## Visual timeline: 1G to 6G

The following graphic is rendered directly by GitHub using **Mermaid** (no external image hosting required).

```mermaid
flowchart LR
    G1["📞 1G<br/>1980s<br/>Analog voice"] --> G2["✉️ 2G<br/>1990s<br/>Digital + SMS"]
    G2 --> G3["🌐 3G<br/>2000s<br/>Mobile internet"]
    G3 --> G4["📱 4G<br/>2010s<br/>All-IP LTE"]
    G4 --> G5["📡 5G<br/>2020s<br/>5G NR + 5GC"]
    G5 -.-> G6["🧠 6G<br/>~2030 target<br/>AI + sensing research"]
    classDef historical fill:#eaf3ff,stroke:#3778c2,color:#132b4b,stroke-width:1.5px;
    classDef current fill:#daf5e8,stroke:#237c54,color:#123d2a,stroke-width:1.5px;
    classDef future fill:#fff1da,stroke:#ac7522,color:#573708,stroke-dasharray:5 3;
    class G1,G2,G3,G4 historical;
    class G5 current;
    class G6 future;
```

**Reading the graphic:** Solid arrows show the progression of deployed generations; the dashed arrow marks 6G as an emerging, not-yet-finalized generation. Each generation's detailed network architecture appears below.

## Comparison at a glance

| Generation | Approx. introduction | Representative standards | Access / radio techniques | Core / network approach | Main use cases |
|---|---|---|---|---|---|
| **1G** | 1980s | AMPS, NMT, TACS | Analog FM, FDMA | Circuit-switched | Mobile voice |
| **2G** | 1990s | GSM, IS-95; GPRS/EDGE enhancements | TDMA or CDMA | Circuit-switched voice; later packet-data overlay | Voice, SMS, basic data |
| **3G** | 2000s | UMTS/WCDMA, CDMA2000; HSPA | Wideband CDMA / CDMA | Circuit- and packet-switched domains | Web, video calling, multimedia |
| **4G** | 2010s | LTE, LTE-Advanced | OFDMA downlink, SC-FDMA uplink (LTE), MIMO | Evolved Packet Core (EPC), all-IP | Streaming, broadband, VoLTE |
| **5G** | 2019 onward | 5G NR, 5G Core | OFDM-based NR, massive MIMO, beamforming | 5G Core (5GC), service-based control plane | eMBB, URLLC, mMTC |
| **6G** | ~2030 target | IMT-2030 framework; specifications in development | Candidate advanced radio and spectrum technologies | **Not finalized**; AI-integrated and distributed designs under study | Immersive services, integrated sensing, ubiquitous coverage |

*These are broad generational summaries; standards and deployments vary across operators and regions.*

## Common architecture concepts

```mermaid
flowchart TB
    UE[User Equipment / Mobile Device] <-->|Wireless Link| RAN[Radio Access Network / Base Stations]
    RAN <--> CN[Core Network]
    CN <--> EXT[Internet / Phone Network / Cloud]
```

- **User Equipment (UE):** Phones, modems, sensors, vehicles, or other connected devices.
- **Radio Access Network (RAN):** The antennas, base stations, and radio-control functions that connect devices to the network.
- **Core Network:** Authentication, mobility, call or session control, policy, and routing to other networks.
- **Circuit switching:** Reserves a connection for a call, as in classic telephone systems.
- **Packet switching:** Transfers data as packets, enabling IP-based services.

## 1G — Analog cellular

**Core idea:** The earliest cellular systems carried voice as an analog radio signal.

**Representative systems:** AMPS, NMT, and TACS.

### Simplified 1G architecture

```mermaid
flowchart LR
    PHONE[Analog Mobile Phone] <-->|Analog Radio| BS[Base Station]
    BS --> MTSO[Mobile Telephone Switching Office]
    MTSO --> PSTN[Public Switched Telephone Network]
```

**Architecture:** A phone communicated with a base station, while a mobile switching office set up calls, handled mobility, and connected calls to the public telephone network.

**Key characteristics:** Analog FM, FDMA, circuit switching.

**Limitations:** Weak privacy, limited capacity, and little to no general-purpose mobile data.

## 2G — Digital cellular

**Core idea:** Digital communication enabled clearer voice, SMS, better spectral efficiency, and improved security. GPRS later added packet data to GSM networks.

**Representative systems:** GSM and IS-95 (cdmaOne); GPRS and EDGE are commonly described as 2.5G/2.75G enhancements.

### Simplified GSM/GPRS architecture

```mermaid
flowchart TB
    MS[Mobile Station] --> BTS[Base Transceiver Station]
    BTS --> BSC[Base Station Controller]
    BSC --> MSC[Mobile Switching Centre]
    MSC --> PSTN[Telephone Network]
    BSC --> SGSN[Serving GPRS Support Node]
    SGSN --> GGSN[Gateway GPRS Support Node]
    GGSN --> NET[Internet / Packet Network]
    HLR[(HLR / Subscriber Records)] -.-> MSC
    HLR -.-> SGSN
```

| Component | Role |
|---|---|
| BTS | Transmits and receives radio signals |
| BSC | Controls multiple BTS sites and radio resources |
| MSC | Switches circuit-based voice calls |
| HLR / VLR | Maintains subscription and location information |
| SGSN | Handles packet-data mobility and sessions |
| GGSN | Provides packet-data connectivity to external networks |

**Architectural change from 1G:** Digital radio and, with GPRS, a separate packet-data path alongside circuit-switched voice.

## 3G — Mobile internet

**Core idea:** Higher-capacity radio access made web browsing, multimedia, and video calls more practical.

**Representative systems:** UMTS/WCDMA, CDMA2000, HSPA/HSPA+.

### Simplified UMTS architecture

```mermaid
flowchart TB
    UE[User Equipment] --> NB[Node B]
    NB --> RNC[Radio Network Controller]
    RNC --> MSC[MSC / Circuit-Switched Core]
    MSC --> PSTN[Telephone Network]
    RNC --> SGSN[SGSN]
    SGSN --> GGSN[GGSN]
    GGSN --> IP[Internet]
```

| Component | Role |
|---|---|
| Node B | 3G radio base station |
| RNC | Controls multiple Node Bs, radio resources, and handovers |
| MSC | Supports circuit-switched voice |
| SGSN / GGSN | Support packet-data services |

**Architectural change from 2G:** New wideband radio technologies and higher mobile data rates, while UMTS retained both circuit- and packet-switched core domains.

## 4G — All-IP broadband

**Core idea:** LTE introduced a flatter radio network and an all-IP packet core. Voice can be delivered over IMS as VoLTE.

**Representative systems:** LTE and LTE-Advanced.

### Simplified LTE / EPC architecture

```mermaid
flowchart TB
    UE[User Equipment] --> ENB[eNodeB / E-UTRAN]
    ENB -.->|Control signaling| MME[Mobility Management Entity]
    MME -.-> HSS[(Home Subscriber Server)]
    ENB -->|User traffic| SGW[Serving Gateway]
    SGW --> PGW[Packet Data Network Gateway]
    PGW --> DATA[Internet / Data Networks / IMS]
    MME -.-> SGW
```

| Component | Role |
|---|---|
| eNodeB | LTE radio access, scheduling, and radio mobility functions |
| MME | Control-plane mobility and signaling |
| S-GW | User-packet forwarding and mobility anchor |
| P-GW | Connectivity to external packet networks |
| HSS | Subscriber data and authentication support |
| PCRF | Policy and charging decisions |
| IMS | IP multimedia services, including VoLTE |

**Architectural change from 3G:** No separate RNC in LTE; a flatter RAN, packet-only core, and standardized control-/user-plane functions.

## 5G — Service-based architecture

**Core idea:** 5G combines **New Radio (NR)** with a flexible core, especially in **Standalone (SA)** deployments. A **Non-Standalone (NSA)** deployment can use LTE/EPC as its anchor; the diagram below focuses on 5G SA.

### Simplified 5G Standalone architecture

```mermaid
flowchart TB
    UE[5G User Equipment] --> GNB[gNodeB / NG-RAN]
    GNB -.->|N2 control plane| AMF[AMF]
    GNB -->|N3 user plane| UPF[UPF]
    AMF -.-> SMF[SMF]
    SMF -.->|N4 control| UPF
    UPF --> DN[Data Network / Internet / Edge]
    AMF -.-> AUSF[AUSF]
    AMF -.-> UDM[UDM]
    AMF -.-> NSSF[NSSF]
    SMF -.-> PCF[PCF]
    NRF[NRF] -.-> AMF
    NRF -.-> SMF
```

*Dotted lines represent simplified logical control/service relationships, not a complete set of standardized reference points.*

| 5G function | Meaning | Primary responsibility |
|---|---|---|
| AMF | Access and Mobility Management Function | Registration and mobility signaling |
| SMF | Session Management Function | PDU session management |
| UPF | User Plane Function | Packet forwarding and data-network connectivity |
| AUSF | Authentication Server Function | Authentication |
| UDM | Unified Data Management | Subscriber data management |
| PCF | Policy Control Function | Policy decisions |
| NRF | Network Repository Function | Network-function discovery |
| NSSF | Network Slice Selection Function | Slice selection support |
| NEF | Network Exposure Function | Controlled exposure of network capabilities |

### Main 5G service categories

- **eMBB (Enhanced Mobile Broadband):** High-throughput multimedia and broadband.
- **URLLC (Ultra-Reliable Low-Latency Communications):** Time-critical communications with strict reliability requirements.
- **mMTC (Massive Machine-Type Communications):** Very large numbers of connected devices.

**Architectural change from 4G:** A service-based 5G core, more flexible software/cloud deployments, network slicing, and stronger separation of control and user functions. Network slicing is a logical feature of the overall system; it is not equivalent to deploying a physically separate network for each customer.

## 6G — IMT-2030 research

**Core idea:** 6G is under research and standardization. The ITU's name for the next IMT generation is **IMT-2030**. Its scope includes enhanced communications, sensing, AI-related capabilities, and broader coverage.

> **Important:** The following is an **illustrative research concept**, **not an official or finalized 6G reference architecture**. Specific network functions, interfaces, and deployment choices will depend on future standards.

### Illustrative 6G research architecture

```mermaid
flowchart TB
    DEV[Devices: XR / Robots / Vehicles / Sensors]
    DEV <--> ACCESS[Integrated Access Layer]
    TER[Terrestrial Radio] <--> ACCESS
    NTN[Non-Terrestrial Networks / Satellites] <--> ACCESS
    SENSE[Integrated Sensing Functions] <--> ACCESS
    ACCESS <--> EDGE[Distributed Edge Computing and AI]
    EDGE <--> CORE[Future Programmable Core / Orchestration]
    CORE <--> CLOUD[Cloud / Applications / Digital Twins]
    AI[AI-driven Optimization and Automation] -.-> ACCESS
    AI -.-> EDGE
    AI -.-> CORE
```

### Candidate research areas

- **AI-integrated networking:** AI for resource allocation, management, and possibly protocol design.
- **Integrated Sensing and Communication (ISAC):** Radio systems that support both connectivity and sensing functions.
- **Terrestrial/non-terrestrial integration:** Coordinated ground networks and satellite links.
- **Advanced spectrum:** Research on new high-frequency bands, including sub-THz candidates.
- **Distributed / cell-free MIMO:** Coordinated radio transmission from distributed sites.
- **Edge intelligence:** Computation and machine learning close to devices.
- **Network digital twins:** Simulation and monitoring of network behavior.

### ITU IMT-2030 usage scenarios

1. Immersive Communication (IC)
2. Hyper-Reliable and Low-Latency Communication (HRLLC)
3. Massive Communication (MC)
4. Ubiquitous Connectivity (UC)
5. Artificial Intelligence and Communication (AIAC)
6. Integrated Sensing and Communication (ISAC)

The IMT-2030 framework discusses ambitious capability ranges. They are **research objectives**, not guaranteed field performance or requirements already delivered by commercial 6G systems.

## Architecture evolution

```mermaid
flowchart LR
    G1[1G<br/>Analog + Circuit Switching] --> G2[2G<br/>Digital Voice + SMS<br/>Later Packet Data]
    G2 --> G3[3G<br/>Wideband Radio<br/>Circuit + Packet Core]
    G3 --> G4[4G<br/>LTE + All-IP EPC]
    G4 --> G5[5G<br/>5G NR + Service-Based 5GC]
    G5 --> G6[6G Research<br/>IMT-2030 + AI + Sensing]
```

| Dimension | 1G | 2G | 3G | 4G | 5G | 6G (research) |
|---|---|---|---|---|---|---|
| Voice | Analog circuit | Digital circuit | Mainly circuit | IP/IMS (VoLTE) | IMS / VoNR and interworking | To be defined |
| Data | Minimal | GPRS/EDGE | Packet core / HSPA | All-IP EPC | 5GC packet sessions | Future architecture TBD |
| Radio node | Base station | BTS | Node B | eNodeB | gNodeB | Not finalized |
| Core model | Switching office | MSC; SGSN/GGSN | MSC; SGSN/GGSN | EPC | 5GC | Under development |
| Main innovation | Mobility | Digital cellular | Mobile internet | Broadband IP | Flexible service-based architecture | Intelligent connectivity and sensing research |

## Research directions

Areas well suited to a technical paper or thesis include:

1. **4G EPC vs. 5G Core:** Compare MME/HSS/S-GW/P-GW against AMF/SMF/UPF/UDM and the service-based control plane.
2. **RAN evolution:** Compare BTS+BSC, Node B+RNC, eNodeB, and gNodeB; explore disaggregation and cloud RAN.
3. **Network slicing:** Isolation, orchestration, reliability, and resource guarantees.
4. **Energy-efficient radio networks:** Power consumption versus coverage, capacity, and traffic demand.
5. **AI in 5G-Advanced and future 6G:** Model deployment, reliability, explainability, and security.
6. **ISAC and terrestrial/non-terrestrial integration:** Trade-offs in coverage, spectrum, and coordination.

## References

Primary and standards-oriented resources:

1. **ITU-R M.2160**, *Framework and overall objectives of the future development of IMT for 2030 and beyond*. [ITU IMT-2030 overview](https://www.itu.int/en/ITU-R/study-groups/rsg5/rwp5d/imt-2030/Pages/default.aspx).
2. **3GPP TS 23.501**, *System Architecture for the 5G System (5GS)*. [3GPP specification portal](https://www.3gpp.org/dynareport/23501.htm).
3. **3GPP TS 23.502**, *Procedures for the 5G System (5GS)*. [3GPP specification portal](https://www.3gpp.org/dynareport/23502.htm).
4. **3GPP TS 23.002**, *Network architecture* (GSM/UMTS and related systems). [3GPP specification portal](https://www.3gpp.org/dynareport/23002.htm).
5. **3GPP TS 23.401**, *GPRS enhancements for E-UTRAN access* (LTE/EPC). [3GPP specification portal](https://www.3gpp.org/dynareport/23401.htm).
6. **3GPP TS 38.300**, *NR and NG-RAN Overall Description*. [3GPP specification portal](https://www.3gpp.org/dynareport/38300.htm).
7. **ITU**, [International Mobile Telecommunications (IMT)](https://www.itu.int/en/ITU-R/Pages/default.aspx) — background on global mobile radio frameworks.

> **Research note:** These diagrams deliberately simplify real networks and omit some interfaces, security functions, roaming architectures, and deployment variants. For rigorous implementation work, refer to the cited specification releases and their exact versions.

---

**Suggested repository topics:** `telecommunications`, `mobile-networks`, `1g`, `2g`, `3g`, `4g`, `5g`, `6g`, `network-architecture`, `wireless-communication`, `research`.
