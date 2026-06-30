# Architecture Decision Records Index

## Overview

This index provides a comprehensive catalogue of all Architecture Decision Records (ADRs) governing the SAP on Azure reference architecture. ADRs capture significant architectural decisions, their context, rationale, and consequences, ensuring that the reasoning behind key choices is preserved and accessible to all stakeholders. In the SAP on Azure context, where decisions span networking, compute, storage, security, high availability, disaster recovery, and governance, a structured decision record approach is essential for maintaining architectural integrity across multi-year programmes.

This index serves as the single authoritative reference for ADR discovery and navigation. Each ADR is cross-referenced to the relevant chapters in this documentation set, enabling readers to trace from a design recommendation back to the underlying architectural decision. The index is maintained by the Architecture Review Board (ARB) and updated as part of the quarterly review cadence defined in the ADR Process section below.

---

## ADR Process

### Lifecycle States

ADRs in this programme follow a four-state lifecycle:

```
Proposed --> Accepted --> Deprecated
                 |
                 v
            Superseded
```

| State | Description |
|---|---|
| Proposed | Draft ADR submitted for review; not yet authoritative |
| Accepted | Approved by ARB; governs current architecture |
| Deprecated | No longer relevant; not replaced by a newer decision |
| Superseded | Replaced by a newer ADR; superseding ADR number noted |

### Roles and Responsibilities

| Role | Responsibility |
|---|---|
| Solution Architect | Identifies need for ADR; drafts initial content |
| Domain Lead | Reviews technical accuracy within their domain |
| Architecture Review Board | Approves or rejects ADRs; manages lifecycle transitions |
| Programme Manager | Ensures ADR review cadence is maintained |
| Security Lead | Reviews all ADRs with security implications |
| SAP Basis Lead | Reviews all ADRs with SAP-specific implications |

### When to Create an ADR

An ADR must be created when any of the following criteria are met:

- The decision involves a technology selection with significant cost, security, or operational impact
- The decision is difficult or expensive to reverse once implemented
- Multiple reasonable alternatives exist and the choice is non-obvious
- The decision affects more than one workload, subscription, or team
- The decision deviates from Microsoft or SAP published best practice
- The decision involves a commitment (Reserved Instance, Enterprise Agreement SKU lock-in)
- The decision has compliance or regulatory implications
- Stakeholders have disagreed about the approach during design sessions

### ADR Review Process

1. **Identify need:** Architect identifies a decision point meeting the above criteria
2. **Draft ADR:** Use the template at `adr/templates/adr-template.md`; fill all required sections
3. **Self-review:** Author validates against the ADR template checklist
4. **Domain review:** Domain Lead reviews for technical accuracy (minimum 2 business days)
5. **Security review:** Security Lead reviews ADRs touching identity, network, or data (minimum 2 business days)
6. **Pull request:** Submit ADR as a PR to the `docs/adr/` directory; link to relevant chapter PRs
7. **ARB review:** ARB reviews at the next scheduled meeting (weekly during design phase; monthly during delivery)
8. **Acceptance or rejection:** ARB approves (state to Accepted), requests changes (state remains Proposed), or rejects (ADR closed with reasoning recorded)

**Quarterly Review Cadence:** The ARB conducts a quarterly sweep of all Accepted ADRs to identify candidates for Deprecated or Superseded status based on technology changes, new SAP guidance, or Microsoft product evolution.

---

## Master ADR Index

| ADR | Title | Status | Domain | Decision Date | Supersedes |
|---|---|---|---|---|---|
| ADR-0001 | Hub-Spoke VNet Topology for SAP Landing Zone | Accepted | Landing Zone | 2024-01-15 | — |
| ADR-0002 | Subscription Topology: Production and Non-Production Under SAP Management Group | Accepted | Landing Zone | 2024-01-15 | — |
| ADR-0003 | ExpressRoute as Primary Connectivity for SAP to On-Premises | Accepted | Networking | 2024-01-22 | — |
| ADR-0004 | Azure Firewall Premium as Centralised Egress and Inspection Point | Accepted | Networking | 2024-01-22 | — |
| ADR-0005 | Hub-Spoke VNet over Azure Virtual WAN for SAP Landing Zone | Accepted | Networking | 2024-01-22 | — |
| ADR-0006 | Mv2-Series VM Family as Primary for SAP HANA Scale-Up | Accepted | Compute | 2024-02-05 | — |
| ADR-0007 | Ultra Disk for HANA Log; Azure NetApp Files for HANA Data and Shared | Accepted | Storage | 2024-02-05 | — |
| ADR-0008 | Azure NetApp Files Ultra Performance Tier for SAP HANA | Accepted | Storage | 2024-02-05 | — |
| ADR-0009 | Availability Zones over Availability Sets for SAP High Availability | Accepted | HA | 2024-02-12 | — |
| ADR-0010 | ENSA2 over ENSA1 for ASCS/ERS High Availability | Accepted | SAP HANA | 2024-02-12 | — |
| ADR-0011 | HANA System Replication SYNC Mode for Within-Region HA | Accepted | SAP HANA | 2024-02-12 | — |
| ADR-0012 | Azure Backup Backint Agent for HANA; RMAN with Azure Blob for Oracle | Accepted | DR | 2024-02-19 | — |
| ADR-0013 | Warm Standby DR with HSR ASYNC to Secondary Region | Accepted | DR | 2024-02-19 | — |
| ADR-0014 | Azure Policy Enforce Mode for SAP Landing Zone Controls | Accepted | Governance | 2024-03-04 | — |
| ADR-0015 | Entra ID SSO (SAML 2.0) for SAP Fiori and Web Dispatcher | Accepted | Security | 2024-03-04 | — |
| ADR-0016 | Microsoft Sentinel with SAP Solution as Primary SIEM | Accepted | Security | 2024-03-04 | — |
| ADR-0017 | Azure Monitor for SAP Solutions as Primary Monitoring Platform | Accepted | Operations | 2024-03-11 | — |
| ADR-0018 | Centralised Private DNS Zone Design for SAP Workloads | Accepted | Networking | 2024-03-11 | — |
| ADR-0019 | RHEL for SAP Solutions as Preferred OS; SLES as Supported Alternative | Accepted | Compute | 2024-03-18 | — |
| ADR-0020 | Reserved Instance Commitment Strategy for SAP Compute | Accepted | Governance | 2024-03-18 | — |
| ADR-0021 | Azure Backup Vault with Cross-Region Restore for SAP VMs | Accepted | DR | 2024-03-25 | — |
| ADR-0022 | Backup Retention Design: 35-Day Operational plus 7-Year Compliance | Accepted | DR | 2024-03-25 | — |
| ADR-0023 | Azure Firewall Premium over Third-Party NVA for SAP Traffic Inspection | Accepted | Networking | 2024-04-01 | — |
| ADR-0024 | Pacemaker with Azure Fence Agent for SAP Cluster Fencing | Accepted | HA | 2024-04-01 | — |
| ADR-0025 | HANA Scale-Up Architecture as Default; Scale-Out Reserved for BW/4HANA | Accepted | SAP HANA | 2024-04-08 | — |
| ADR-0026 | Proximity Placement Groups Per Availability Zone for SAP HA Pairs | Accepted | Compute | 2024-04-08 | — |
| ADR-0027 | Entra ID Conditional Access for SAP Administrative Access | Accepted | Security | 2024-04-15 | — |
| ADR-0028 | ANF Cross-Region Replication for HANA Shared and sapmnt DR | Accepted | DR | 2024-04-15 | — |
| ADR-0029 | Infrastructure as Code Mandate: Bicep Primary, Terraform Secondary | Accepted | Governance | 2024-04-22 | — |
| ADR-0030 | Azure Bastion Standard as Sole Administrative Access Path for SAP VMs | Accepted | Security | 2024-04-22 | — |

