# Semantic Equivalence Map

**Version:** 1.0 (public starter kit release)
**Purpose:** Shared synonym registry used by all modules. When scoring, fact-checking, or building content, terms in the same group are treated as semantically equivalent.

**Field note:** Examples below use cybersecurity roles; rebuild the lists for your own field. The group structure, tags, and usage rules are the method - the specific vocabulary is a worked example.

## How to use this
- **Scoring modules**: count synonyms toward the same keyword for keyword density
- **Fact-check module**: recognize that paraphrases of fact registry entries (my-data/fact_registry.json) trace to the same source
- **Content build module**: deliberately vary terminology across bullets for verb/term diversity while remaining accurate
- **Recognition-only tag**: terms marked [RECOGNITION-ONLY] are kept so the scorer recognizes the JD keyword, but they are NOT claimable as your own experience. Content build must never assign them to you as lived experience. Your fact registry governs what is claimable.
- **Scope notes**: where your relationship to a term is real but limited (leadership level but not hands-on operator, familiarity but not expertise, adjacency but not ownership), record a scope note in parentheses next to the term. Content build must respect that fence. Any tags or scope notes you see below are illustrative examples from one candidate profile - re-tag every entry against your own fact registry before first use.
- **Maintenance**: add new groups as you encounter them in JDs

---

## Identity Lifecycle Management
- JML = joiner-mover-leaver
- Identity lifecycle = identity lifecycle management = ILM
- Provisioning / deprovisioning / role changes / offboarding (all part of JML when used together)
- HR-to-directory automation = source-of-truth provisioning

## Access Governance
- IGA = Identity Governance and Administration
- Access governance = entitlement management
- Recertification campaigns = access reviews = attestation campaigns
- SoD = Segregation of Duties = toxic combination review
- Least privilege = minimum necessary access

## Access Control Models
- RBAC = Role-Based Access Control = role-based access
- ABAC = Attribute-Based Access Control = attribute-based access
- PBAC = Policy-Based Access Control
- DAC = Discretionary Access Control
- MAC = Mandatory Access Control

## Authentication & Federation
- SSO = Single Sign-On
- MFA = Multi-Factor Authentication = 2FA when in the 2-factor case
- SAML = Security Assertion Markup Language
- OIDC = OpenID Connect
- OAuth 2.0 = OAuth2
- Federation = identity federation = federated authentication
- ADFS = Active Directory Federation Services

## Microsoft Identity Stack
- Entra ID = Azure AD = Azure Active Directory (rebrand)
- Microsoft Entra ID Governance = AAD Governance = Entra ID Governance
- Conditional Access = Entra Conditional Access = AAD Conditional Access
- AD = Active Directory = on-premises AD
- Hybrid identity = hybrid AD = on-prem + cloud identity

## Privileged Access
- PAM = Privileged Access Management
- PIM = Privileged Identity Management (Microsoft term)
- JIT = Just-in-Time access = time-bound access
- Break-glass = emergency access procedure = privileged escape valve
- Privileged drift = privileged access drift = entitlement creep on privileged accounts

## Zero Trust
- Zero Trust = ZT = zero-trust architecture (ZTA)
- Identity-centric security = identity-first security
- Continuous verification = continuous authentication
- Assume-breach = assume-breach design = post-breach posture
- Micro-segmentation = network segmentation (when in ZT context)
- Least privilege (also under Access Governance above)

## Incident Response
- IR = Incident Response
- DFIR = Digital Forensics and Incident Response
- SOC = Security Operations Center
- CSIRT = Computer Security Incident Response Team
- Incident command = incident command function = IC
- Tabletop exercises = TTX = TT exercise = simulation drill
- Post-incident review = after-action review = AAR = lessons-learned = retrospective
- Adversary eviction = environment take-back = remediation and eviction
- Containment = time-to-contain
- Follow-the-sun = around-the-clock coverage = 24x7 IR coverage = global incident coverage

## SOC Operations and Detection/Response Stack
Where you have a real stack, note the actual product next to the term (e.g., "SIEM (my stack: Microsoft Sentinel)") so content build names real tools instead of guessing.
- SOC = Security Operations Center = 24x7 SOC = security operations
- SecOps = security operations = cyber operations = cyber defense operations
- SIEM = Security Information and Event Management
- SOAR = Security Orchestration, Automation and Response
- EDR = Endpoint Detection and Response
- XDR = Extended Detection and Response
- NDR = Network Detection and Response [RECOGNITION-ONLY - example tag]
- TIP = Threat Intelligence Platform [RECOGNITION-ONLY as a named platform - example tag]
- Email security = email threat protection
- Deception = deception technology = honeypots [RECOGNITION-ONLY - example tag]
- DLP = Data Loss Prevention (example scope note: advisory / governance level, not operator)
- Detection-as-code = detection engineering pipeline

