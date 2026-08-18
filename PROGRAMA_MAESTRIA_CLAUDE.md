# MAESTRÍA INTENSIVA: SKILLS, AGENTES Y PROYECTOS EN CLAUDE
**12 semanas | 2 hrs/día | 168 horas totales**

---

## FILOSOFÍA PEDAGÓGICA

### Principios rectores
1. **Aprendizaje por construcción**: No explicaciones teóricas aisladas. Cada concepto se aprende construyendo algo funcional.
2. **Escalado progresivo**: De skills simples → skills complejos → agentes de 1 nivel → agentes multinivel → proyectos distribuidos.
3. **Retroalimentación inmediata**: Cada sesión produce un artefacto evaluable (código, skill, prompt, o agente funcionando).
4. **Reutilización y mejora**: Los días pares, optimizas lo que construiste el día impar.
5. **Síntesis ejecutiva**: Documentas cada semana en formato decisional (como tu skill comunicacion-ejecutiva).

---

## ESTRUCTURA: 4 FASES

### FASE 1: DOMINIO DE SKILLS (Semanas 1-3 | 42 horas)
**Objetivo**: Pasar de "crear skills funcionales" a "diseñar skills para arquitecturas complejas"

#### Semana 1: Fundamentos avanzados de skills
- **Día 1-2**: Arquitectura interna de skills
  - Estructura YAML/JSON: metadata, triggers, instructions, constraints
  - Cómo Claude decide cuándo usar un skill
  - Diferencia: skill vs. prompt system vs. MCP server
  - *Construcción*: Audita tu skill comunicacion-ejecutiva. ¿Qué triggers son implícitos? ¿Cómo mejorar la detección?

- **Día 3-4**: Diseño de triggers efectivos
  - Triggers por palabra clave, patrón, contexto, usuario
  - Anti-patrones: triggers demasiado amplios, demasiado restrictivos
  - *Construcción*: Crea 3 versiones de triggers para un skill "análisis-financiero". Prueba cuál converge mejor.

- **Día 5-6**: Constraints y safety en skills
  - Cómo especificar límites éticos, de dominio, de formato
  - Cascada de constraints: global → skill → prompt
  - *Construcción*: Diseña constraints para un skill "legal-advice" para México. Documenta qué casos rechaza y por qué.

- **Día 7-8**: Integración de skills con Projects
  - Cómo un Project configura y apila múltiples skills
  - Orden de aplicación, prioridad, conflictos
  - *Construcción*: En Claude Projects, configura tu skill comunicacion-ejecutiva + uno nuevo "análisis-kpis". Prueba la sinergia.

- **Día 9-10**: Evaluación y optimización
  - Métricas de skill: precisión de triggers, relevancia de salida, tiempo de respuesta
  - A/B testing de instrucciones
  - *Construcción*: Ejecuta 20 prompts contra tu skill financiero. Mide qué % de casos usa el skill. Itera.

#### Semana 2: Skills para casos de uso empresariales
- **Día 1-2**: Skills de transformación (Datos → Insights)
  - Inputs: CSV, JSON, SQL query results
  - Outputs: Resumen ejecutivo, gráficos, recomendaciones
  - *Construcción*: Crea skill "sql-to-executive-summary" basado en tu experiencia CECO/Vertica

- **Día 3-4**: Skills de validación y compliance
  - Cómo un skill verifica reglas de negocio (CNBV, normativas)
  - Outputs: Reportes de conformidad, alertas, acciones correctivas
  - *Construcción*: Skill para auditoría de gastos (costo, justificación, categoría) con reglas mexicanas

- **Día 5-6**: Skills con estado y memoria
  - Cómo mantener contexto entre llamadas al skill
  - Patrones: sesión, usuario, proyecto
  - *Construcción*: Skill "presupuesto-anual" que recuerda decisiones previas, acumula gasto, proyecta

