# Mapa de equivalencia semántica

*Edición en español (México), traducida de la versión inglesa en el commit 062314c. La versión en inglés es la canónica.*

**Versión:** 1.0 (lanzamiento público del kit de inicio)
**Propósito:** Registro compartido de sinónimos que usan todos los módulos. Al calificar, verificar hechos o construir contenido, los términos de un mismo grupo se tratan como semánticamente equivalentes.

**Nota de campo:** Los ejemplos siguientes usan puestos de ciberseguridad; reconstruya las listas para su propio campo. La estructura de grupos, las etiquetas y las reglas de uso son el método; el vocabulario específico es un ejemplo trabajado.

## Cómo usar este mapa
- **Módulos de calificación**: cuentan los sinónimos como la misma palabra clave para la densidad de palabras clave
- **Módulo de verificación de hechos**: reconoce que las paráfrasis de entradas del registro de hechos (my-data/fact_registry.json) se rastrean hasta la misma fuente
- **Módulo de construcción del contenido**: varía deliberadamente la terminología entre viñetas para diversificar verbos y términos sin perder exactitud
- **Etiqueta de solo reconocimiento**: los términos marcados [RECOGNITION-ONLY] (solo reconocimiento) se conservan para que el calificador reconozca la palabra clave de la descripción del puesto (JD), pero NO pueden afirmarse como experiencia propia. La construcción del contenido nunca debe asignárselos a usted como experiencia vivida. Su registro de hechos rige lo que puede afirmarse.
- **Notas de alcance**: donde su relación con un término es real pero limitada (nivel de liderazgo pero no operador práctico, familiaridad pero no pericia, adyacencia pero no propiedad), registre una nota de alcance entre paréntesis junto al término. La construcción del contenido debe respetar ese límite de alcance. Todas las etiquetas o notas de alcance que vea abajo son ejemplos ilustrativos tomados del perfil de una sola persona candidata; vuelva a etiquetar cada entrada contra su propio registro de hechos antes del primer uso.
- **Mantenimiento**: agregue grupos nuevos conforme los encuentre en las JD

---

## Gestión del ciclo de vida de la identidad
- JML = joiner-mover-leaver (ingreso, movimiento, salida)
- Ciclo de vida de la identidad = gestión del ciclo de vida de la identidad = ILM
- Aprovisionamiento / desaprovisionamiento / cambios de rol / baja (offboarding) (todos parte de JML cuando se usan juntos)
- Automatización de RH a directorio = aprovisionamiento desde la fuente de verdad

## Gobernanza de accesos
- IGA = Identity Governance and Administration (gobernanza y administración de identidades)
- Gobernanza de accesos = gestión de derechos de acceso (entitlements)
- Campañas de recertificación = revisiones de acceso = campañas de atestación
- SoD = Segregation of Duties (segregación de funciones) = revisión de combinaciones tóxicas
- Privilegio mínimo = acceso mínimo necesario

## Modelos de control de acceso
- RBAC = Role-Based Access Control (control de acceso basado en roles) = acceso basado en roles
- ABAC = Attribute-Based Access Control (control de acceso basado en atributos) = acceso basado en atributos
- PBAC = Policy-Based Access Control (control de acceso basado en políticas)
- DAC = Discretionary Access Control (control de acceso discrecional)
- MAC = Mandatory Access Control (control de acceso obligatorio)

## Autenticación y federación
- SSO = Single Sign-On (inicio de sesión único)
- MFA = Multi-Factor Authentication (autenticación multifactor) = 2FA cuando se trata del caso de 2 factores
- SAML = Security Assertion Markup Language (lenguaje de marcado para afirmaciones de seguridad)
- OIDC = OpenID Connect
- OAuth 2.0 = OAuth2 (marco de autorización delegada)
- Federación = federación de identidades = autenticación federada
- ADFS = Active Directory Federation Services (servicios de federación de Active Directory)