## Detection Engineering
- Threat-Informed Defense = Adversary-Informed Detection Engineering
- Detection coverage engineering = detection coverage validation = detection efficacy
- Telemetry engineering = telemetry quality validation = log coverage assessment
- ATT&CK-aligned detection coverage = MITRE ATT&CK coverage mapping

## Threat Intelligence and Hunting
- CTI = Cyber Threat Intelligence = threat intelligence
- Threat actor analysis = adversary analysis = nation-state actor analysis
- IoC = Indicators of Compromise = indicators
- Threat hunting = proactive hunting (example scope note: leadership and governance level, not hands-on operator)
- Purple teaming = purple team integration = red and blue integration
- UEBA = User and Entity Behavior Analytics
- Adversary emulation = adversary emulation leadership

## Red Team and Offensive Testing
- Red team trusted cell = trusted cell operations
- Adversary emulation leadership = offensive testing leadership
- Purple team integration
- Penetration testing = pen testing = pen test findings (example scope fence: leadership/adjacency ONLY - never hands-on performance claims; content build never pulls the bare token as lived practice; the scorer may still count it at recognition level)
- BAS = Breach and Attack Simulation = continuous control validation [RECOGNITION-ONLY as a named platform - example tag]

## Vulnerability and Disclosure
- Vulnerability management = vuln management = vulnerability lifecycle
- Vulnerability applicability assessment = applicability triage = is-it-exploitable-here
- Remediation coordination = patch coordination
- Patching at scale = out-of-band patching = emergency patching = patching outside the patch rings
- Prioritization = risk-based prioritization
- CVD = Coordinated Vulnerability Disclosure = responsible disclosure
- Security researcher engagement = researcher coordination = vulnerability intake
- (Record your own scope here: e.g., partnership or coordination roles vs full program ownership - the fence controls what content build may claim)

## Insider Risk
- Insider risk = insider threat = insider risk program
- Personnel security = workforce risk
- Case management = investigation protocols
- Offboarding controls = Leaver-phase controls = departure controls
- Monitoring strategy [RECOGNITION-ONLY as program ownership - example tag]
- (Record your own scope here: workstream coordination vs program ownership are different claims)

## Security Posture and Digital Risk
- Security Posture Management = SPM = continuous posture management
- Attack surface management = ASM = external attack surface
- Control gaps = control coverage = control effectiveness
- Threat exposure = exposure management
- Digital Risk Monitoring = digital risk protection = DRP [RECOGNITION-ONLY - example tag]
- Brand protection = brand impersonation monitoring [RECOGNITION-ONLY - example tag]
- Dark web monitoring = credential leakage monitoring [RECOGNITION-ONLY - example tag]

## Executive and Client Partnership
- Deputy CISO partnership = internal executive security partnership
- Customer CISO partnership = client CISO engagement
- C-level escalation point = senior escalation point = primary escalation point
- Executive risk briefings = Board-quality reporting = Audit Committee reporting
- Field CISO = client-facing security advisory = security assurance engagement = shared-fate security
- Trusted peer relationships = peer CISO relationships

## IR Cycle Time and KPIs
- Incident response cycle time = incident resolution cycle
- MTTR = Mean Time To Resolve = Mean Time to Resolution = Mean Time to Restore
- MTTD = Mean Time To Detect
- Time-to-contain = containment time
- KPI = Key Performance Indicator
- KRI = Key Risk Indicator
- Analyst efficiency = analyst productivity = tuning and automation gains

## SecOps Leadership Lexicon
- Security operations director = cyber operations leadership = head of cyber defense
- SOC operations governance = SecOps governance
- 24x7 IR coverage = around-the-clock coverage
- Incident command function = CSIRT leadership
- Global head of cyber defense = senior-most security leader

## Security Architecture
- Security architecture and design = enterprise security architecture
- Threat modeling = secure by design
- Zero Trust architecture (also under Zero Trust)
- Network security = firewalls = IDS/IPS (example scope note: architecture and feature level, not hands-on network engineering)
- Endpoint protection = defensive architecture