- **Día 7-8**: Skills que llaman otros skills (composición)
  - Skill A invoca Skill B en su pipeline
  - Manejo de cascadas, errores, timeouts
  - *Construcción*: Skill "propuesta-financiera-kia" que internamente llama "comparador-leasing", "calculador-cuotas", "evaluador-riesgo"

- **Día 9-10**: Documentación y versionado de skills
  - CHANGELOG, breaking changes, migration guide
  - Versionado semántico para skills (1.0.0, 1.1.0, 2.0.0)
  - *Construcción*: Documenta tu skill comunicacion-ejecutiva en formato changelog. Prepara v2.0 con mejoras.

#### Semana 3: Patterns avanzados y anti-patrones
- **Día 1-2**: Skill como proxy hacia herramientas externas
  - Skill que orquesta: API call → Parse → Format → User
  - Error handling, timeouts, fallbacks
  - *Construcción*: Skill que llama API de CNBV (o simula) para validar institución financiera

- **Día 3-4**: Skills para generación de código
  - Skill que produce Python/SQL/JS ejecutable
  - QA: ¿El código funciona? ¿Es seguro? ¿Es eficiente?
  - *Construcción*: Skill "python-analytics-generator" que crea scripts para análisis de datos

- **Día 5-6**: Debugging de skills que no se usan
  - Por qué un skill bien diseñado no se dispara
  - Técnicas para mejorar la "discoverability"
  - *Construcción*: Toma un skill que rara vez usas. Rediseña triggers y test.

- **Día 7-8**: Métricas de éxito de skills
  - Precisión, recall, F1 score
  - Usuarios afectados, ROI (tiempo ahorrado)
  - Feedback loops para mejora continua
  - *Construcción*: Crea dashboard mental (tabla) con KPIs de tus 3 skills principales

- **Día 9-10**: Proyecto integrador Fase 1
  - **Entregable**: Suite de 3 skills empresariales completamente documentados, versionados y testeados
  - Incluye: Skill A (independiente) + Skill B (independiente) + Skill C (compone A+B)
  - Cada skill tiene: documentación, changelog, 10+ test cases, métricas

---

### FASE 2: AGENTES DE NIVEL ÚNICO (Semanas 4-6 | 42 horas)
**Objetivo**: Entender cómo un agente orquesta skills, herramientas y decisiones

#### Semana 4: Arquitectura de agentes autónomos
- **Día 1-2**: Qué es un agente vs. un skill vs. un LLM
  - Loop: Percepción → Reasoning → Acción
  - Diferencia: determinístico vs. no determinístico
  - *Construcción*: Diagrama de flujo (decisión) de un agente "propuesta-crediticia"

- **Día 3-4**: Diseño de herramientas (tools) para agentes
  - Tipos: compute, retrieve, validate, transform
  - Interfaz: inputs, outputs, constraints
  - *Construcción*: Define 5 herramientas atómicas que necesitaría tu agente crediticio

- **Día 5-6**: Prompts de agentes: system prompt como director
  - Cómo instruir a Claude para que actúe como agente autónomo
  - Roles, responsabilidades, límites de autoridad
  - *Construcción*: Escribe system prompt para agente "gestor-gastos" que automáticamente categoriza, valida, reporta

- **Día 7-8**: Loop de reasoning: Chain-of-Thought para agentes
  - Cómo el agente explica su razonamiento
  - Técnicas: step-by-step, tree-of-thought, reflection
  - *Construcción*: Agente que decide si aprobar un gasto >$5k explicitando criterios

- **Día 9-10**: Evaluación y testing de agentes
  - Casos de prueba: éxito esperado vs. real
  - Fallos graceful: qué pasa si el agente no puede decidir
  - *Construcción*: Test suite de 20 casos para tu agente crediticio