## Pila de identidad de Microsoft
- Entra ID (servicio de identidad en la nube de Microsoft) = Azure AD = Azure Active Directory (nombres anteriores del mismo servicio; cambio de marca)
- Microsoft Entra ID Governance (gobernanza de identidades de Entra) = AAD Governance = Entra ID Governance
- Conditional Access (acceso condicional, las políticas de acceso de Entra) = Entra Conditional Access = AAD Conditional Access
- AD = Active Directory (servicio de directorio local de Microsoft) = AD local (on-premises)
- Identidad híbrida = AD híbrido = identidad local + identidad en la nube

## Acceso privilegiado
- PAM = Privileged Access Management (gestión de accesos privilegiados)
- PIM = Privileged Identity Management (término de Microsoft)
- JIT = acceso Just-in-Time = acceso con límite de tiempo
- Break-glass = procedimiento de acceso de emergencia = mecanismo de emergencia para acceso privilegiado
- Deriva de privilegios = deriva de accesos privilegiados = acumulación de derechos (entitlement creep) en cuentas privilegiadas

## Zero Trust
- Zero Trust (confianza cero) = ZT = arquitectura de confianza cero (ZTA)
- Seguridad centrada en la identidad = seguridad con la identidad primero
- Verificación continua = autenticación continua
- Asumir la brecha (assume-breach) = diseño assume-breach = postura posterior a la brecha
- Microsegmentación = segmentación de red (en contexto de ZT)
- Privilegio mínimo (también bajo Gobernanza de accesos, arriba)

## Respuesta a incidentes
- IR = Incident Response (respuesta a incidentes)
- DFIR = Digital Forensics and Incident Response (forense digital y respuesta a incidentes)
- SOC = Security Operations Center (centro de operaciones de seguridad)
- CSIRT = Computer Security Incident Response Team (equipo de respuesta a incidentes de seguridad informática)
- Comando de incidentes = función de comando de incidentes = IC
- Ejercicios de mesa (tabletop) = TTX = ejercicio TT = simulacro
- Revisión posterior al incidente = revisión posterior a la acción = AAR = lecciones aprendidas = retrospectiva
- Expulsión del adversario = retoma del control del entorno = remediación y expulsión
- Contención = tiempo para contener
- Follow-the-sun (relevo por husos horarios) = cobertura continua = cobertura de IR 24x7 = cobertura global de incidentes

## Operaciones del SOC y pila de detección y respuesta
Donde tenga una pila real, anote el producto real junto al término (por ejemplo, "SIEM (mi pila: Microsoft Sentinel)", donde Microsoft Sentinel es el SIEM en la nube de Microsoft) para que la construcción del contenido nombre herramientas reales en lugar de adivinar.
- SOC = Security Operations Center = SOC 24x7 = operaciones de seguridad
- SecOps = operaciones de seguridad = operaciones cibernéticas = operaciones de ciberdefensa
- SIEM = Security Information and Event Management (gestión de información y eventos de seguridad)
- SOAR = Security Orchestration, Automation and Response (orquestación, automatización y respuesta de seguridad)
- EDR = Endpoint Detection and Response (detección y respuesta en endpoints)
- XDR = Extended Detection and Response (detección y respuesta extendidas)
- NDR = Network Detection and Response (detección y respuesta de red) [RECOGNITION-ONLY: etiqueta de ejemplo]
- TIP = Threat Intelligence Platform (plataforma de inteligencia de amenazas) [RECOGNITION-ONLY como plataforma con nombre: etiqueta de ejemplo]
- Seguridad del correo = protección contra amenazas en el correo
- Engaño = tecnología de engaño (deception) = honeypots [RECOGNITION-ONLY: etiqueta de ejemplo]
- DLP = Data Loss Prevention (prevención de pérdida de datos) (nota de alcance de ejemplo: nivel de asesoría y gobernanza, no operador)
- Detección como código = pipeline de ingeniería de detección

## Ingeniería de detección
- Threat-Informed Defense (defensa informada por amenazas) = Adversary-Informed Detection Engineering (ingeniería de detección informada por el adversario)
- Ingeniería de cobertura de detección = validación de la cobertura de detección = eficacia de detección
- Ingeniería de telemetría = validación de la calidad de la telemetría = evaluación de la cobertura de logs
- Cobertura de detección alineada a ATT&CK (base de conocimientos de tácticas y técnicas de adversarios, de MITRE) = mapeo de cobertura MITRE ATT&CK

