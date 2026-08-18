# ROADMAP: PRIMERAS 4 SEMANAS
## Fase 1 de 12 semanas - Dominio de Skills

**Objetivo a 30 días**: 3 skills robustos + 1 agente simple funcional

---

## SEMANA 1: FUNDAMENTOS AVANZADOS DE SKILLS

### Sesión 1 (Lunes) - Auditoría de tu skill "comunicacion-ejecutiva"
**Duración**: 2 hrs

**Meta**: Entender profundamente qué hace que tu skill funcione (o no)

**Actividades (120 min)**:
1. **0:00-0:10**: Revisa la definición de tu skill (estructura YAML)
2. **0:10-0:30**: Prueba 15 prompts diferentes contra tu skill
   - 5 que claramente deberían triggear (ej: "Redacta memo ejecutivo")
   - 5 que podrían triggear (ambiguo)
   - 5 que NO deberían triggear (fuera de dominio)
   - **Documenta**: ¿Cuál es el porcentaje de trigger acertado?

3. **0:30-1:00**: Analiza los "falsos negativos"
   - Prompts que DEBERÍAN triggear pero no lo hicieron
   - ¿Por qué? ¿Qué trigger keywords faltan?

4. **1:00-1:30**: Rediseña triggers v2.0
   - Expande keywords
   - Agrega patrones de contexto
   - Documenta cambios

5. **1:30-2:00**: Testing de v2.0 + documentación
   - Prueba los mismos 15 prompts contra v2.0
   - ¿Mejoró? ¿Se rompió algo?
   - Escribe changelog

**Entregable**: 
- Documento: "comunicacion-ejecutiva-audit.md" con resultados
- Changelog de mejoras a v2.0
- Métrica: % de precision mejora (ej: 60% → 80%)

---

### Sesión 2 (Martes) - Creación de skill "analisis-financiero"

**Duración**: 2 hrs

**Meta**: Crear nuevo skill especializado (inspirado en tu experiencia CECO/Vertica)

**Actividades (120 min)**:
1. **0:00-0:15**: Especificación del skill
   - Nombre: analisis-financiero
   - Triggers: "analiza estos gastos", "dame insights financieros", "¿dónde cortamos?"
   - Inputs: CSV/JSON de transacciones
   - Outputs: Resumen ejecutivo, recomendaciones de ahorro
   - Constraints: Solo datos sanitizados; no revelar info personal

2. **0:15-0:45**: Estructura YAML del skill
   - Metadata completa
   - Instrucciones detalladas (basadas en comunicacion-ejecutiva)
   - Ejemplos de inputs/outputs

3. **0:45-1:30**: Implementación en Claude Projects
   - Crea proyecto "skills-fase1"
   - Agrega skill "analisis-financiero"
   - Prueba 10 casos: ¿qué tan bueno es?

4. **1:30-1:50**: Iteración
   - Ajusta instrucciones si es necesario
   - Mejora precisión de triggers

5. **1:50-2:00**: Documentación inicial
   - README: qué es este skill
   - Ejemplos de uso

**Entregable**:
- Skill "analisis-financiero" funcional en tu Project
- YAML file guardado en GitHub
- Documentación básica

---

### Sesión 3 (Miércoles) - Exploración de triggers en profundidad

**Duración**: 2 hrs

**Meta**: Entender cómo Claude decide cuándo usar un skill

**Actividades (120 min)**:
1. **0:00-0:20**: Teoría rápida
   - Lee documentación de skills de Anthropic (si existe)
   - Comprende: word matching vs. semantic matching vs. context-based

2. **0:20-1:00**: Experimento A/B de triggers
   - Toma tu skill "comunicacion-ejecutiva"
   - Versión A: triggers simples ("ejecutivo", "dirección", "junta")
   - Versión B: triggers más específicos ("redacta para board", "memo para CEO")
   - Prueba ambas con 20 prompts
   - **Resultado**: ¿Cuál versión tiene mejor precision/recall?