#### Semana 5: Agentes para procesos empresariales
- **Día 1-2**: Agente de análisis de datos
  - Input: Dataset desordenado
  - Output: Insights, visualizaciones, recomendaciones
  - *Construcción*: Agente que toma CSV de gastos CECO/Vertica y produce reportes automáticamente

- **Día 3-4**: Agente de toma de decisiones
  - Integración de múltiples criterios (costo, riesgo, tiempo, estrategia)
  - Output: Recomendación + justificación
  - *Construcción*: Agente para evaluar opciones de financing (Kia vs. Toyota)

- **Día 5-6**: Agente de validación y compliance
  - Verifica reglas complejas contra datos
  - Genera reportes de violaciones, mitigaciones
  - *Construcción*: Agente CNBV que valida propuestas crediticias contra normativa

- **Día 7-8**: Agente como interfaz conversacional
  - Usuario → Agente → Decisión + Explicación
  - Multi-turn, preservando contexto
  - *Construcción*: Chatbot "asesor-financiero" que dialoga y asesora sobre opciones de compra

- **Día 9-10**: Integración agente + skills
  - El agente usa tus skills de Fase 1 como herramientas
  - Sinergia: cuándo delegar al skill vs. razonar internamente
  - *Construcción*: Agente "propuesta-crediticia" que usa skills: "validador-cnbv", "calculador-cuotas", "comunicacion-ejecutiva"

#### Semana 6: Agentes con memoria y persistencia
- **Día 1-2**: Tipos de memoria en agentes
  - Sesión (multi-turn dentro de un chat)
  - Usuario (histórico entre sesiones)
  - Contexto (documentos, knowledge bases)
  - *Construcción*: Diseña memoria para agente "gestor-presupuesto-anual"

- **Día 3-4**: Implementación de memoria
  - Dónde guardar (base de datos, archivos, vector DB)
  - Cómo indexar y retrieval
  - *Construcción*: Agente que recuerda decisiones previas del usuario y ajusta recomendaciones

- **Día 5-6**: Agentes con aprendizaje
  - Feedback del usuario → mejora de future decisions
  - Patterns: "el usuario siempre elige opción X cuando hay riesgo"
  - *Construcción*: Agente que trackea decisiones tuyas y predice preferencias

- **Día 7-8**: Fallback y recovery en agentes
  - Qué pasa si herramienta falla, API está down, etc.
  - Estrategias: retry, degradación, escalación a humano
  - *Construcción*: Agente con 3 niveles de fallback (automático → asistencia → humano)

- **Día 9-10**: Proyecto integrador Fase 2
  - **Entregable**: Agente empresarial completamente funcional
  - Usa 3+ skills de Fase 1
  - Tiene memoria (sesión + usuario)
  - Incluye: especificación, system prompt, herramientas, test suite (30+ casos)
  - Tema sugerido: "Gestor de propuestas crediticias" o "Asesor de inversiones"

---

### FASE 3: AGENTES MULTINIVEL Y ORQUESTACIÓN (Semanas 7-9 | 42 horas)
**Objetivo**: Arquitecturas donde agentes coordinan otros agentes

#### Semana 7: Patrones de agentes multinivel
- **Día 1-2**: Supervisor vs. Workers
  - Agente supervisor recibe solicitud, delega a workers especializados
  - Cada worker es agente autónomo con su dominio
  - *Construcción*: Diseña arquitectura para sistema de propuestas crediticias
    - Supervisor: ruteador inicial
    - Worker 1: Validador CNBV
    - Worker 2: Analista de riesgo
    - Worker 3: Calculador financiero

- **Día 3-4**: Implementación de supervisor
  - Cómo el supervisor decide qué worker llamar
  - Manejo de resultados parciales, conflictos
  - *Construcción*: Supervisor que evalúa solicitud y rutea a 1+ workers

- **Día 5-6**: Coordinación entre workers
  - Workers que se comunican, comparten contexto
  - Sincronización: todos deben terminar antes de siguiente fase
  - *Construcción*: 3 workers que colaboran en paralelo, luego síntesis