## Inteligencia y cacería de amenazas
- CTI = Cyber Threat Intelligence = inteligencia de amenazas
- Análisis de actores de amenaza = análisis de adversarios = análisis de actores de Estados nación
- IoC = Indicators of Compromise (indicadores de compromiso) = indicadores
- Threat hunting (cacería de amenazas) = cacería proactiva (nota de alcance de ejemplo: nivel de liderazgo y gobernanza, no operador práctico)
- Purple teaming = integración de purple team = integración de red team y blue team
- UEBA = User and Entity Behavior Analytics (analítica de comportamiento de usuarios y entidades)
- Emulación de adversarios = liderazgo de emulación de adversarios

## Red team y pruebas ofensivas
- Célula de confianza del red team = operaciones de célula de confianza
- Liderazgo de emulación de adversarios = liderazgo de pruebas ofensivas
- Integración de purple team
- Pruebas de penetración = pentesting = hallazgos de pentest (límite de alcance de ejemplo: SOLO liderazgo o adyacencia, nunca afirmaciones de ejecución práctica; la construcción del contenido nunca toma el término a secas como práctica vivida; el calificador aún puede contarlo a nivel de reconocimiento)
- BAS = Breach and Attack Simulation (simulación de brechas y ataques) = validación continua de controles [RECOGNITION-ONLY como plataforma con nombre: etiqueta de ejemplo]

## Vulnerabilidades y divulgación
- Gestión de vulnerabilidades = gestión de vulns = ciclo de vida de vulnerabilidades
- Evaluación de aplicabilidad de vulnerabilidades = triaje de aplicabilidad = ¿es explotable aquí?
- Coordinación de remediación = coordinación de parches
- Parcheo a escala = parcheo fuera de banda = parcheo de emergencia = parcheo fuera de los anillos de parches
- Priorización = priorización basada en riesgo
- CVD = Coordinated Vulnerability Disclosure (divulgación coordinada de vulnerabilidades) = divulgación responsable
- Interacción con investigadores de seguridad = coordinación con investigadores = recepción de reportes de vulnerabilidades
- (Registre aquí su propio alcance: por ejemplo, roles de colaboración o coordinación frente a propiedad completa del programa; el límite de alcance controla lo que la construcción del contenido puede afirmar)

## Riesgo interno
- Riesgo interno = amenaza interna = programa de riesgo interno
- Seguridad del personal = riesgo de la fuerza laboral
- Gestión de casos = protocolos de investigación
- Controles de baja = controles de la fase de salida (leaver) = controles de desvinculación
- Estrategia de monitoreo [RECOGNITION-ONLY como propiedad del programa: etiqueta de ejemplo]
- (Registre aquí su propio alcance: coordinar una línea de trabajo y ser dueño del programa son afirmaciones distintas)

## Postura de seguridad y riesgo digital
- Gestión de la postura de seguridad = SPM = gestión continua de la postura
- Gestión de la superficie de ataque = ASM = superficie de ataque externa
- Brechas de control = cobertura de controles = efectividad de controles
- Exposición a amenazas = gestión de la exposición
- Monitoreo de riesgo digital = protección contra riesgo digital = DRP [RECOGNITION-ONLY: etiqueta de ejemplo]
- Protección de marca = monitoreo de suplantación de marca [RECOGNITION-ONLY: etiqueta de ejemplo]
- Monitoreo de la dark web = monitoreo de fuga de credenciales [RECOGNITION-ONLY: etiqueta de ejemplo]

## Colaboración con ejecutivos y clientes
- Colaboración con el CISO adjunto = colaboración con ejecutivos internos de seguridad
- Colaboración con el CISO del cliente = interacción con el CISO del cliente
- Punto de escalamiento a nivel C = punto de escalamiento sénior = punto de escalamiento principal
- Informes de riesgo a ejecutivos = informes aptos para el consejo de administración = reportes al comité de auditoría
- Field CISO (CISO de campo) = asesoría de seguridad de cara al cliente = encargo de aseguramiento de seguridad = shared-fate security (seguridad basada en un destino común)
- Relaciones de confianza entre pares = relaciones entre CISO pares