---

## ADR Detail Summaries

### ADR-0001: Hub-Spoke VNet Topology for SAP Landing Zone

**Status:** Accepted | **Decision Date:** 2024-01-15 | **Domain:** Landing Zone

**Context:** SAP workloads require network isolation between tiers (HANA, application, web dispatcher), controlled connectivity to on-premises via ExpressRoute, and centralised security inspection. Multiple topology patterns are available in Azure: flat VNet, hub-spoke, and Azure Virtual WAN.

**Decision:** Implement a hub-spoke VNet topology with a dedicated SAP spoke VNet per environment (production, non-production). The hub VNet hosts shared services: ExpressRoute Gateway, VPN Gateway, Azure Firewall, Azure Bastion, and Private DNS Resolver.

**Rationale:** Hub-spoke provides clear network segmentation, centralises security controls in the hub, allows independent scaling of spoke VNets, and aligns with the Azure Landing Zone accelerator for SAP. The topology simplifies firewall rule management by funnelling all inter-spoke and internet-bound traffic through the hub.

**Chapter References:** Chapter 02 (Networking Design), Chapter 03 (Landing Zone)
**SAP Notes:** SAP Note 2015553, SAP Note 1928533

---

### ADR-0002: Subscription Topology: Production and Non-Production Under SAP Management Group

**Status:** Accepted | **Decision Date:** 2024-01-15 | **Domain:** Landing Zone

**Context:** Azure governance requires a management group hierarchy that separates SAP workloads from other enterprise workloads while enabling consistent policy application. The number of subscriptions needed must balance blast radius isolation against management overhead.

**Decision:** Create a dedicated SAP Management Group under the corporate Landing Zone hierarchy. Provision separate subscriptions for SAP Production and SAP Non-Production. Shared services (hub networking, monitoring) reside in the existing Connectivity and Management subscriptions from the enterprise Landing Zone.

**Rationale:** Subscription-level isolation limits the blast radius of misconfiguration, enables separate RBAC boundaries for production operations, supports independent cost tracking, and allows production-specific Azure Policy assignments (e.g., stricter change management locks on production resources).

**Chapter References:** Chapter 03 (Landing Zone), Chapter 14 (Governance)
**SAP Notes:** None directly applicable

---

### ADR-0003: ExpressRoute as Primary Connectivity for SAP to On-Premises

**Status:** Accepted | **Decision Date:** 2024-01-22 | **Domain:** Networking

**Context:** SAP workloads require high-bandwidth, low-latency connectivity to on-premises data centres for RFC/IDOC interfaces, ALE distribution, batch file transfers, and user access from corporate network. Both ExpressRoute and Site-to-Site VPN are available Azure connectivity options.

**Decision:** Deploy ExpressRoute circuits as the primary connectivity mechanism between the SAP Azure landing zone and on-premises. Provision Site-to-Site VPN as a backup path for ExpressRoute failover. Use ExpressRoute Global Reach to enable direct on-premises-to-on-premises routing where multiple sites connect to Azure.

**Rationale:** ExpressRoute provides dedicated bandwidth, predictable latency (sub-10ms achievable), and SLA-backed availability not possible with internet-based VPN. SAP RFC and IDOC traffic patterns benefit from consistent low-latency connectivity. The VPN backup ensures business continuity during ExpressRoute outages.

**Chapter References:** Chapter 02 (Networking Design)
**SAP Notes:** SAP Note 1928533, SAP Note 2015553

---

### ADR-0004: Azure Firewall Premium as Centralised Egress and Inspection Point

**Status:** Accepted | **Decision Date:** 2024-01-22 | **Domain:** Networking

**Context:** SAP workloads generate diverse traffic: internet-bound software downloads, Microsoft 365 connectivity, Azure PaaS service access, and inter-spoke traffic. All outbound traffic requires inspection and control. The choice between Azure Firewall and third-party NVAs must be made.

**Decision:** Deploy Azure Firewall Premium in the hub VNet as the single egress and traffic inspection point. Configure IDPS in Alert and Deny mode. Use Azure Firewall Policy with Rule Collection Groups organised by SAP workload domain.

**Rationale:** Azure Firewall Premium provides IDPS, TLS inspection, and URL filtering without the operational overhead of NVA cluster management. Native integration with Azure Monitor and Microsoft Sentinel simplifies security operations. The Premium SKU supports the TLS inspection required for SAP cloud connector and SAP BTP traffic.

**Chapter References:** Chapter 02 (Networking Design), Chapter 12 (Security)
**SAP Notes:** None directly applicable

---

### ADR-0005: Hub-Spoke VNet over Azure Virtual WAN for SAP Landing Zone

**Status:** Accepted | **Decision Date:** 2024-01-22 | **Domain:** Networking

**Context:** Azure Virtual WAN (vWAN) offers an alternative to hub-spoke that simplifies branch connectivity and provides automated routing. The SAP programme must choose between hub-spoke and vWAN as the foundational network topology.

**Decision:** Implement hub-spoke VNet topology rather than Azure Virtual WAN for the SAP landing zone.

**Rationale:** At the time of decision, Azure Virtual WAN has limitations relevant to SAP: (1) third-party NVA integration in the vWAN hub does not support all SAP traffic patterns; (2) Azure Bastion cannot be deployed directly in a vWAN hub; (3) the programme's existing enterprise Landing Zone uses hub-spoke, and vWAN would require a parallel architecture. Hub-spoke provides full control over routing and security without vWAN constraints. This decision is flagged for review in Q3 2026 as vWAN capabilities continue to mature.

**Chapter References:** Chapter 02 (Networking Design), Chapter 03 (Landing Zone)
**SAP Notes:** None directly applicable

---

### ADR-0006: Mv2-Series VM Family as Primary for SAP HANA Scale-Up

**Status:** Accepted | **Decision Date:** 2024-02-05 | **Domain:** Compute

**Context:** SAP HANA requires certified Azure VM families. Multiple options exist: M-series (original), Mv2-series, and the newer Msv3/Mdsv3 series. The decision must balance memory capacity, certification status, price, and availability.

