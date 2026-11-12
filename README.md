Mobile Network Generations and Architecture
A step-by-step learning guide from 1G to 6G

This guide explains how mobile networks evolved from analogue voice calls to modern, software-driven mobile broadband and emerging AI-enabled networks. It is designed for beginners, students, and aspiring telecom engineers.
Status note: 1G–5G are historical or deployed generations. 6G is under research and standardisation; its architecture and capabilities are evolving, so examples here are conceptual rather than a final deployed standard.

Learning objectives
By the end, you should be able to:
- Explain the main purpose of each generation (1G–6G).
- Identify the major network components and how they connect.
- Describe the difference between the radio access network (RAN) and the core network.
- Understand the shift from analogue voice to digital, packet data, all-IP networks, and cloud-native cores.
- Recognise which proposed 6G capabilities are still under development.
Start here: How a mobile network works
A typical mobile system contains three main pieces:
1. User equipment (UE): a phone, modem, sensor, or another connected device.
2. Radio access network (RAN): radio sites and controllers that connect devices wirelessly to the operator network.
3. Core network: authenticates subscribers, manages connections and mobility, and routes voice or data to other networks.
Simplified view:
[Phone / Device] ))) [Radio Access Network] ---> [Core Network] ---> [Internet / Telephone Network]
The details change considerably between generations.
Step 1 — 1G: Analogue voice
Era: Commercially introduced in the late 1970s and 1980s (depending on country).

Main purpose: Wireless voice calling.
[1G Mobile Phone] ))) [Analogue Cell Site] ---> [Mobile Switching Network] ---> [PSTN / Telephone]
Learn:
1. A handset turns speech into an analogue electrical signal.
2. The handset transmits the signal by radio to a nearby cell site.
3. The mobile switching network connects the call to another phone.
4. A handoff may transfer the call when the user moves between cells.
Limitations: Analogue voice, limited capacity and security, and no modern packet-based mobile internet.

Key terms: AMPS, analogue radio, frequency division multiple access (FDMA), handoff, PSTN.
Step 2 — 2G: Digital voice and SMS
Era: Early 1990s onward.

Main purpose: Digital voice and text messaging; later, basic packet data.

Example: GSM architecture
[2G Phone] ))) [BTS] ---> [BSC] ---> [MSC] ---> [PSTN / Other Voice Networks]
                         |
                         +-- (GPRS/EDGE packet path via SGSN/GGSN) ---> [Internet]
Learn:
1. BTS (Base Transceiver Station) exchanges radio signals with the phone.
2. BSC (Base Station Controller) manages multiple BTS sites and radio resources.
3. MSC (Mobile Switching Centre) supports circuit-switched voice calls.
4. SMS allows short text messages; GPRS/EDGE later add mobile packet data through separate packet-core nodes.
Key terms: GSM, BTS, BSC, MSC, SIM, SMS, GPRS, EDGE.
Step 3 — 3G: Mobile internet
Era: Early 2000s onward.

Main purpose: Better mobile data, web access, multimedia, and video calls.

Example: UMTS architecture
[3G Phone] ))) [NodeB] ---> [RNC] ---> [3G Core Network] ---> [Internet / Telephone Network]
Learn:
1. NodeB is the 3G radio base station.
2. RNC (Radio Network Controller) controls groups of NodeBs and manages radio resources.
3. The core network supports voice and packet data, using different domains in classic UMTS deployments.
4. HSPA/HSPA+ improve data rates over early 3G systems.
Key terms: UMTS, WCDMA, NodeB, RNC, SGSN, GGSN, HSPA.
Step 4 — 4G: Mobile broadband and all-IP data
Era: Around 2009–2010 onward.

Main purpose: Fast mobile broadband, streaming, apps, and IP-based communication.

Example: LTE architecture
[4G Smartphone] ))) [eNodeB] ---> [EPC] ---> [Internet / IP Services]
                                     |
                                     +-- [IMS] ---> [VoLTE Calls]