3. **1:00-1:30**: Diseño de triggers para "analisis-financiero"
   - Triggers técnicos: "csv", "datos", "analytics"
   - Triggers de negocio: "gastos", "presupuesto", "costo"
   - Triggers combinados: "análisis de gastos", "insights financieros"

4. **1:30-1:50**: Prueba y refinamiento
   - 15 prompts para "analisis-financiero"
   - Mide precision

5. **1:50-2:00**: Documentación de learnings
   - "que-aprendí-triggers.md"
   - Best practices: qué triggers funcionan, cuáles no

**Entregable**:
- Experimento A/B documentado
- Triggers optimizados para ambos skills
- Lecciones aprendidas sobre trigger design

---

### Sesión 4 (Jueves) - Creación de skill "validador-gastos"

**Duración**: 2 hrs

**Meta**: Skill con lógica de validación y reglas de negocio

**Actividades (120 min)**:
1. **0:00-0:15**: Diseño de requisitos
   - Input: Gasto (monto, categoría, justificación)
   - Validaciones:
     - Monto máximo por categoría (ej: viáticos max $500)
     - Categoría válida (de lista predefinida)
     - Justificación coherente (no vacía, idioma español)
   - Output: Aprobado/Rechazado + razones + sugerencias

2. **0:15-0:45**: Implementación del skill
   - Estructura YAML con validaciones
   - Instrucciones claras sobre reglas
   - Ejemplos de entrada/salida

3. **0:45-1:30**: Testing exhaustivo
   - 20 casos de prueba (10 aprobados, 10 rechazados, variantes)
   - Edge cases: monto negativo, categoría typo, etc.
   - ¿El skill es consistente?

4. **1:30-1:50**: Mejora de precisión
   - Ajusta instrucciones si hay falsos positivos/negativos
   - Agrega ejemplos explícitos

5. **1:50-2:00**: Documentación
   - Changelog
   - Test results

**Entregable**:
- Skill "validador-gastos" en Project
- Test suite (20 casos documentados)
- Métricas de precision

---

### Sesión 5 (Viernes) - Composición: "comunicacion-ejecutiva" + "analisis-financiero"

**Duración**: 2 hrs

**Meta**: Un skill llama otro skill (composición)

**Actividades (120 min)**:
1. **0:00-0:20**: Diseño de composición
   - Nuevo skill: "reporte-ejecutivo-gastos"
   - Qué hace: toma datos de gastos → llama "analisis-financiero" → formatea con "comunicacion-ejecutiva"
   - Arquitectura: skill A → skill B → output combinado

2. **0:20-1:00**: Implementación
   - Instrucciones que integren múltiples skills
   - ¿Cómo se "llama" un skill dentro de otro?
   - (En realidad, en Claude Projects, es el Project quien orquesta, pero simula que tu skill coordina)

3. **1:00-1:30**: Testing
   - Input: CSV de gastos
   - Output esperado: Análisis + reporte ejecutivo
   - ¿Funciona la composición?

4. **1:30-1:50**: Iteración
   - Mejora flujo de datos entre skills

5. **1:50-2:00**: Documentación + reflexión
   - Diagrama de flujo: skill A → skill B → output
   - Aprendizajes

**Entregable**:
- Skill "reporte-ejecutivo-gastos" funcional
- Diagrama de composición
- Test cases

---

### Semana 1 - Checkpoint

**Entregables completados**:
- ✅ 3 skills mejorados/creados: comunicacion-ejecutiva (v2.0), analisis-financiero, validador-gastos
- ✅ 1 skill compuesto: reporte-ejecutivo-gastos
- ✅ Test suites: 50+ casos
- ✅ GitHub repo con todo versionado

**Métricas**:
- Precision promedio de triggers: 85%+
- Todos los skills documentados y listos para uso

---

## SEMANA 2: SKILLS PARA CASOS EMPRESARIALES