**Decision:** Select Mv2-series (Standard_M208ms_v2, Standard_M416ms_v2, Standard_M416s_v2) as the primary VM family for SAP HANA scale-up deployments. Msv3/Mdsv3 series to be evaluated for Q3 2026 refresh.

**Rationale:** Mv2-series is fully SAP HANA-certified for scale-up to 12 TB in the TDIv5 framework. The series provides the memory-to-CPU ratios required for HANA in-memory operation. Mv2 VMs are available in all required Azure regions with Availability Zone support. The newer Msv3 series, while promising, lacked full TDIv5 certification coverage at decision time.

**Chapter References:** Chapter 04 (Compute), Chapter 05 (SAP HANA)
**SAP Notes:** SAP Note 1928533, SAP Note 2316233, SAP Note 2855238

---

### ADR-0007: Ultra Disk for HANA Log; Azure NetApp Files for HANA Data and Shared

**Status:** Accepted | **Decision Date:** 2024-02-05 | **Domain:** Storage

**Context:** SAP HANA storage requires specific IOPS, throughput, and latency characteristics for log (write-intensive, latency-critical), data (read-intensive during restart, large sequential), and shared (/hana/shared, /usr/sap) volumes. Multiple Azure storage options exist: Premium SSD, Ultra Disk, and Azure NetApp Files.

**Decision:** Use Azure Ultra Disk for the HANA log volume (/hana/log) to meet the 1 ms write latency requirement. Use Azure NetApp Files (ANF) Ultra performance tier for HANA data (/hana/data) and shared (/hana/shared) volumes.

**Rationale:** Ultra Disk provides sub-millisecond latency for HANA log writes, which is critical for HANA savepoint and transaction commit performance. ANF provides NFS-based shared storage required for HANA shared volumes, supports HSR replication scenarios, and enables ANF Cross-Region Replication for DR. ANF Ultra tier meets SAP KPI requirements for HANA data volumes per SAP Note 2972496.

**Chapter References:** Chapter 06 (Storage), Chapter 05 (SAP HANA)
**SAP Notes:** SAP Note 2972496, SAP Note 2789388, SAP Note 3024346

---

### ADR-0008: Azure NetApp Files Ultra Performance Tier for SAP HANA

**Status:** Accepted | **Decision Date:** 2024-02-05 | **Domain:** Storage

**Context:** ANF offers Standard, Premium, and Ultra performance tiers with different throughput and IOPS characteristics. The tier selection must meet SAP HANA KPI requirements validated by SAP Storage Connector API checks.

**Decision:** Deploy all SAP HANA volumes (data, log backup, shared) on ANF Ultra performance tier.

**Rationale:** ANF Ultra provides 128 MiB/s throughput per TiB of capacity, enabling SAP HANA KPI compliance for volumes sized per SAP guidelines. The performance tier is consistent and does not degrade under concurrent workloads. ANF Ultra supports the throughput requirements documented in SAP Note 2972496 for HANA data volumes without requiring oversized capacity to reach performance targets.

**Chapter References:** Chapter 06 (Storage)
**SAP Notes:** SAP Note 2972496, SAP Note 3024346

---

### ADR-0009: Availability Zones over Availability Sets for SAP High Availability

**Status:** Accepted | **Decision Date:** 2024-02-12 | **Domain:** HA

**Context:** Azure provides two mechanisms for spreading SAP VMs across fault domains: Availability Sets (fault domain and update domain spreading within a datacenter) and Availability Zones (spreading across physically separate datacenters within a region). The HA architecture must choose the primary spreading mechanism.

**Decision:** Deploy all SAP HA pairs (HANA primary/secondary, ASCS/ERS, application server pairs) across Availability Zones. Use Availability Sets only for regions where Availability Zones are not available.

**Rationale:** Availability Zones provide a higher level of isolation than Availability Sets by separating workloads across physically distinct datacenters with independent power, cooling, and network. Zone-redundant deployments protect against datacenter-level failures, not just rack-level failures. Azure Load Balancer Standard and ANF support zone-redundant configurations. Microsoft Azure SLA for zone-redundant VMs is 99.99% versus 99.95% for Availability Sets.

**Chapter References:** Chapter 07 (High Availability), Chapter 04 (Compute)
**SAP Notes:** SAP Note 1928533, SAP Note 2694118

---

### ADR-0010: ENSA2 over ENSA1 for ASCS/ERS High Availability

**Status:** Accepted | **Decision Date:** 2024-02-12 | **Domain:** SAP HANA

**Context:** SAP provides two Enqueue Server architectures: ENSA1 (original, where ERS holds a replication of the enqueue lock table) and ENSA2 (simplified, where ERS takes over as primary enqueue server on ASCS failure). New SAP releases support ENSA2; some older releases require ENSA1.

**Decision:** Implement ENSA2 for all SAP ASCS/ERS HA configurations where the SAP release supports it (SAP kernel 7.53+, SAP S/4HANA 1809+).

**Rationale:** ENSA2 simplifies the HA architecture by eliminating the separate Enqueue Replication Server process dependency. ENSA2 provides faster failover and eliminates edge cases in ENSA1 where the ERS lock table could be incomplete. SAP has positioned ENSA2 as the strategic architecture and ENSA1 as legacy.

**Chapter References:** Chapter 07 (High Availability), Chapter 08 (SAP Application Layer)
**SAP Notes:** SAP Note 2630416, SAP Note 3064934

---

### ADR-0011: HANA System Replication SYNC Mode for Within-Region HA

**Status:** Accepted | **Decision Date:** 2024-02-12 | **Domain:** SAP HANA

**Context:** HANA System Replication (HSR) supports multiple replication modes: SYNC (synchronous with acknowledgement), SYNCMEM (synchronous in memory only), and ASYNC (asynchronous). The mode choice affects RTO/RPO and application write latency.

**Decision:** Configure HSR in SYNC mode with logreplay operation mode for all within-region HA configurations.

**Rationale:** SYNC mode guarantees zero RPO for committed transactions. The primary node does not acknowledge a commit until the secondary has written to its persistent log. Within an Azure region using Availability Zones, the network latency between zones is consistently below 2ms, making SYNC mode feasible without significant application impact. ASYNC mode would allow data loss on failover, which is not acceptable for production financial and logistics SAP systems. The logreplay operation mode minimises secondary takeover time.

**Chapter References:** Chapter 05 (SAP HANA), Chapter 07 (High Availability)
**SAP Notes:** SAP Note 2407186, SAP Note 1999880

---

### ADR-0012: Azure Backup Backint Agent for HANA; RMAN with Azure Blob for Oracle

**Status:** Accepted | **Decision Date:** 2024-02-19 | **Domain:** DR

**Context:** SAP HANA backup can be performed via: (1) Azure Backup with the Backint agent (native integration), (2) storage snapshots via ANF, or (3) custom backup scripts. Oracle-based SAP systems require a separate backup strategy.