## Tiempo de ciclo de IR y KPI
- Tiempo de ciclo de respuesta a incidentes = ciclo de resolución de incidentes
- MTTR = Mean Time To Resolve = Mean Time to Resolution = Mean Time to Restore (tiempo medio de resolución o restauración)
- MTTD = Mean Time To Detect (tiempo medio de detección)
- Tiempo para contener = tiempo de contención
- KPI = Key Performance Indicator (indicador clave de desempeño)
- KRI = Key Risk Indicator (indicador clave de riesgo)
- Eficiencia de analistas = productividad de analistas = mejoras obtenidas mediante ajustes y automatización

## Léxico de liderazgo en SecOps
- Director de operaciones de seguridad = liderazgo de operaciones cibernéticas = jefatura de ciberdefensa
- Gobernanza de operaciones del SOC = gobernanza de SecOps
- Cobertura de IR 24x7 = cobertura continua
- Función de comando de incidentes = liderazgo del CSIRT
- Jefatura global de ciberdefensa = líder de seguridad de mayor jerarquía

## Arquitectura de seguridad
- Arquitectura y diseño de seguridad = arquitectura de seguridad empresarial
- Modelado de amenazas = seguridad desde el diseño
- Arquitectura Zero Trust (también bajo Zero Trust)
- Seguridad de red = firewalls = IDS/IPS (nota de alcance de ejemplo: nivel de arquitectura y funcionalidades, no ingeniería de red práctica)
- Protección de endpoints = arquitectura defensiva

## ITSM (gestión de servicios de TI)
- ITSM = IT Service Management (gestión de servicios de TI)
- ITIL = marco ITIL (si no tiene la certificación ITIL, etiquételo para que la construcción del contenido nunca la afirme)
- Gestión de incidentes, gestión de problemas, gestión de cambios = prácticas de ITIL
- SLA = Service Level Agreement (acuerdo de nivel de servicio)
- SLO = Service Level Objective (objetivo de nivel de servicio)
- MTTR = Mean Time To Resolve (o Restore)
- MTTD = Mean Time To Detect
- KPI = Key Performance Indicator
- KRI = Key Risk Indicator

## Riesgo y gobernanza
- CISM = Certified Information Security Manager (si no la tiene, etiquétela para que la construcción del contenido nunca la afirme)
- Gestión de riesgos = marcos de riesgo
- Aceptación de riesgos = decisiones de aceptación de riesgos = gestión de excepciones
- Tratamiento de riesgos = mitigación de riesgos
- Controles internos = marco de control