Learn:
1. eNodeB (eNB) provides LTE radio access and handles many functions previously split across radio controllers.
2. EPC (Evolved Packet Core) handles mobility, authentication, and packet routing.
3. LTE uses an all-IP packet core rather than 2G/3G-style circuit-switched voice in its radio/core design.
4. IMS/VoLTE supports voice calling over LTE; early deployments also used fallbacks to older networks.
Key terms: LTE, eNodeB, EPC, MME, SGW, PGW, IMS, VoLTE.
Step 5 — 5G: Flexible, high-capacity connectivity
Era: Commercial deployments began in 2019.

Main purpose: Enhanced mobile broadband, lower-latency services, and connectivity for large numbers of devices.

Example: Standalone (SA) 5G architecture
[Phone / IoT Device] ))) [gNodeB (5G NR)] ---> [5G Core (service-based)] ---> [Data Network]
                                                   |
                                                   +-- [Edge Applications]
Learn:
1. gNodeB (gNB) provides 5G New Radio access.
2. The 5G Core (5GC) separates control functions and user-plane forwarding and uses a service-based architecture for many control-plane interactions.
3. Network slicing enables logical network arrangements for differing service requirements.
4. Edge computing may place applications close to users to reduce end-to-end delay.
5. Distinguish NSA (Non-Standalone) 5G, which relies on existing LTE infrastructure in some parts of the network, from SA (Standalone) 5G with a 5G Core.
Key terms: 5G NR, gNodeB, 5GC, AMF, SMF, UPF, SBA, slicing, MEC, NSA, SA.
Step 6 — 6G: Research and emerging architecture
Status: In research and standardisation; not yet a broadly deployed commercial generation as of October 2026.

Areas being explored: AI-assisted or AI-native networking, integrated sensing and communication, new spectrum options, advanced automation, and closer integration of terrestrial and non-terrestrial networks.

Illustrative concept — not a final 6G standard:
[Future Devices / Sensors] ))) [Advanced Radio Access]
                                      |
                            [Intelligent Network Functions]
                                      |
                       [Cloud / Edge / Satellite Services]
Learn:
1. Study how AI may help optimise network operation and resource management.
2. Explore proposed integrated sensing and communication (ISAC) capabilities.
3. Understand possible roles for non-terrestrial networks (NTN), such as satellite-based connectivity.
4. Separate research goals and marketing claims from features confirmed by standards and real deployments.
Key terms: IMT-2030, AI-native networks, ISAC, NTN, edge intelligence, 6G research.
Comparison at a glance
Generation	Primary shift	Representative radio access	Representative core/network
1G	Analogue mobile voice	Analogue cell site	Mobile switching network
2G	Digital voice and SMS	BTS + BSC (GSM)	MSC; packet nodes for GPRS/EDGE
3G	Richer mobile data	NodeB + RNC (UMTS)	Circuit/packet core domains
4G	All-IP mobile broadband	eNodeB (LTE)	EPC; IMS for VoLTE
5G	Advanced broadband and flexible services	gNodeB (5G NR)	5G Core (SBA)
6G	Proposed intelligent and integrated capabilities	Future advanced RAN (under study)	Architecture still evolving


Suggested seven-session study plan
1. Session 1 — Foundations: Learn UE, cells, spectrum, RAN, core, and PSTN.
2. Session 2 — 1G and 2G: Compare analogue and digital voice; trace a GSM call.
3. Session 3 — 3G: Draw NodeB → RNC → core and explain mobile data.
4. Session 4 — 4G: Trace an LTE data session and learn what EPC and IMS do.
5. Session 5 — 5G: Compare NSA versus SA; map gNodeB and 5G Core functions.
6. Session 6 — 6G: Review research directions and identify what is not yet standardised.
7. Session 7 — Review: Redraw all six architectures from memory and explain their differences.
Quick self-check
1. What does the letter G mean?
2. Why was the transition from 1G to 2G important?
3. What is the difference between a NodeB, eNodeB, and gNodeB?
4. What does the EPC do in 4G?
5. What is the difference between 5G NSA and SA?
6. Why should 6G diagrams be labelled conceptual?
Further reading
- 3GPP — Mobile telecommunications specifications
- ITU — International Telecommunication Union
- ETSI — European Telecommunications Standards Institute
Learning goal: Understand not only what changed between 1G and 6G, but where each function lives in the network and why the architecture changed.