**Decision:** Use Azure Backup with the Backint agent as the primary backup mechanism for SAP HANA. For Oracle-based SAP systems, use RMAN with Azure Blob Storage as the backup target via Azure Backup for Oracle.

**Rationale:** Azure Backup with Backint provides native integration with SAP HANA, supports streaming backups directly to the Recovery Services Vault, and enables point-in-time recovery through log backup chain management. The Backint interface is the SAP-recommended method for cloud backup integration. RMAN is the Oracle-native backup mechanism, and Azure Blob provides cost-effective storage for RMAN backup sets at scale.

**Chapter References:** Chapter 10 (Backup and Recovery), Chapter 11 (Disaster Recovery)
**SAP Notes:** SAP Note 2713666, SAP Note 2039883

---

### ADR-0013: Warm Standby DR with HSR ASYNC to Secondary Region

**Status:** Accepted | **Decision Date:** 2024-02-19 | **Domain:** DR

**Context:** A DR strategy must be defined balancing RTO/RPO requirements against cost. Options include: cold standby (restore from backup), warm standby (pre-provisioned infrastructure, replication-based), and hot standby (active-active with synchronous replication).

**Decision:** Implement a warm standby DR strategy. Deploy pre-provisioned but deallocated (or minimally sized) VMs in the secondary Azure region. Use HSR ASYNC mode for HANA data replication to the DR site. Use ANF Cross-Region Replication (CRR) for shared volumes.

**Rationale:** Cold standby cannot meet the programme's RTO target of 4 hours. Hot standby (active-active with synchronous cross-region replication) is cost-prohibitive and not technically feasible with SYNC mode due to inter-region latency. Warm standby with ASYNC replication provides near-zero RPO for committed transactions (typically less than 15 seconds replication lag) and an RTO achievable within the 4-hour target by pre-provisioning infrastructure and maintaining current OS and SAP binaries on DR VMs.

**Chapter References:** Chapter 11 (Disaster Recovery)
**SAP Notes:** SAP Note 2407186, SAP Note 1999880

---

### ADR-0014: Azure Policy Enforce Mode for SAP Landing Zone Controls

**Status:** Accepted | **Decision Date:** 2024-03-04 | **Domain:** Governance

**Context:** Azure Policy can operate in Audit mode (logs non-compliance) or Enforce mode (prevents non-compliant resource creation). The governance posture for the SAP landing zone must be defined.

**Decision:** Deploy all SAP-specific Azure Policies in Enforce (Deny) mode for security and networking controls. Deploy cost and tagging policies in Audit mode initially, transitioning to Enforce mode after 60 days of baseline measurement.

**Rationale:** Enforce mode prevents configuration drift before it occurs, eliminating the need for remediation tasks. For security controls (no public IPs on SAP VMs, mandatory disk encryption, required NSG attachment), Audit mode provides insufficient protection as violations persist until discovered and remediated. The phased approach for cost/tagging policies allows legitimate exceptions to be identified before enforcement breaks deployments.

**Chapter References:** Chapter 14 (Governance), Chapter 12 (Security)
**SAP Notes:** None directly applicable

---

### ADR-0015: Entra ID SSO (SAML 2.0) for SAP Fiori and Web Dispatcher

**Status:** Accepted | **Decision Date:** 2024-03-04 | **Domain:** Security

**Context:** SAP Fiori users require single sign-on from corporate credentials. SSO can be implemented via SAML 2.0, OAuth 2.0/OIDC, or Kerberos (SNC). The identity provider is Microsoft Entra ID.

**Decision:** Implement SAML 2.0-based SSO from Microsoft Entra ID to SAP Fiori launchpad via the SAP Fiori enterprise application in Entra ID. Configure the SAP Web Dispatcher as the SAML service provider. Use SAP Cloud Identity Services (IAS/IPS) as an intermediary for provisioning and proxy authentication where required.

**Rationale:** SAML 2.0 is the mature, broadly supported standard for SAP Fiori SSO. Entra ID has a pre-built SAP Fiori gallery application with documented configuration. SAML 2.0 allows Entra ID Conditional Access policies to be enforced at authentication time, enabling MFA requirements and device compliance checks before SAP access is granted.

**Chapter References:** Chapter 12 (Security), Chapter 13 (Identity and Access)
**SAP Notes:** SAP Note 2173571, SAP Note 1846202

---

### ADR-0016: Microsoft Sentinel with SAP Solution as Primary SIEM

**Status:** Accepted | **Decision Date:** 2024-03-04 | **Domain:** Security

**Context:** SAP audit logs, security logs, and Azure infrastructure logs require centralised SIEM for threat detection and compliance. Options include Microsoft Sentinel, SAP Enterprise Threat Detection (ETD), and third-party SIEMs (Splunk, QRadar).

**Decision:** Deploy Microsoft Sentinel as the primary SIEM. Enable the Microsoft Sentinel Solution for SAP to ingest SAP ABAP audit logs, SAP security audit log, and SAP ICM/Web Dispatcher logs. Retain SAP Solution Manager for ABAP transport management monitoring.

**Rationale:** Microsoft Sentinel provides native Azure integration, built-in connectors for all Azure services used in the landing zone (Azure Firewall, Entra ID, Azure Activity), and the SAP Solution provides pre-built analytic rules for SAP-specific threat scenarios (privilege escalation, RFC gateway abuse, sensitive table access). A single SIEM simplifies SOC operations versus maintaining both Sentinel and SAP ETD.

**Chapter References:** Chapter 12 (Security)
**SAP Notes:** SAP Note 3254025

---

### ADR-0017: Azure Monitor for SAP Solutions as Primary Monitoring Platform

**Status:** Accepted | **Decision Date:** 2024-03-11 | **Domain:** Operations

**Context:** SAP monitoring requires visibility into SAP application metrics (enqueue server, work processes, RFC queues), HANA database metrics, and OS-level metrics. Options include: Azure Monitor for SAP Solutions (AMS), SAP Solution Manager with CCMS, and third-party tools (Dynatrace, Nagios).

**Decision:** Deploy Azure Monitor for SAP Solutions (AMS) as the primary monitoring platform for SAP infrastructure and application monitoring. Retain SAP Solution Manager for ABAP workload management, transport management, and SAP Early Watch Alert reports.

**Rationale:** AMS provides native Azure integration, pre-built dashboards for SAP HANA, ASCS, and application servers, and feeds into Azure Monitor alerts and action groups. AMS does not require additional agents on SAP VMs beyond the standard Azure Monitor Agent. The AMS provider model is extensible and SAP-supported. SAP Solution Manager is retained for application-layer monitoring not available in AMS.

**Chapter References:** Chapter 15 (Operations and Monitoring)
**SAP Notes:** SAP Note 3123386

---

### ADR-0018: Centralised Private DNS Zone Design for SAP Workloads

**Status:** Accepted | **Decision Date:** 2024-03-11 | **Domain:** Networking

