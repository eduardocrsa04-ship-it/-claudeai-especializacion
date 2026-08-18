# SETUP: Claude Project "Hub de Maestría en Claude IA"
## Tu Workspace Centralizado para 12 Semanas

---

## PARTE 1: CREAR EL PROJECT

### Paso 1: Abrir Claude Projects
1. Ve a **claude.ai**
2. En la barra lateral izquierda, haz clic en **"+ New Project"**
3. O ve directamente a: **claude.ai/projects**

### Paso 2: Nombre y descripción
**Nombre del Project:**
```
Hub de Maestría en Claude IA
```

**Descripción del Project:**
```
Workspace centralizado para especialización en 12 semanas: skills, agentes y proyectos. 
Incluye: 9+ skills maduros, múltiples agentes, sistema multinivel, solución empresarial.
Fase actual: [Semana X/12]
```

### Paso 3: Configuración inicial
- **Privacy**: Privado (solo tú)
- **Sharing**: Desactiva (esto es solo tuyo)
- **Auto-update**: Sí (queremos que Claude tenga acceso a mejores tools)

---

## PARTE 2: AGREGAR EL SKILL ORQUESTADOR

### Paso 1: Importar skill "especialista-ia"

En tu nuevo Project:
1. Haz clic en **Settings** (⚙️ arriba a la derecha)
2. Ve a **Skills**
3. Haz clic en **+ Add Skill**
4. Opción A: **Upload SKILL.md file**
   - Copia el contenido de `especialista-ia-SKILL.md` 
   - Pégalo en nuevo archivo local: `especialista-ia.md`
   - Upload ese archivo
   
   Opción B: **Paste SKILL content**
   - Si tu sistema lo permite, copia/pega el contenido directamente

5. Guarda el Project

### Paso 2: Verificar que el skill se agregó
- Abre una nueva chat en el Project
- Escribe: "Hola, quiero comenzar mi sesión de aprendizaje"
- El skill debería triggerear automáticamente

**Esperado**: Ves algo como:
```
[especialista-ia skill activated]
Guía de Maestría en Claude IA detectada.
¿Quieres iniciar una nueva sesión? Tengo 3 preguntas clave...
```

Si NO triggerealready, revisa:
- ¿El archivo SKILL.md tiene frontmatter correcto (name: especialista-ia)?
- ¿El description del skill es específico (menciona "especialización 12 semanas")?

---

## PARTE 3: AGREGAR KNOWLEDGE BASE (DOCUMENTOS CLAVE)

Tu Project necesita acceso a tus documentos maestro. Esto permite que el skill y otros puedan referenciarlos.

### Documentos a agregar

1. **PROGRAMA_MAESTRIA_CLAUDE.md**
   - Path: `/mnt/user-data/outputs/PROGRAMA_MAESTRIA_CLAUDE.md`
   - Purpose: "Programa completo de 12 semanas"

2. **ROADMAP_PRIMERAS_4_SEMANAS.md**
   - Path: `/mnt/user-data/outputs/ROADMAP_PRIMERAS_4_SEMANAS.md`
   - Purpose: "Detalles de Fase 1"

3. **especialista-ia-SKILL.md** (este archivo como referencia)
   - Purpose: "Instrucciones del skill orquestador"

### Cómo agregar documentos

En Project Settings → **Knowledge** o **Documents**:
1. Haz clic en **+ Add Document**
2. Para cada documento:
   - **Source**: Upload file O paste text
   - **Name**: Nombre descriptivo (ej: "Roadmap Semanas 1-4")
   - **Type**: Markdown / Text
3. Guarda el Project

**Resultado**: El skill puede referirse a estos documentos. Ejemplo:
- "Según ROADMAP_PRIMERAS_4_SEMANAS, Sesión 1 es auditoría de comunicacion-ejecutiva"
- "PROGRAMA_MAESTRIA_CLAUDE menciona que Fase 2 comienza en Semana 4"

---

## PARTE 4: CONFIGURAR SYSTEM PROMPT DEL PROJECT

El Project puede tener su propio system prompt que aplica a TODAS las chats en el Project.

### Qué agregar a Project System Prompt

En **Project Settings** → **System Prompt**:

```
Eres el entrenador de especialización en Claude IA para Eduardo.

Tu trabajo es:
1. Guiar cada sesión de 2 hrs según el skill "especialista-ia"
2. Mantener a Eduardo en el roadmap de 12 semanas
3. Proporcionar feedback constructivo en artefactos (skills, agentes, tests)
4. Celebrar avances y ayudar cuando se bloquea

IMPORTANTE:
- Cada sesión debe producir algo concreto (skill YAML, test suite, agente, etc.)
- Prioriza construcción real (60+ minutos) sobre teoría
- Mide progreso con métricas específicas (precision %, test cases, documentación)
- No permitas que "teoría sin construcción" cuente como avance

CONTEXTO DE EDUARDO:
- Ubicación: Mexico City
- Rol: Data & Analytics en institución financiera
- Experiencia: Python/SQL, Vertica/CECO, UX executive presentations
- Top projects: Altara Crédito Digital, financing analysis (Kia/Toyota)
- Skills existentes: comunicacion-ejecutiva (v1.0), skill-creator

FASES:
1. Semanas 1-3: Skills avanzados (9 total, triggers, composición, memoria)
2. Semanas 4-6: Agentes simples (2+ agentes autónomos con reasoning)
3. Semanas 7-9: Agentes multinivel (supervisor + workers)
4. Semanas 10-12: Solución empresarial (impacto real en su trabajo)

Cuando veas que Eduardo está perdido o desmotivado, usa skill "especialista-ia" 
para rescatarlo (opciones de pivot/aceleración).
```

---

## PARTE 5: ESTRUCTURA DE CARPETAS (GitHub)

Tu Project debería estar respaldado en GitHub. Estructura recomendada:

```
claudeai-especializacion/
├── README.md                              # Overview del proyecto
├── PROGRAMA_MAESTRIA_CLAUDE.md            # Programa completo
├── ROADMAP_PRIMERAS_4_SEMANAS.md         # Detalle Fase 1
├── PROYECTO_HUB_MAESTRIA_SETUP.md        # Este archivo
├── especialista-ia-SKILL.md              # Tu skill orquestador
│
├── /fase-1-skills/                       # Semanas 1-3
│   ├── comunicacion-ejecutiva/
│   │   ├── v1.0-ORIGINAL.md
│   │   ├── v2.0-MEJORADO.md
│   │   └── changelog.md
│   ├── analisis-financiero/
│   │   ├── SKILL.md
│   │   ├── test-cases.json
│   │   └── ejemplos-uso.md
│   ├── validador-gastos/
│   ├── calculador-cuotas/
│   ├── evaluador-cnbv/
│   ├── extractor-insights-vertica/
│   ├── gestor-presupuesto/
│   ├── reporte-ejecutivo-gastos/
│   └── metricas-fase-1.md
│
├── /fase-2-agentes-simples/              # Semanas 4-6
│   ├── gestor-gastos-ceco/
│   │   ├── README.md
│   │   ├── system-prompt.md
│   │   ├── architecture.md
│   │   └── test-suite.json
│   ├── gestor-presupuesto-anual/
│   └── metricas-fase-2.md
│
├── /fase-3-agentes-multinivel/           # Semanas 7-9
│   ├── sistema-propuestas-crediticias/
│   │   ├── supervisor-agent.md
│   │   ├── workers/
│   │   │   ├── validador-cnbv.md
│   │   │   ├── analista-riesgo.md
│   │   │   └── calculador-financiero.md
│   │   ├── architecture.md
│   │   └── test-suite.json
│   └── metricas-fase-3.md
│
├── /fase-4-capstone/                    # Semanas 10-12
│   ├── proyecto-altara-credito-digital/
│   │   ├── PRD.md
│   │   ├── architecture.md
│   │   ├── demo-videos.md
│   │   ├── presentation.pptx
│   │   └── test-results.md
│   └── reflexion-final.md
│
├── /utilities/
│   ├── metrics-tracker.json              # Actualizar semanalmente
│   ├── test-templates.json               # Plantillas para test cases
│   └── checkpoint-questions.md           # Preguntas semanales
│
└── /aprendizajes/
    ├── semana-1.md
    ├── semana-2.md
    ├── ... (documentar qué aprendiste cada semana)
    └── patrones-clave.md
```

### Cómo inicializar repo

```bash
# Crea repo en GitHub (vacío, con README)
git clone https://github.com/[tu-usuario]/claudeai-especializacion.git
cd claudeai-especializacion

# Copia archivos iniciales
cp /ruta/a/PROGRAMA_MAESTRIA_CLAUDE.md .
cp /ruta/a/ROADMAP_PRIMERAS_4_SEMANAS.md .
cp /ruta/a/especialista-ia-SKILL.md .
cp /ruta/a/PROYECTO_HUB_MAESTRIA_SETUP.md .

# Crea carpetas
mkdir -p fase-1-skills fase-2-agentes-simples fase-3-agentes-multinivel fase-4-capstone utilities aprendizajes

# Primer commit
git add .
git commit -m "Initial commit: programa maestría Claude 12 semanas"
git push origin main
```

---

## PARTE 6: TRACKER DE MÉTRICAS