- **Día 7-8**: Recursión de agentes
  - Un agente llama agentes similares (sub-problemas)
  - Casos: divide-and-conquer, tree search
  - *Construcción*: Agente que descompone "evaluar propuesta crediticia" en sub-evaluaciones

- **Día 9-10**: Evaluación de sistemas multinivel
  - Performance: latencia, throughput, error rates
  - Debugging: dónde falla la orquestación
  - *Construcción*: Stress test de tu sistema: 10 propuestas simultáneas

#### Semana 8: Proyectos complejos con agentes
- **Día 1-2**: Ciclo de vida de proyecto en Claude
  - Knowledge base (documents)
  - Skills (herramientas)
  - Agentes (workers)
  - System prompt (coordinador)
  - *Construcción*: Estructura proyecto "Evaluación de Altara Crédito Digital" (cosa que estás haciendo!)

- **Día 3-4**: Gestión de contexto en proyectos
  - Qué información llega a qué agente
  - Privacy: qué información NO debe ver cierto agente
  - *Construcción*: Define flujo de información para tu proyecto Altara

- **Día 5-6**: Agentes especializados en dominio
  - Agente que entiende profundamente un dominio (ej: finanzas, legal, tech)
  - Acceso a knowledge base del dominio
  - *Construcción*: Agente "experto-crédito-digital" que conoce propuestas y tendencias

- **Día 7-8**: Integración con herramientas externas
  - Agentes que conectan con: APIs, bases de datos, archivos
  - MCP servers como "conexión" hacia sistemas externos
  - *Construcción*: Agente que retrieval datos de una API (real o simulada)

- **Día 9-10**: Proyecto integrador Fase 3
  - **Entregable**: Sistema completo de 2+ niveles de agentes
  - Incluye: Supervisor + 3-4 Workers + Skills + Memory
  - Documentación de arquitectura (diagrama, flujos, decisiones)
  - Test suite exhaustivo (50+ casos)
  - Metrics dashboard
  - Tema sugerido: Sistema de aprobación de gastos multi-nivel (CECO)

#### Semana 9: Escalado y production-readiness
- **Día 1-2**: Observability en agentes
  - Logging de decisiones, calls, resultados
  - Tracing: seguir una solicitud a través de múltiples agentes
  - *Construcción*: Implementa logging completo en tu sistema Fase 3

- **Día 3-4**: Performance y optimización
  - Identificar cuellos de botella
  - Paralelización de workers
  - Caching de resultados
  - *Construcción*: Profile tu sistema. Optimiza 2-3 queries lentas.

- **Día 5-6**: Manejo de errores en cascada
  - Qué pasa si supervisor falla, workers fallan, skill falla
  - Resiliencia: recuperación automática
  - *Construcción*: Diseña error handling strategy para Fase 3

- **Día 7-8**: Versionado de sistemas de agentes
  - Cómo hacer cambios sin romper usuarios
  - A/B testing: nueva versión de agente vs. vieja
  - *Construcción*: Prepara migration path de v1.0 → v2.0 de tu sistema

- **Día 9-10**: Documentación para deployment
  - Architecture Decision Records (ADR)
  - Runbook: cómo deployar, rollback, debug
  - *Construcción*: Crea documentación completa para que alguien más pueda mantener tu sistema

---

### FASE 4: MAESTRÍA Y ESPECIALIZACIÓN (Semanas 10-12 | 42 horas)
**Objetivo**: Expertise nivel profesional en arquitecturas Claude complejas

#### Semana 10: Patrones avanzados y anti-patrones
- **Día 1-2**: Agentes que se adaptan (reinforcement learning light)
  - Feedback del usuario informa decisiones futuras
  - *Construcción*: Agente que mejora sus recomendaciones basado en si usuario las sigue