**Context:** SAP workloads use multiple hostnames: virtual hostnames for HA (ASCS, HANA primary), physical hostnames for individual VMs, and Azure Private Endpoint hostnames for PaaS services. DNS resolution must be consistent across on-premises and Azure.

**Decision:** Deploy a centralised Private DNS Zone architecture in the hub VNet using Azure Private DNS Resolver. Create SAP-specific Private DNS Zones for SAP virtual hostnames. Link all spoke VNets to the central DNS zones. Configure the on-premises DNS to forward SAP Azure hostnames to the Azure Private DNS Resolver inbound endpoint.

**Rationale:** Centralised DNS management in the hub ensures consistent name resolution across all SAP spokes and from on-premises. The Private DNS Resolver eliminates the need for DNS forwarder VMs and provides SLA-backed availability. Virtual hostnames (separate from physical VM hostnames) are required for SAP HA configurations and must be registered in DNS independently of VM NIC IPs.

**Chapter References:** Chapter 02 (Networking Design), Chapter 07 (High Availability)
**SAP Notes:** SAP Note 962955

---

### ADR-0019: RHEL for SAP Solutions as Preferred OS; SLES as Supported Alternative

**Status:** Accepted | **Decision Date:** 2024-03-18 | **Domain:** Compute

**Context:** SAP HANA and SAP NetWeaver are certified on specific versions of Red Hat Enterprise Linux (RHEL) for SAP Solutions and SUSE Linux Enterprise Server (SLES) for SAP. The programme must define an OS standard.

**Decision:** Standardise on Red Hat Enterprise Linux for SAP Solutions (RHEL for SAP) as the preferred operating system for all SAP workloads on Azure. SUSE Linux Enterprise Server for SAP (SLES for SAP) is supported as an alternative where customer preference or existing licensing dictates. Maintain version standards: RHEL 8.x or 9.x; SLES 15 SP4 or later.

**Rationale:** Both RHEL and SLES are fully supported and SAP-certified on Azure. The preference for RHEL reflects the programme customer's existing Red Hat Enterprise Agreement and internal operations team expertise. Standardising on a single OS reduces operational complexity (patch management, cluster configuration). This ADR is flagged for review if the customer's OS preference changes.

**Chapter References:** Chapter 04 (Compute)
**SAP Notes:** SAP Note 2772999, SAP Note 2235581

---

### ADR-0020: Reserved Instance Commitment Strategy for SAP Compute

**Status:** Accepted | **Decision Date:** 2024-03-18 | **Domain:** Governance

**Context:** SAP production compute (Mv2-series VMs) is predictable and long-running. Azure Reserved Instances (RIs) provide significant cost savings (up to 72% versus pay-as-you-go) in exchange for 1-year or 3-year commitments. The commitment scope and term must be defined.

**Decision:** Purchase 3-year Reserved Instances for all SAP production VMs (HANA, ASCS, application servers) at subscription scope. Purchase 1-year Reserved Instances for SAP non-production VMs. Reserve at the VM family level (Mv2-series) to allow instance size flexibility within the family.

**Rationale:** Production SAP systems are long-running (more than 95% uptime) and do not change VM family frequently. 3-year RIs provide maximum cost savings. Instance size flexibility (selecting the VM family rather than specific size) enables resizing within the Mv2 family without losing RI benefits. Subscription scope (rather than shared scope) ensures RI benefits are applied to SAP workloads first.

**Chapter References:** Chapter 14 (Governance), Chapter 16 (Cost Management)
**SAP Notes:** None directly applicable

---

### ADR-0021: Azure Backup Vault with Cross-Region Restore for SAP VMs

**Status:** Accepted | **Decision Date:** 2024-03-25 | **Domain:** DR

**Context:** VM-level backup (distinct from HANA Backint backup) is required for OS disks, application disks, and point-in-time VM recovery. Cross-Region Restore capability must be evaluated for DR scenarios.

**Decision:** Deploy Azure Backup Recovery Services Vault in each SAP subscription with Cross-Region Restore enabled. Configure VM backup policies for SAP application servers and non-HANA components. HANA database backups use Backint (ADR-0012) as the primary mechanism; VM backup covers the OS and application disk layer.

**Rationale:** Cross-Region Restore allows VM restore into the DR region from the primary region's backup vault without maintaining a separate vault. This reduces DR infrastructure cost and simplifies vault management. Enabling CRR at vault creation is required as it cannot be enabled after the vault is created.

**Chapter References:** Chapter 10 (Backup and Recovery), Chapter 11 (Disaster Recovery)
**SAP Notes:** None directly applicable

---

### ADR-0022: Backup Retention Design: 35-Day Operational plus 7-Year Compliance

**Status:** Accepted | **Decision Date:** 2024-03-25 | **Domain:** DR

**Context:** Backup retention must satisfy both operational recovery requirements (ability to restore to any point in the last month) and compliance requirements (financial data retention regulations requiring multi-year backup preservation).

**Decision:** Configure Azure Backup policies with: (1) daily backup retained for 35 days; (2) weekly backup retained for 52 weeks; (3) monthly backup retained for 12 months; (4) yearly backup retained for 7 years. Store long-term retention (monthly and yearly) in Azure Backup Vault using Archive tier to minimise cost.

**Rationale:** 35-day daily retention covers the standard operational recovery window including month-end close periods. 7-year compliance retention satisfies financial audit requirements. Archive tier for long-term backups reduces storage cost by approximately 75% versus vault-standard tier, with an acceptable 12-hour rehydration delay for compliance restores.

**Chapter References:** Chapter 10 (Backup and Recovery)
**SAP Notes:** None directly applicable

---

### ADR-0023: Azure Firewall Premium over Third-Party NVA for SAP Traffic Inspection

**Status:** Accepted | **Decision Date:** 2024-04-01 | **Domain:** Networking

**Context:** A detailed comparison of Azure Firewall Premium versus third-party Network Virtual Appliances (Palo Alto, Fortinet, Check Point) for SAP traffic inspection. This ADR extends ADR-0004 with explicit NVA comparison rationale.

**Decision:** Confirm Azure Firewall Premium as the traffic inspection solution. Do not deploy third-party NVAs in the hub.

**Detailed Comparison:**

| Criterion | Azure Firewall Premium | Third-Party NVA |
|---|---|---|
| Management overhead | Azure Portal / Firewall Policy | Vendor-specific management plane |
| HA | Built-in zone-redundant | Requires NVA cluster (Active/Active or Active/Standby) |
| Scaling | Automatic (up to 30 Gbps) | Manual scale-out; adds routing complexity |
| Integration with Sentinel | Native connector | Syslog/CEF connector (additional configuration) |
| SAP traffic support | Verified via SAP support channels | Vendor-specific; SAP support scope unclear |
| Cost | Predictable (hourly + data processed) | VM costs + licences + egress |
| IDPS | Built-in Premium feature | Requires separate subscription/module |