Crea archivo `utilities/metrics-tracker.json` para trackear tu progreso:

```json
{
  "program": {
    "start_date": "2026-01-13",
    "current_week": 1,
    "current_phase": "Fase 1: Skills Avanzados",
    "total_hours_planned": 168,
    "total_hours_completed": 0
  },
  
  "phase_1_skills": {
    "comunicacion_ejecutiva": {
      "status": "v1.0 → v2.0",
      "trigger_precision": "60% → 85%",
      "test_cases": 15,
      "documentation": "changelog, README",
      "github_url": "fase-1-skills/comunicacion-ejecutiva"
    },
    "analisis_financiero": {
      "status": "draft",
      "trigger_precision": "pending",
      "test_cases": 0,
      "documentation": "pending"
    }
    // ... más skills
  },
  
  "weekly_checkpoints": {
    "week_1": {
      "target_skills": 4,
      "actual_skills": 0,
      "target_test_cases": 50,
      "actual_test_cases": 0,
      "on_track": true,
      "blockers": "None yet"
    }
  },
  
  "capstone_project": {
    "topic": "Altara Crédito Digital Evaluation",
    "status": "pending",
    "expected_week": 10
  }
}
```

**Actualiza este archivo semanalmente**. Semanal means cada viernes después de reflexión.

---

## PARTE 7: SESIÓN TIPO DENTRO DEL PROJECT

Una vez configurado, así se verá tu flujo diario:

### Lunes 9am - Sesión 1

**Abre el Project** → Nueva chat

**Escribes:**
```
/sessión-nueva

Hoy es Semana 1, Día 1 (Lunes).
Ayer completé: [nada, es día 1]
Objetivo hoy: Auditar comunicacion-ejecutiva y alcanzar 85% precision en triggers

¿Cómo estructuramos estos 120 minutos?
```

**Yo respondo:**
```
✅ Sesión 1: Auditoría de comunicacion-ejecutiva

Timeline de 120 minutos:
0:00-0:05    Repaso: qué es "trigger precision"
0:05-0:25    Investigación: Revisa tu skill v1.0, prueba 15 prompts
0:25-1:35    Construcción: Diseña triggers v2.0, implementa
1:35-1:50    Testing: Corre 15 prompts contra v2.0
1:50-2:00    Documentación: Changelog, métricas

[Detalles específicos de cada fase...]
```

**A los 60 minutos, reportas:**
```
/checkpoint-60min

✅ Auditoria completada: comunicacion-ejecutiva v1.0 tiene 60% precision
✅ Identifiqué problemas: triggers muy genéricos, faltan contextos
✅ Diseñé triggers v2.0: 3 versiones con mejoras
⏳ Comenzando testing ahora
```

**A los 120 minutos, entregas:**
```
/entrega

Entregable: comunicacion-ejecutiva-v2.0-UPDATED.md

Cambios:
- Triggers expandidos: 5 → 12 keywords
- Agregué patrones de contexto (ej: "para board", "resumen ejecutivo")
- Testing: 15 prompts, 85% precision (12/15 correctos)

Changelog: 
v1.0 → v2.0
- Expanded trigger keywords
- Added context-based patterns
- Improved precision from 60% to 85%

Archivo: [link a GitHub]
Checklist: ✅ Concreto, ✅ Documentado, ✅ Testeado, ✅ Mejorable
```

**Yo valido:**
```
✅ SESIÓN 1 COMPLETADA

Validación:
✅ Artefacto concreto (YAML mejorado)
✅ Documentación clara (changelog)
✅ Testing completo (15 casos, 85%)
✅ Versión mejorable (v2.0, no final)

Métrica:
- Completaste auditoría exitosamente
- Mejoraste precision de 60% → 85% (objetivo 85%) ✅
- Documentación clear

Siguiente: Martes, Sesión 2 (Crear skill analisis-financiero)
```

---

## PARTE 8: ACCESO A DOCUMENTOS DENTRO DE CHATS

Una vez que agregues documentos al Project knowledge, puedes referenciarlos en chats:

**Tú escribes:**
```
Necesito recordar cuáles son los objetivos de Semana 1
```

**Yo puedo responder:**
```
Según ROADMAP_PRIMERAS_4_SEMANAS.md, Semana 1 tiene objetivos:

- Sesión 1-2: Auditar comunicacion-ejecutiva, v2.0
- Sesión 3-4: Trigger design avanzado
- Sesión 5-6: Constraints y safety
- Sesión 7-8: Integration con Projects
- Sesión 9-10: Evaluation y optimization

Actualmente estás en Sesión 1. ¿Necesitas más detalles de hoy?
```

---

## PARTE 9: RESPALDO Y SINCRONIZACIÓN