### Sesión 6 (Lunes) - Skill "extractor-insights-vertica"

**Duración**: 2 hrs

**Meta**: Skill que transforma datos SQL/CSV en insights

**Contexto**: Basado en tu experiencia CECO/Vertica de mejora de proceso de gastos

**Actividades (120 min)**:
1. **0:00-0:20**: Especificación
   - Input: Resultado de query Vertica (simulado en JSON)
   - Transformaciones:
     - Agregación por categoría
     - Tendencias (mes vs mes)
     - Outliers (gastos anómalos)
   - Output: JSON con insights estructurados

2. **0:20-1:00**: Implementación
   - Instrucciones para identificar patrones
   - Ejemplos de datos CECO reales (anonimizados)
   - Formato de salida

3. **1:00-1:30**: Testing con datos reales
   - ¿Identifica outliers correctamente?
   - ¿Las agregaciones son exactas?
   - Performance: ¿qué tan rápido?

4. **1:30-1:50**: Iteración
   - Mejora precisión en detección de anomalías

5. **1:50-2:00**: Documentación
   - Input/output examples

**Entregable**:
- Skill funcional
- Test cases con datos CECO simulados
- Documentación

---

### Sesión 7 (Martes) - Skill "evaluador-cnbv"

**Duración**: 2 hrs

**Meta**: Skill que valida propuestas contra normativa CNBV

**Actividades (120 min)**:
1. **0:00-0:20**: Investigación rápida de CNBV basics
   - Límites de crédito
   - Documentación requerida
   - Ratios de riesgo

2. **0:20-1:00**: Implementación del skill
   - Validaciones contra reglas CNBV (simplificadas)
   - Output: Lista de cumplimiento/incumplimientos
   - Sugerencias de remediación

3. **1:00-1:30**: Testing
   - 10 casos: propuestas que cumplen, que no

4. **1:30-1:50**: Mejora e iteración

5. **1:50-2:00**: Documentación

**Entregable**:
- Skill "evaluador-cnbv"
- Test suite
- Disclaimer: simplificado, no reemplaza revisión legal

---

### Sesión 8 (Miércoles) - Skill "calculador-cuotas"

**Duración**: 2 hrs

**Meta**: Skill que calcula amortización de créditos (útil para tu análisis Kia/Toyota)

**Actividades (120 min)**:
1. **0:00-0:15**: Especificación
   - Inputs: monto principal, tasa anual, plazo (meses)
   - Output: tabla de amortización, cuota mensual, total pagado, intereses

2. **0:15-1:00**: Implementación
   - Fórmula de amortización (ya existe, pero lo integras en skill)
   - Manejo de diferentes tipos de crédito (simple, compuesto)

3. **1:00-1:30**: Testing
   - Valida contra calculadoras conocidas (Banamex, Scotiabank)
   - ¿Resultados exactos o aproximados?

4. **1:30-1:50**: Iteración y mejora

5. **1:50-2:00**: Documentación + ejemplos

**Entregable**:
- Skill "calculador-cuotas" preciso y testeado
- Ejemplos con tus datos (Kia Sportage HEV vs. Toyota)

---

### Sesión 9 (Jueves) - Skill con memoria: "gestor-presupuesto"

**Duración**: 2 hrs

**Meta**: Skill que "recuerda" decisiones previas del usuario

**Actividades (120 min)**:
1. **0:00-0:20**: Diseño de memoria
   - Qué recordar: gastos previos, categorías, límites establecidos
   - Dónde guardar: simular persistencia (JSON file)
   - Flujo: user → skill → actualiza memoria

2. **0:20-1:00**: Implementación
   - Instrucciones para acceder a "memoria"
   - Validar gasto contra presupuesto histórico
   - Alertas si se aproxima a límite

3. **1:00-1:30**: Testing
   - Simula 5 usuarios con históricos diferentes
   - ¿El skill ajusta comportamiento?

4. **1:30-1:50**: Mejora

5. **1:50-2:00**: Documentación