**Rationale:** Azure Firewall Premium provides equivalent security capabilities to third-party NVAs for the threat scenarios relevant to the SAP landing zone, without the operational burden of NVA cluster management. The native Azure integration reduces the number of operational tools required.

**Chapter References:** Chapter 02 (Networking Design), Chapter 12 (Security)
**SAP Notes:** None directly applicable

---

### ADR-0024: Pacemaker with Azure Fence Agent for SAP Cluster Fencing

**Status:** Accepted | **Decision Date:** 2024-04-01 | **Domain:** HA

**Context:** SAP HANA and ASCS/ERS HA on Linux requires a cluster manager. Pacemaker is the standard Linux cluster manager used with both RHEL and SLES. The fencing mechanism (STONITH) must be defined: options include the Azure Fence Agent (SBD with Azure API), shared disk SBD, and iSCSI-based SBD.

**Decision:** Implement Pacemaker clusters with the Azure Fence Agent (fence_azure_arm) as the STONITH mechanism. Configure the fence agent with a Managed Identity on each cluster VM to avoid stored credentials.

**Rationale:** The Azure Fence Agent is the Microsoft and SAP recommended STONITH mechanism for Azure-hosted SAP clusters. It uses the Azure VM REST API to force-stop a misbehaving node, eliminating the need for physical IPMI access. Managed Identity authentication removes the credential management burden of service principal secrets. The fence agent is actively maintained by Microsoft and SAP, ensuring compatibility with future OS and kernel updates.

**Chapter References:** Chapter 07 (High Availability)
**SAP Notes:** SAP Note 2694118, SAP Note 1928533

---

### ADR-0025: HANA Scale-Up Architecture as Default; Scale-Out Reserved for BW/4HANA

**Status:** Accepted | **Decision Date:** 2024-04-08 | **Domain:** SAP HANA

**Context:** SAP HANA can be deployed as scale-up (single large VM) or scale-out (multiple VMs with HANA distributed storage). Scale-out enables larger total memory beyond single VM limits but adds architectural complexity.

**Decision:** Deploy SAP HANA in scale-up configuration as the default architecture. Reserve HANA scale-out consideration exclusively for SAP BW/4HANA systems requiring more than 12 TB of memory (beyond Mv2 series maximum).

**Rationale:** HANA scale-up is simpler to operate, provides lower latency (no inter-node HANA data exchange), and is sufficient for S/4HANA systems up to 12 TB. Scale-out introduces complexity in HSR configuration, storage layout (multiple nodes sharing ANF), and HA cluster configuration. The programme's current S/4HANA sizing is within Mv2 scale-up capacity.

**Chapter References:** Chapter 05 (SAP HANA), Chapter 04 (Compute)
**SAP Notes:** SAP Note 2080991, SAP Note 2939585

---

### ADR-0026: Proximity Placement Groups Per Availability Zone for SAP HA Pairs

**Status:** Accepted | **Decision Date:** 2024-04-08 | **Domain:** Compute

**Context:** SAP HA pairs (HANA primary/secondary, ASCS/ERS) are deployed across Availability Zones per ADR-0009. Within each zone, the SAP application servers and database server must have low latency between them. Proximity Placement Groups (PPGs) can pin VMs to the same physical hardware cluster but cannot span zones.

**Decision:** Create one Proximity Placement Group per Availability Zone per SAP system. Anchor each PPG to the Mv2 HANA VM in that zone (as Mv2 VMs have limited placement options). Deploy the application server VMs in the same zone into the corresponding PPG.

**Rationale:** PPGs ensure the application servers and HANA database in the same zone are on the same physical hardware cluster, minimising network latency for HANA client connections. Anchoring PPGs to the HANA VM prevents placement failures caused by the limited datacenter capacity for Mv2 VMs. Cross-zone PPGs are not supported, so each zone requires its own PPG.

**Chapter References:** Chapter 04 (Compute), Chapter 07 (High Availability)
**SAP Notes:** SAP Note 2844316

---

### ADR-0027: Entra ID Conditional Access for SAP Administrative Access

**Status:** Accepted | **Decision Date:** 2024-04-15 | **Domain:** Security

**Context:** SAP administrative access (SAP Basis, OS-level via Bastion, SAP GUI for administration) represents a high-risk access pattern requiring stronger authentication controls than standard Fiori SSO.

**Decision:** Define a dedicated Entra ID Conditional Access policy for SAP administrative access. Require: (1) phishing-resistant MFA (FIDO2 or certificate-based); (2) compliant device; (3) named locations only (corporate network or managed VPN); (4) Privileged Identity Management (PIM) just-in-time activation for SAP_BASIS role before access is permitted. Apply to all users with SAP_BASIS, SAP_HANA_ADMIN, or equivalent roles.

**Rationale:** SAP administrative access provides capability to exfiltrate entire databases, modify financial configurations, and create backdoor users. Standard MFA (SMS/TOTP) is insufficient for this risk level. Phishing-resistant MFA, combined with PIM just-in-time activation, provides a defence-in-depth approach requiring active approval workflow before high-privilege access is granted.

**Chapter References:** Chapter 12 (Security), Chapter 13 (Identity and Access)
**SAP Notes:** SAP Note 2734827

---

### ADR-0028: ANF Cross-Region Replication for HANA Shared and sapmnt DR

**Status:** Accepted | **Decision Date:** 2024-04-15 | **Domain:** DR

**Context:** HANA data replication via HSR (ADR-0013) covers the HANA database. The HANA shared volume and SAP global transport directory also require DR replication as they contain SAP profiles, executables, and transport data not covered by HSR.

**Decision:** Enable Azure NetApp Files Cross-Region Replication (CRR) for all ANF volumes in the primary region that are not covered by HSR: hana-shared, sapmnt, and usr-sap-trans. Configure CRR with daily replication schedule and hourly for sapmnt volumes with active transport activity.

**Rationale:** ANF CRR provides asynchronous volume replication to the DR region at the storage layer, independent of the OS and application. This ensures the DR site has current SAP profiles, kernel binaries, and transport data available at DR failover time. Without ANF CRR, DR recovery would require manual copy of these volumes, extending RTO beyond the 4-hour target.

**Chapter References:** Chapter 06 (Storage), Chapter 11 (Disaster Recovery)
**SAP Notes:** SAP Note 1552925

---

### ADR-0029: Infrastructure as Code Mandate: Bicep Primary, Terraform Secondary

**Status:** Accepted | **Decision Date:** 2024-04-22 | **Domain:** Governance

**Context:** All Azure infrastructure must be deployed via Infrastructure as Code (IaC) to ensure consistency, auditability, and repeatability. The IaC tooling choice must be standardised. Options include: ARM templates, Bicep, Terraform, and Pulumi.