- **Día 3-4**: Agentes adversariales (red teams)
  - Cómo un agente intenta "romper" las decisiones de otro
  - Casos de uso: testing, adversarial robustness
  - *Construcción*: Agente "abogado del diablo" que cuestiona propuestas crediticias

- **Día 5-6**: Agentes que generan agentes
  - Meta: un agente que diseña otros agentes para nuevas tareas
  - *Construcción*: "Agent factory" que toma descripción de problema y genera agente automáticamente

- **Día 7-8**: Anti-patrones comunes
  - Agentes que alucina (confianza excesiva en reasoning)
  - Agentes con prompts ambiguos (resultados inconsistentes)
  - Agentes que no escalan (exponential complexity)
  - *Construcción*: Audita tu sistema Fase 3. ¿Cuáles riesgos tiene?

- **Día 9-10**: Investigación y experimentación personal
  - Escoge un patrón avanzado que te interese profundizar
  - Diseña 2-3 experimentos para explorar
  - *Construcción*: Proof-of-concept de tu investigación

#### Semana 11: Aplicación a tu contexto profesional
- **Día 1-2**: Análisis de procesos actuales
  - Qué procesos en tu trabajo podrían beneficiarse de skills/agentes
  - ROI potential: tiempo ahorrado, calidad mejorada, escalabilidad
  - *Construcción*: Mapeo de 5 procesos CECO/Altara/análisis que podrían automatizarse

- **Día 3-4**: Diseño de solución empresarial
  - Architecture específica para tu contexto
  - Integración con sistemas existentes (Vertica, APIs internas)
  - *Construcción*: PRD (Product Requirements Document) para 1-2 proyectos pilotos

- **Día 5-6**: Prototipado rápido
  - MVP de solución para 1 proceso
  - Demo a stakeholders
  - *Construcción*: Prototype funcional listo para presentar

- **Día 7-8**: Estrategia de adoption y rollout
  - Cómo convencer a colegas, líderes
  - Change management: entrenamiento, documentación
  - *Construcción*: Deck de pitch + plan de implementación (timeline, recursos, riesgos)

- **Día 9-10**: Proyecto capstone Fase 4 (Parte 1)
  - **Entregable**: Solución empresarial completamente funcional
  - Tema: Mejora de proceso real en tu contexto (CECO, Altara, análisis de gastos)
  - Incluye: Prototipo, documentación técnica, presentación ejecutiva

#### Semana 12: Síntesis, testing extremo y profesionalización
- **Día 1-2**: QA y testing exhaustivo
  - 100+ test cases contra tu solución
  - Edge cases, scenarios de fracaso
  - *Construcción*: Test suite completo, bug report y fixes

- **Día 3-4**: Documentación profesional
  - README: cómo usar
  - API docs: qué endpoints/funciones expone
  - Architecture guide: por qué decidiste esto
  - Troubleshooting guide: cómo debuggear cuando falla
  - *Construcción*: Documenta tu solución empresarial como si la venderías

- **Día 5-6**: Performance bajo carga
  - Qué pasa con 100, 1000, 10000 requests
  - Bottlenecks, latency, error rates
  - *Construcción*: Load test tu sistema, identifica límites

- **Día 7-8**: Presentación final y reflexión
  - Deck ejecutivo: qué construiste, cuál es el impacto, qué aprendiste
  - Demo del sistema en vivo
  - *Construcción*: Presentation de 15 min + Q&A

- **Día 9-10**: Proyecto capstone Fase 4 (Parte 2) + Síntesis final
  - **Entregable final**: Carpeta con todo
    - Código fuente (skills, agentes, prompts)
    - Documentación técnica completa
    - Test suites
    - Metrics y benchmarks
    - Presentation deck
    - Reflection: qué construiste, qué aprendiste, cuál es el next step
  - **Bonus**: Roadmap de mejoras futuras (v2.0, v3.0)

---

## METODOLOGÍA: CÓMO ESTUDIAR 2 HORAS/DÍA