**Entregable**:
- Skill que "recuerda" estado de usuario
- Test suite

---

### Sesión 10 (Viernes) - Integración: Suite de skills para "propuesta-crediticia"

**Duración**: 2 hrs

**Meta**: Todos los skills anteriores trabajan juntos

**Actividades (120 min)**:
1. **0:00-0:30**: Diseño de arquitectura
   - User inicia: "Evalúa esta propuesta de crédito de $500k"
   - Flujo: validación CNBV → análisis de riesgo → cálculo de cuotas → comunicación ejecutiva
   - Qué skill se ejecuta en qué orden

2. **0:30-1:30**: Testing end-to-end
   - 5 propuestas completas
   - ¿Fluye correctamente entre skills?
   - ¿Output final es coherente?

3. **1:30-1:50**: Debugging y fixes
   - Qué skills no interactúan bien
   - Mejora coordinación

4. **1:50-2:00**: Documentación
   - Diagrama completo del flujo
   - Como debería usarse

**Entregable**:
- Suite de 5+ skills integrados y funcionales
- Diagrama de arquitectura
- End-to-end test cases

---

### Semana 2 - Checkpoint

**Entregables completados**:
- ✅ 5 skills nuevos: extractor, validador, calculador, gestor, suite
- ✅ Total portfolio: 9 skills maduros
- ✅ 100+ test cases acumulados
- ✅ Todos documentados y versionados

**Reflexión**: ¿Cómo estos skills podrían servir en tu trabajo diario?

---

## SEMANA 3: AGENTE SIMPLE (PRIMER AGENTE)

### Sesión 11 (Lunes) - Diseño de "Agente Gestor de Gastos"

**Duración**: 2 hrs

**Meta**: Entender qué es un agente vs. un skill

**Actividades (120 min)**:
1. **0:00-0:15**: Teoría
   - Skill: reactivo (user pide → skill responde)
   - Agente: proactivo (razona, decide, actúa iterativamente)
   - Loop: Percibir → Razonar → Decidir → Actuar

2. **0:15-0:45**: Especificación del agente
   - Nombre: "Gestor-Gastos-CECO"
   - Objetivo: Procesar solicitud de gasto → validar → calcular impacto presupuestario → recomendar
   - Tools disponibles: tus 5 skills anteriores
   - Autoridad: ¿puede aprobar directamente o solo recomendar?

3. **0:45-1:30**: Diseño del system prompt
   - Rol: "Eres un auditor de gastos experimentado"
   - Responsabilidades: validar, analizar, recomendar
   - Límites: no aprobar >$10k sin escalación
   - Tone: profesional, conciso

4. **1:30-1:50**: Documentación de arquitectura
   - Diagrama: Agente → Tools (tus skills)
   - Flujo de decisión

5. **1:50-2:00**: Prepare test cases
   - 10 escenarios de prueba listos

**Entregable**:
- Especificación completa del agente
- System prompt draft
- Test cases

---

### Sesión 12 (Martes) - Implementación del Agente

**Duración**: 2 hrs

**Actividades (120 min)**:
1. **0:00-0:30**: Setup en Claude Projects
   - Crea nuevo Project o subsection
   - Agrega nombre, descripción
   - Carga system prompt

2. **0:30-1:15**: Testing inicial
   - 5 casos simples: gasto pequeño, gasto grande, gasto dudoso, etc.
   - ¿El agente razona correctamente?
   - ¿Llama tools correctamente?

3. **1:15-1:45**: Debugging
   - ¿Qué no funciona?
   - Ajusta system prompt

4. **1:45-1:55**: Documentación

5. **1:55-2:00**: Reflexión
   - ¿Cómo se diferencia este agente de un skill complejo?

**Entregable**:
- Agente funcional en Claude Project
- Test results

---

### Sesión 13 (Miércoles) - Testing exhaustivo del agente

**Duración**: 2 hrs