**Decision:** Mandate Infrastructure as Code for all SAP Azure resource deployments. Designate Azure Bicep as the primary IaC language. Terraform (AzureRM provider) is the approved secondary option for teams with existing Terraform expertise or where cross-cloud portability is required. ARM templates are permitted only for resources where Bicep/Terraform support is absent. Manual portal deployments are prohibited for production resources.

**Rationale:** Bicep provides native Azure Resource Manager integration, is first-party supported by Microsoft, eliminates ARM template verbosity, and has strong IDE tooling (VS Code Bicep extension). Bicep modules are available from the Azure Verified Modules library for common patterns including SAP landing zone components. Terraform is retained as a secondary option to preserve team flexibility without mandating a migration of existing Terraform codebases.

**Chapter References:** Chapter 14 (Governance), Chapter 17 (Infrastructure as Code)
**SAP Notes:** None directly applicable

---

### ADR-0030: Azure Bastion Standard as Sole Administrative Access Path for SAP VMs

**Status:** Accepted | **Decision Date:** 2024-04-22 | **Domain:** Security

**Context:** Administrative access to SAP VMs (SSH for Linux OS administration, RDP for Windows jump servers) must be secured. Options include: public IP with NSG, Azure Bastion, site-to-site VPN jump server, and third-party PAM solutions.

**Decision:** Deploy Azure Bastion Standard SKU in the hub VNet as the sole administrative access mechanism for all SAP VMs. Prohibit public IPs on SAP VMs enforced by Azure Policy (ADR-0014). Configure Bastion with native client support enabled for SSH and RDP tunnelling from local clients. Integrate Bastion session recordings with Azure Monitor Logs.

**Rationale:** Azure Bastion eliminates the attack surface of exposed SSH/RDP ports by providing browser-based or native client tunnelled access without public IPs on target VMs. The Standard SKU provides session recording, IP-based connection, and native client support required for SAP GUI connections via RDP to jump servers. NSG-based access control alone is insufficient as it requires public IPs or complex VPN routing for remote administration.

**Chapter References:** Chapter 12 (Security), Chapter 15 (Operations and Monitoring)
**SAP Notes:** None directly applicable

---

## ADRs by Domain

### Landing Zone

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0001 | Hub-Spoke VNet Topology for SAP Landing Zone | Accepted | 2024-01-15 |
| ADR-0002 | Subscription Topology: Production and Non-Production Under SAP Management Group | Accepted | 2024-01-15 |

The Landing Zone ADRs establish the foundational structural decisions for the SAP programme: how subscriptions are organised under the management group hierarchy and how network topology is structured. These decisions are prerequisites for all subsequent domain decisions and are the most difficult to change once the programme is in delivery.

---

### Networking

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0003 | ExpressRoute as Primary Connectivity for SAP to On-Premises | Accepted | 2024-01-22 |
| ADR-0004 | Azure Firewall Premium as Centralised Egress and Inspection Point | Accepted | 2024-01-22 |
| ADR-0005 | Hub-Spoke VNet over Azure Virtual WAN for SAP Landing Zone | Accepted | 2024-01-22 |
| ADR-0018 | Centralised Private DNS Zone Design for SAP Workloads | Accepted | 2024-03-11 |
| ADR-0023 | Azure Firewall Premium over Third-Party NVA for SAP Traffic Inspection | Accepted | 2024-04-01 |

The Networking domain has the largest number of ADRs, reflecting the complexity of SAP connectivity requirements. The five networking ADRs collectively define the connectivity model (ExpressRoute), security inspection approach (Azure Firewall Premium), topology choice (hub-spoke), DNS design (centralised Private DNS Resolver), and NVA comparison rationale.

---

### Compute

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0006 | Mv2-Series VM Family as Primary for SAP HANA Scale-Up | Accepted | 2024-02-05 |
| ADR-0019 | RHEL for SAP Solutions as Preferred OS; SLES as Supported Alternative | Accepted | 2024-03-18 |
| ADR-0026 | Proximity Placement Groups Per Availability Zone for SAP HA Pairs | Accepted | 2024-04-08 |

The Compute domain ADRs define the VM family for HANA (Mv2), the OS standard (RHEL preferred), and the placement optimisation strategy (PPGs per zone). These three decisions together determine the physical compute substrate for all SAP workloads.

---

### Storage

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0007 | Ultra Disk for HANA Log; Azure NetApp Files for HANA Data and Shared | Accepted | 2024-02-05 |
| ADR-0008 | Azure NetApp Files Ultra Performance Tier for SAP HANA | Accepted | 2024-02-05 |

The Storage ADRs define the storage architecture for SAP HANA, the most storage-demanding component. The two ADRs together specify the storage type per HANA volume (Ultra Disk for log, ANF for data and shared) and the ANF performance tier (Ultra).

---

### Security

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0015 | Entra ID SSO (SAML 2.0) for SAP Fiori and Web Dispatcher | Accepted | 2024-03-04 |
| ADR-0016 | Microsoft Sentinel with SAP Solution as Primary SIEM | Accepted | 2024-03-04 |
| ADR-0027 | Entra ID Conditional Access for SAP Administrative Access | Accepted | 2024-04-15 |
| ADR-0030 | Azure Bastion Standard as Sole Administrative Access Path for SAP VMs | Accepted | 2024-04-22 |

The Security domain ADRs address the four primary security layers: user authentication (SSO via SAML 2.0), threat detection (Sentinel), privileged access control (Conditional Access with PIM), and administrative access path (Bastion). Together they implement a zero-trust approach for SAP on Azure.

---

### High Availability

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0009 | Availability Zones over Availability Sets for SAP High Availability | Accepted | 2024-02-12 |
| ADR-0024 | Pacemaker with Azure Fence Agent for SAP Cluster Fencing | Accepted | 2024-04-01 |

The HA domain ADRs establish the zone spreading strategy (AZs over ASets) and the cluster fencing mechanism (Pacemaker with Azure Fence Agent). These decisions underpin the 99.99% availability target for production SAP systems.

---

### Disaster Recovery

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0012 | Azure Backup Backint Agent for HANA; RMAN with Azure Blob for Oracle | Accepted | 2024-02-19 |
| ADR-0013 | Warm Standby DR with HSR ASYNC to Secondary Region | Accepted | 2024-02-19 |
| ADR-0021 | Azure Backup Vault with Cross-Region Restore for SAP VMs | Accepted | 2024-03-25 |
| ADR-0022 | Backup Retention Design: 35-Day Operational plus 7-Year Compliance | Accepted | 2024-03-25 |
| ADR-0028 | ANF Cross-Region Replication for HANA Shared and sapmnt DR | Accepted | 2024-04-15 |

The DR domain is the largest by ADR count, reflecting the complexity of SAP disaster recovery spanning database backup (Backint/RMAN), DR strategy (warm standby), VM backup (Recovery Services Vault with CRR), retention policy (operational and compliance tiers), and shared volume replication (ANF CRR).

---