## Marcos de cumplimiento
Etiquete cada marco con su nivel honesto (afirmar con confianza / familiaridad práctica / exposición limitada / [RECOGNITION-ONLY]). El calificador cuenta todos para determinar las coincidencias de palabras clave; la construcción del contenido solo afirma los que su registro de hechos respalda.
- SOX = Sarbanes-Oxley
- SOC 2 (informe de controles de organizaciones de servicios) = SOC 2 Type I / Type II
- ISO 27001 = ISO/IEC 27001 (norma internacional de gestión de la seguridad de la información)
- NIST = NIST CSF (marco de ciberseguridad del NIST) = NIST Cybersecurity Framework
- NIST 800-61 = NIST SP 800-61 (publicación especial del NIST sobre manejo de incidentes) = ciclo de vida de la respuesta a incidentes
- NIST 800-53, 800-171 = controles NIST (catálogos específicos)
- PCI = PCI DSS (estándar de seguridad de datos de la industria de tarjetas de pago) = Payment Card Industry
- GDPR = General Data Protection Regulation (Reglamento General de Protección de Datos)
- HIPAA = Health Insurance Portability and Accountability Act
- HITRUST = HITRUST CSF (marco de seguridad común de HITRUST)
- FFIEC = Federal Financial Institutions Examination Council
- NYDFS = NY Department of Financial Services Part 500
- NAIC = National Association of Insurance Commissioners
- NERC/CIP (estándares del sector eléctrico norteamericano) = protección de infraestructura crítica
- GxP = Good Practice (buenas prácticas; regulaciones de calidad farmacéutica)
- CSV = Computer System Validation (validación de sistemas computarizados, farmacéutica)
- 21 CFR Part 11 = registros y firmas electrónicos de la FDA
- EU Annex 11 (anexo europeo sobre sistemas computarizados) = sistemas computarizados (GMP de la UE)
- DoD 8500 = serie DoD Instruction 8500
- CNSSI = Committee on National Security Systems Instructions
- NISPOM = National Industrial Security Program Operating Manual
- NIST RMF = NIST Risk Management Framework (marco de gestión de riesgos del NIST)
- CMMC = Cybersecurity Maturity Model Certification (certificación de madurez en ciberseguridad del Departamento de Defensa de EE. UU.)
- FIPS = Federal Information Processing Standards (comúnmente FIPS 140-2/140-3)
- FedRAMP = Federal Risk and Authorization Management Program (programa federal de gestión de riesgos y autorizaciones; ejemplo de límite de precisión: "familiaridad operativa con entornos FedRAMP" es una afirmación distinta y más pequeña que ser dueño de la ATO/autorización, autor del SSP/POA&M o hacer trabajo de 3PAO; escriba el límite en su nota de alcance y nunca deje que la construcción del contenido lo cruce)
- DORA = Digital Operational Resilience Act (ley de resiliencia operativa digital; regulación del sector financiero de la UE)

## Industria regulada y foros gubernamentales
- Industria regulada = encargos en industrias reguladas
- Servicios financieros regulados = servicios financieros
- Salud = regulado por HIPAA = sector salud regulado
- Sector público = federal = gobierno
- ISAC = Information Sharing and Analysis Center [RECOGNITION-ONLY: a menos que sea miembro]
- InfraGard = FBI InfraGard [RECOGNITION-ONLY: a menos que sea miembro]
- CISA = Cybersecurity and Infrastructure Security Agency
- FBI = Federal Bureau of Investigation
- USSS = US Secret Service
- DHS = Department of Homeland Security
- Enlace con fuerzas del orden = coordinación con LE (si hubo interacción durante incidentes, mantenga la afirmación genérica en papel)

## Gestión de programas y proyectos
- TPM = Technical Program Manager (gerente técnico de programa)
- PM = Program Manager (o Project Manager, según el contexto)
- Iniciativa multifuncional = programa entre equipos = esfuerzo con múltiples partes interesadas
- Gestión de partes interesadas = interacción con ejecutivos = influencia entre organizaciones
- Gestión de líneas de trabajo = coordinación de líneas de trabajo (nota de alcance de ejemplo: gestionar líneas de trabajo y construir el programa desde cero son afirmaciones distintas)

## M&A
- M&A = Mergers and Acquisitions (fusiones y adquisiciones)
- Integración = integración de M&A = integración posterior a la adquisición
- Migración de tenant a tenant = migración entre tenants = T2T
- Consolidación de directorios = consolidación de AD

## Automatización
- IaC = Infrastructure as Code (infraestructura como código)
- PowerShell, Python, REST, API = herramientas de automatización
- Basado en eventos = orientado a eventos = pub/sub cuando aplique
- Autoservicio = desvío de tickets (cuando el resultado es automatización)

## IA / GenAI
- GenAI = IA generativa = asistido por LLM
- Agentes de IA = agentes autónomos = IA agéntica
- RAG = Retrieval-Augmented Generation (generación aumentada por recuperación)
- Restricciones por rol = guardrails (barreras de seguridad) = acción acotada

---

## Cómo agregar entradas nuevas
Cuando encuentre un sinónimo que no está en este mapa:
1. Agréguelo al grupo apropiado, o cree un grupo nuevo si ninguno encaja
2. Anote la adición en sus notas de sesión (my-data/)
3. Actualice la versión y la fecha de última actualización
4. Si un término es una palabra clave de la JD que usted no puede afirmar, agréguelo con la etiqueta [RECOGNITION-ONLY] para que el calificador lo vea pero la construcción del contenido nunca se lo asigne