### Estructura de sesión (120 minutos)
```
0:00 - 0:05    Revisión de objetivo del día
0:05 - 0:25    Investigación + diseño (lectura, diagrama, planning)
0:25 - 1:35    Construcción activa (código, prompt, skill, pruebas)
1:35 - 1:50    Testing e iteración (bugs, mejoras)
1:50 - 2:00    Documentación + reflexión (notas, changelog)
```

### Herramientas recomendadas
- **Claude Projects**: Desarrolla skills y agentes
- **GitHub**: Versionado de todo (skills YAML, prompts, test code)
- **Jupyter Notebooks**: Para análisis y experimentación
- **Miro/Obsidian**: Diagramas de arquitectura, notas
- **Spreadsheet**: Tracking de métricas semana a semana

### Hábitos de aprendizaje
1. **Cada semana**: Revisa qué construiste. ¿Funciona? ¿Cuál es el patrón emergente?
2. **Cada día**: Documenta 1 cosa clave aprendida (en un "aprendizajes.md")
3. **Cada 2 semanas**: Refactoriza tus deliverables anteriores con lo que aprendiste
4. **Cada mes**: Revisión ejecutiva: ¿estoy avanzando hacia maestría?

---

## MÉTRICAS DE ÉXITO

### Por fase
- **Fase 1**: 3 skills documentados, testeados, usables en proyectos reales
- **Fase 2**: 1 agente autónomo que toma decisiones complejas sin intervención
- **Fase 3**: 1 sistema multinivel que coordina múltiples agentes + skills
- **Fase 4**: 1 solución empresarial que impacta un proceso real en tu trabajo

### Acumuladas
- **Portafolio**: 10+ skills maduros + 4+ agentes complejos
- **Documentación**: Suficientemente clara que alguien podría usar tus soluciones
- **Testing**: 200+ test cases que pasan
- **Performance**: Latencia <2s para decisiones; <5s para análisis complejos

---

## PRÓXIMOS PASOS INMEDIATOS

### Esta semana (Semana 1)
1. **Auditoría de skill actual**: Revisa "comunicacion-ejecutiva" y "skill-creator"
   - ¿Qué triggers funcionan? ¿Cuáles no?
   - ¿Cómo mejoraría v2.0?
   
2. **Setup de environment**:
   - GitHub repo para versionar skills
   - Spreadsheet para tracking de métricas
   - Claude Project dedicado a "Especialización IA"

3. **Sesión 1**: Lunes y martes (Día 1-2)
   - Auditoría profunda de comunicacion-ejecutiva
   - Rediseña de triggers
   - Documenta decisiones en changelog

---

## AJUSTES PERSONALIZADOS

Dado tu contexto (Eduardo, CDMX, data/analytics, Altara, financiero):

**Skills prioritarios para ti**:
- Comunicacion-ejecutiva (ya tienes ✓)
- Análisis-financiero (para propuestas, gastos)
- Validador-CNBV (compliance)
- Generador-reportes (Vertica → insights)

**Agentes prioritarios**:
- Gestor-gastos-CECO
- Evaluador-propuestas-crediticias (Altara)
- Asesor-financiero-personal (para tu Kia Sportage)

**Proyecto capstone**: Sistema de evaluación de "Altara Crédito Digital" que ya estás haciendo

---

## COSTO DE OPORTUNIDAD vs. BENEFICIO

**Inversión**: 168 horas = ~10 días hábiles intensivos (2 hrs/día × 84 días)

**Beneficio esperado**:
- Automatización de procesos que te toman 5-10 hrs/semana → ahorro de 250+ hrs/año
- Capacidad de prototipar soluciones en horas (vs. semanas con consultores)
- Expertise demandable en mercado latinoamericano (aún escaso)
- Multiplicador en tu rol: puedes liderar iniciativas de IA en tu institución

**ROI**: 2 meses de especialización = 2 años de productividad mejorada