### Governance

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0014 | Azure Policy Enforce Mode for SAP Landing Zone Controls | Accepted | 2024-03-04 |
| ADR-0020 | Reserved Instance Commitment Strategy for SAP Compute | Accepted | 2024-03-18 |
| ADR-0029 | Infrastructure as Code Mandate: Bicep Primary, Terraform Secondary | Accepted | 2024-04-22 |

The Governance ADRs define how the SAP Azure estate is controlled: policy enforcement posture (Enforce mode), cost optimisation commitment (Reserved Instances), and deployment discipline (IaC mandate). These decisions create the guardrails within which all other architectural decisions operate.

---

### SAP HANA

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0010 | ENSA2 over ENSA1 for ASCS/ERS High Availability | Accepted | 2024-02-12 |
| ADR-0011 | HANA System Replication SYNC Mode for Within-Region HA | Accepted | 2024-02-12 |
| ADR-0025 | HANA Scale-Up Architecture as Default; Scale-Out Reserved for BW/4HANA | Accepted | 2024-04-08 |

The SAP HANA domain ADRs address SAP-specific architectural decisions: ASCS/ERS enqueue architecture (ENSA2), HANA replication mode (SYNC), and HANA deployment model (scale-up default). These decisions require deep SAP product knowledge and are reviewed with SAP support engagement.

---

### Operations

| ADR | Title | Status | Decision Date |
|---|---|---|---|
| ADR-0017 | Azure Monitor for SAP Solutions as Primary Monitoring Platform | Accepted | 2024-03-11 |

The Operations domain currently has one ADR establishing the monitoring platform choice. Additional operations ADRs covering alerting runbooks, patching strategy, and change management are planned for Q3 2024.

---

## Superseded Decisions

### Currently Superseded ADRs

At initial publication of this index (Q2 2024), no ADRs have been superseded. This table will be populated as the architecture evolves.

| Superseded ADR | Title | Superseded By | Supersession Date | Reason |
|---|---|---|---|---|
| — | — | — | — | — |

### Pending Supersession Candidates

The following ADRs are identified as likely candidates for supersession in Q3-Q4 2026 based on technology evolution:

| ADR | Title | Likely Supersession Driver | Target Review Quarter |
|---|---|---|---|
| ADR-0005 | Hub-Spoke VNet over Azure Virtual WAN | Azure Virtual WAN maturation (Bastion in vWAN hub, improved NVA integration) | Q3 2026 |
| ADR-0019 | RHEL for SAP Solutions as Preferred OS | Potential customer OS preference change; SLES market share in SAP environments | Q4 2026 |
| ADR-0006 | Mv2-Series VM Family as Primary for HANA Scale-Up | Msv3/Mdsv3 full TDIv5 certification; Mv2 retirement timeline | Q3 2026 |

---

## ADR Template Reference

All ADRs in this programme use the template located at `adr/templates/adr-template.md`. The template enforces consistent structure across all decision records.

### Required Template Sections

| Section | Purpose | Required |
|---|---|---|
| Title | ADR number and short descriptive title | Yes |
| Status | Current lifecycle state | Yes |
| Decision Date | ISO 8601 date of ARB acceptance | Yes |
| Domain | Primary architectural domain | Yes |
| Context | Problem statement and forces driving the decision | Yes |
| Decision | The decision made, stated clearly | Yes |
| Rationale | Why this decision was made over alternatives | Yes |
| Consequences | Positive and negative consequences of the decision | Yes |
| Alternatives Considered | Other options evaluated with brief assessment | Yes |
| Chapter References | Links to relevant chapters in this documentation | Yes |
| SAP Notes | Applicable SAP Note IDs | Where applicable |
| Related ADRs | Links to ADRs that depend on or influence this ADR | Where applicable |
| Review Date | Date for next scheduled review | Yes |

### File Naming Convention

ADR files must follow the naming convention: `ADR-NNNN-short-title-kebab-case.md`

Examples:
- `ADR-0001-hub-spoke-vnet-topology.md`
- `ADR-0015-entra-id-sso-saml-fiori.md`
- `ADR-0030-azure-bastion-admin-access.md`

### Creating a New ADR

1. Identify the next available ADR number from this index
2. Copy `adr/templates/adr-template.md` to `adr/decisions/ADR-NNNN-title.md`
3. Complete all required sections of the template
4. Set status to `Proposed`
5. Submit a pull request referencing any related chapter documentation PRs
6. Assign the Domain Lead and Security Lead (if applicable) as reviewers
7. Present at the next ARB meeting
8. Upon ARB approval, update status to `Accepted` and add the decision date; update this index

---

## Validation Checklist

### Index Completeness

- [x] All 30 ADRs are listed in the Master ADR Index table
- [x] All 30 ADRs have ADR Detail Summaries entries
- [x] All 30 ADRs appear in their respective domain sections
- [x] ADR count confirmed: 30 total ADRs indexed
- [x] All required topics from programme scope are covered (see Domain Coverage below)
- [x] Superseded ADRs table is present (empty at initial publication)
- [x] Pending Supersession Candidates table is populated

### Process Compliance

- [x] ADR lifecycle states are defined
- [x] Roles and responsibilities are documented
- [x] Decision criteria (when to create an ADR) are documented
- [x] Eight-step review process is documented
- [x] ARB quarterly review cadence is documented
- [x] ADR template reference and file naming convention are documented
- [x] New ADR creation process (8 steps) is documented

### Domain Coverage Verification

| Domain | ADR Count | Topics Covered |
|---|---|---|
| Landing Zone | 2 | Hub-spoke topology, subscription topology |
| Networking | 5 | ExpressRoute, Azure Firewall, hub-spoke vs vWAN, Private DNS, NVA comparison |
| Compute | 3 | VM family (Mv2), OS choice (RHEL/SLES), Proximity Placement Groups |
| Storage | 2 | Storage type per volume (Ultra Disk/ANF), ANF performance tier |
| Security | 4 | SSO (SAML 2.0), SIEM (Sentinel), Conditional Access, Bastion |
| HA | 2 | Availability Zones, Pacemaker fence agent |
| DR | 5 | Backint/RMAN backup, warm standby DR, VM backup vault, retention policy, ANF CRR |
| Governance | 3 | Policy enforce mode, Reserved Instances, IaC mandate |
| SAP HANA | 3 | ENSA2, HSR SYNC mode, scale-up vs scale-out |
| Operations | 1 | Azure Monitor for SAP Solutions |
| **Total** | **30** | **All required programme topics covered** |

---

## Chapter Metadata

| Attribute | Value |
|---|---|
| Chapter | ADR Index |
| Status | Accepted |
| SAP Products | SAP S/4HANA, SAP BW/4HANA, SAP NetWeaver, SAP HANA |
| Azure Services | All Azure services referenced in ADRs above |
| Last Updated | 2024-04-22 |
| Maintained By | Architecture Review Board |
| Related Chapters | All chapters (ADRs cross-reference all domains) |
| Next Scheduled Review | Q3 2024 (quarterly ARB sweep) |