**Actividades (120 min)**:
1. **0:00-2:00**: Test-driven improvements
   - 10 test cases completos
   - Documenta: caso, entrada, salida esperada, salida actual
   - Si falla: ajusta system prompt, retest
   - Objetivos de precision: 90%+

**Entregable**:
- Test suite completamente documentada
- Agente optimizado

---

### Sesión 14 (Jueves) - Agente + Memoria: "Gestor-Presupuesto-Anual"

**Duración**: 2 hrs

**Meta**: Agente que recuerda y aprende

**Actividades (120 min)**:
1. **0:00-0:30**: Diseño con memoria
   - Agente recuerda: gastos del mes, límites establecidos, decisiones previas
   - Cada decisión → actualiza memoria
   - Próxima solicitud → consulta memoria

2. **0:30-1:30**: Implementación
   - Simula persistencia de memoria
   - Agente razona considerando histórico

3. **1:30-1:50**: Testing
   - Usuario 1 hace 5 solicitudes a lo largo de mes
   - ¿Agente aprende?

4. **1:50-2:00**: Documentación

**Entregable**:
- Agente con memoria funcional
- Test suite

---

### Sesión 15 (Viernes) - Síntesis Semana 3 + Iteración

**Duración**: 2 hrs

**Actividades (120 min)**:
1. **0:00-0:45**: Revisión completa
   - ¿Tienes 2 agentes simples funcionales?
   - ¿Todos los skills de Fase 1 todavía funcionan?
   - ¿Documentación completa?

2. **0:45-1:30**: Refactoring
   - Mejora skills y agentes con nuevo conocimiento
   - Limpia código, instrucciones

3. **1:30-2:00**: Documentación final de Fase 1
   - Resumen ejecutivo: qué construiste
   - Lecciones aprendidas
   - Roadmap siguiente

**Entregable**:
- **ENTREGA FINAL FASE 1**:
  - 9 skills documentados
  - 2 agentes simples funcionales
  - 100+ test cases
  - Documentación ejecutiva

---

### Semana 3-4 - Checkpoint Final Fase 1

**Portfolio al completar primeras 4 semanas**:
- ✅ 9 skills maduros (trigger design, composición, memoria)
- ✅ 2 agentes simples (reasoning, tools, memory)
- ✅ 120+ test cases
- ✅ Documentación profesional
- ✅ GitHub repo con versionado completo

**Reflexión personal**:
- ¿Cuál skill/agente fue más valioso?
- ¿Qué patrón emergente ves?
- ¿Cómo aplicarías esto en tu trabajo real?

**Siguiente**: Semana 4 entra en **Fase 2: Agentes complejos y orquestación**

---

## RECOMENDACIONES PARA ESTAS 4 SEMANAS

### Hábito diario
- **0:00-0:10**: Lee tu objetivo del día
- **2:00-2:10**: Documenta 1 aprendizaje clave

### Hábito semanal (viernes)
- Revisa todos los entregables
- Corre todos los test cases
- Actualiza spreadsheet de métricas

### Revisión bi-semanal
- Refactoriza skills viejos con nuevo conocimiento
- Busca patterns reutilizables

### GitHub discipline
- Commit después de cada sesión
- Mensaje claro: qué cambió, por qué
- PR para cambios grandes

---

## DUDAS QUE SURGIRÁN (Anticipadas)

**P: ¿Qué pasa si un skill no funciona bien?**
R: Regresa a sesión anterior, mejora triggers/instrucciones, retest. La iteración es normal.

**P: ¿Necesito aprender Python para esto?**
R: No es requerido para skills/agentes, pero te ayudaría para testing. Lo dejaremos como bonus.

**P: ¿Puedo saltarme una sesión?**
R: No es ideal. Pero si lo haces, asegúrate de hacer el entregable antes de avanzar.

**P: ¿Cuándo veo resultados prácticos en mi trabajo?**
R: Semana 4 ya deberías tener agentes que puedan automatizar algo pequeño en CECO.