### GitHub Actions (Opcional pero recomendado)

Configura un GitHub webhook para que cada commit que hagas sea respaldado:

```yaml
# .github/workflows/backup.yml
name: Daily Backup
on:
  schedule:
    - cron: '0 8 * * *'  # Cada mañana a las 8am
jobs:
  backup:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Update metrics and sync
        run: |
          # Tu lógica de sync aquí
```

### Manual backup (Recomendado)

Cada viernes después de reflexión semanal:
```bash
git add .
git commit -m "Semana X checkpoint: [resumen de lo que completaste]"
git push origin main
```

---

## PARTE 10: TROUBLESHOOTING

### Skill no triggerealready

**Síntoma**: "Escribo sobre mi programa pero especialista-ia no se activa"

**Solución**:
1. Verifica que el skill esté en Project Settings → Skills ✅
2. El description debe ser muy específico. Prueba escribir:
   - "Quiero estructurar mi sesión de aprendizaje"
   - "Necesito iniciar sesión de especialización"
   - "¿Cuál es mi objetivo hoy en el programa?"
3. Si aún no triggerealready, menciona explícitamente: "Usa el skill especialista-ia para..."

### Project se vuelve lento

**Síntoma**: Las chats tardan mucho en responder

**Solución**:
1. Reduce cantidad de documentos en Knowledge (mantén solo los actuales)
2. Archive chats viejas que no uses
3. Crea sub-Projects si necesitas separar Fases (Fase 1 separado de Fase 2)

### No sé si estoy avanzando

**Solución**:
- Ejecuta `/auditoria` en tu Project
- Yo te reporto: skills completados, test cases, documentación vs. plan
- Comparamos contra PROGRAMA_MAESTRIA_CLAUDE.md

---

## PARTE 11: PRÓXIMOS PASOS — HOY MISMO

### 1. Crear el Project (5 minutos)
```
1. Ve a claude.ai/projects
2. Haz clic "+ New Project"
3. Nombre: "Hub de Maestría en Claude IA"
4. Descripción: (copia del Step 2 arriba)
5. Guardar
```

### 2. Agregar el Skill (10 minutos)
```
1. Abre el Project
2. Haz clic Settings (⚙️)
3. Skills → + Add Skill
4. Copia contenido de especialista-ia-SKILL.md
5. Pega y guarda
```

### 3. Agregar Documentos de Knowledge (10 minutos)
```
1. Settings → Knowledge/Documents
2. Agrega:
   - PROGRAMA_MAESTRIA_CLAUDE.md
   - ROADMAP_PRIMERAS_4_SEMANAS.md
   - especialista-ia-SKILL.md
3. Guarda Project
```

### 4. Crear GitHub Repo (5 minutos)
```
1. Ve a github.com/new
2. Nombre: "claudeai-especializacion"
3. Privado o público (tu preferencia)
4. Inicializa con README
5. Clone en tu computadora
```

### 5. Primera sesión (2 horas)
```
1. Abre tu Project
2. Nueva chat
3. Escribe: "/sessión-nueva" + responde las 3 preguntas
4. Yo estructuro tu primer día
5. ¡Comienza a construir!
```

---

## CHECKLIST FINAL: ¿ESTOY LISTO?

- [ ] Project creado en Claude.ai
- [ ] Skill "especialista-ia" agregado
- [ ] Documentos de programa en Knowledge
- [ ] GitHub repo inicializado
- [ ] Estructura de carpetas creada
- [ ] Métrica tracker inicial completado
- [ ] He leído el ROADMAP completo

**Si todo está ✅**: 

Abre tu Project ahora y escribe:
```
Hola especialista-ia, estoy listo para comenzar.

Hoy es [fecha], Semana 1, Sesión 1.
Ayer completé: [nada, es primer día]
Objetivo hoy: Auditar comunicacion-ejecutiva y alcanzar 85% precision

¿Estructuramos estos 120 minutos?
```

**¡Bienvenido a tu maestría!** 🚀

---

## REFERENCIA RÁPIDA: COMANDOS EN EL PROJECT

```
/sessión-nueva             → Inicia sesión (qué día, qué hiciste ayer, objetivo hoy)
/checkpoint-60min          → Check-in a mitad de sesión
/entrega                   → Valida tu artefacto final
/reflexión-semanal         → Análisis semanal + pasar a siguiente fase
/auditoria                 → Revisión completa de progreso
/rescate                   → Me siento perdido → juntos arreglamos
/acelerar                  → Quiero ir más rápido → opciones
/pausar [razón]            → Pausa programa → replaneamos
```

Estos "commands" son simplemente frases que triggererean el skill. Úsalas libremente.