## ITSM (IT Service Management)
- ITSM = IT Service Management
- ITIL = ITIL framework (if you do not hold the ITIL certification, tag it so content build never claims it)
- Incident management, problem management, change management = ITIL practices
- SLA = Service Level Agreement
- SLO = Service Level Objective
- MTTR = Mean Time To Resolve (or Restore)
- MTTD = Mean Time To Detect
- KPI = Key Performance Indicator
- KRI = Key Risk Indicator

## Risk & Governance
- CISM = Certified Information Security Manager (if you do not hold it, tag it so content build never claims it)
- Risk management = risk frameworks
- Risk acceptance = risk acceptance decisions = exception management
- Risk treatment = risk mitigation
- Internal controls = control framework

## Compliance Frameworks
Tag each framework with your honest level (claim confidently / working familiarity / limited exposure / [RECOGNITION-ONLY]). The scorer counts all of them toward keyword matches; content build only claims the ones your fact registry supports.
- SOX = Sarbanes-Oxley
- SOC 2 = SOC 2 Type I / Type II
- ISO 27001 = ISO/IEC 27001
- NIST = NIST CSF = NIST Cybersecurity Framework
- NIST 800-61 = NIST SP 800-61 = incident response lifecycle
- NIST 800-53, 800-171 = NIST controls (specific catalogs)
- PCI = PCI DSS = Payment Card Industry
- GDPR = General Data Protection Regulation
- HIPAA = Health Insurance Portability and Accountability Act
- HITRUST = HITRUST CSF
- FFIEC = Federal Financial Institutions Examination Council
- NYDFS = NY Department of Financial Services Part 500
- NAIC = National Association of Insurance Commissioners
- NERC/CIP = critical infrastructure protection
- GxP = Good Practice (pharma quality regulations)
- CSV = Computer System Validation (pharma)
- 21 CFR Part 11 = FDA electronic records/signatures
- EU Annex 11 = computerised systems (EU GMP)
- DoD 8500 = DoD Instruction 8500 series
- CNSSI = Committee on National Security Systems Instructions
- NISPOM = National Industrial Security Program Operating Manual
- NIST RMF = NIST Risk Management Framework
- CMMC = Cybersecurity Maturity Model Certification
- FIPS = Federal Information Processing Standards (FIPS 140-2/140-3 commonly)
- FedRAMP = Federal Risk and Authorization Management Program (example of a precision fence: "operating familiarity with FedRAMP environments" is a different, smaller claim than ATO/authorization ownership, SSP/POA&M authorship, or 3PAO work - write the fence into your scope note and never let content build cross it)
- DORA = Digital Operational Resilience Act (EU financial-sector regulation)

## Regulated Industry and Government Forums
- Regulated industry = regulated-industry engagements
- Financial services regulated = financial services
- Healthcare = HIPAA-regulated = healthcare regulated
- Public sector = federal = government
- ISAC = Information Sharing and Analysis Center [RECOGNITION-ONLY unless you are a member]
- InfraGard = FBI InfraGard [RECOGNITION-ONLY unless you are a member]
- CISA = Cybersecurity and Infrastructure Security Agency
- FBI = Federal Bureau of Investigation
- USSS = US Secret Service
- DHS = Department of Homeland Security
- Law enforcement liaison = LE coordination (if engaged during incidents, keep the claim generic on paper)

## Program & Project Management
- TPM = Technical Program Manager
- PM = Program Manager (or Project Manager - context-dependent)
- Cross-functional initiative = cross-team program = multi-stakeholder effort
- Stakeholder management = executive engagement = cross-org influence
- Workstream management = workstream coordination (example scope note: managed workstreams vs built the program from the start are different claims)

## M&A
- M&A = Mergers and Acquisitions
- Integration = M&A integration = post-acquisition integration
- Tenant-to-tenant migration = cross-tenant migration = T2T
- Directory consolidation = AD consolidation

## Automation
- IaC = Infrastructure as Code
- PowerShell, Python, REST, API = automation tooling
- Event-driven = event-based = pub/sub when relevant
- Self-service = ticket deflection (when the outcome is automation)

## AI / GenAI
- GenAI = Generative AI = LLM-assisted
- AI agents = autonomous agents = agentic AI
- RAG = Retrieval-Augmented Generation
- Role-based constraints = guardrails = bounded action

---

## Adding new entries
When you encounter a synonym not in this map:
1. Add to the appropriate group, or create a new group if none fits
2. Note the new addition in your session notes (my-data/)
3. Update version + last updated date
4. If a term is a JD keyword you cannot claim, add it with the [RECOGNITION-ONLY] tag so the scorer sees it but content build never assigns it to you
