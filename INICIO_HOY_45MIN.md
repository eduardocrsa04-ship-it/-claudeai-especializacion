# ⏱️ INICIO HOY EN 45 MINUTOS
## De cero a listo para tu primera sesión de 2 horas

---

## RESUMEN
En 45 minutos tendrás:
- ✅ Claude Project "Hub de Maestría" creado y configurado
- ✅ Skill "especialista-ia" agregado
- ✅ GitHub repo inicializado
- ✅ Listo para comenzar Sesión 1 de Semana 1

**Luego**: 2 horas de trabajo real (auditoría de comunicacion-ejecutiva)

---

## FASE A: SETUP CLAUDE PROJECT (15 minutos)

### Paso 1: Crear proyecto (3 min)
```
1. Ve a https://claude.ai/projects
2. Haz clic en "+ New Project" (botón azul arriba)
3. En "Project Name": 
   Hub de Maestría en Claude IA

4. En "Description":
   Workspace para especialización 12 semanas: skills, agentes, proyectos.
   Fases: 1) Skills avanzados 2) Agentes simples 3) Multinivel 4) Capstone.

5. Haz clic "Create"
6. Espera a que cargue (30 segundos)
```

✅ Checkpoint: ¿Ves tu proyecto en la lista?

---

### Paso 2: Agregar skill "especialista-ia" (12 min)

**Opción A: Si tienes acceso a archivos (RECOMENDADO)**

```
1. En tu Project, haz clic en ⚙️ Settings (arriba a la derecha)
2. Busca sección "Skills" o "Custom Skills"
3. Haz clic "+ Add Skill"
4. Selecciona "Upload SKILL.md file"
5. 
   [IMPORTANTE] Copia el contenido de especialista-ia-SKILL.md
   Crea archivo local: especialista-ia.md
   
6. Upload ese archivo
7. Haz clic "Save" o "Add"
8. Cierra Settings
```

✅ Checkpoint: ¿Ves el skill en Project Settings?

**Opción B: Si no puedes upload (alternativa)**

```
1. En tu Project, abre chat nuevo
2. Escribe: "Quiero crear un skill llamado especialista-ia"
3. Pega el contenido del SKILL.md
4. Pídeme: "Ayúdame a crear este skill en mi Project"
5. Yo te guío paso a paso
```

✅ Checkpoint: ¿Puedes ver el skill en Settings después?

---

### Paso 3: Agregar documentos de programa (Optional pero recomendado, 2 min)

Si tu Project tiene sección "Knowledge" o "Documents":

```
1. Settings → Knowledge / Documents
2. "+ Add Document"
3. Para cada documento:
   - PROGRAMA_MAESTRIA_CLAUDE.md
   - ROADMAP_PRIMERAS_4_SEMANAS.md
   - especialista-ia-SKILL.md
   
   Upload o paste el contenido
4. Guardar
```

Si NO hay sección Knowledge: No es crítico, puedo copiar documentos en chat cuando los necesite.

✅ Checkpoint: ¿El Project se guardó sin errores?

---

## FASE B: SETUP GITHUB (15 minutos)

### Paso 1: Crear repositorio (3 min)

```
1. Ve a https://github.com/new
2. Repository name: 
   claudeai-especializacion

3. Description (opcional):
   Especialización 12 semanas en Claude: skills, agentes, proyectos

4. Privado o Público: Tu preferencia
5. "Initialize this repository with a README"? Sí
6. Haz clic "Create repository"
7. Copia la URL: https://github.com/[tu-usuario]/claudeai-especializacion
```

✅ Checkpoint: ¿Ves el repo en GitHub con README?

---

### Paso 2: Clonar repo en tu computadora (5 min)

**Opción A: Terminal (si usas Git)**

```bash
cd ~/Documentos  # o dónde prefieras guardar proyectos
git clone https://github.com/[tu-usuario]/claudeai-especializacion.git
cd claudeai-especializacion
```

**Opción B: GitHub Desktop**
```
1. Abre GitHub Desktop
2. File → Clone Repository
3. Pega URL: https://github.com/[tu-usuario]/claudeai-especializacion
4. Elige ubicación local
5. Haz clic "Clone"
```

**Opción C: Download ZIP (si no tienes Git)**
```
1. Ve a tu repo en GitHub
2. Botón verde "Code" → Download ZIP
3. Descomprime en ~/Documentos
```

✅ Checkpoint: ¿Tienes una carpeta "claudeai-especializacion" en tu computadora?

---

### Paso 3: Crear estructura de carpetas (5 min)

Abre terminal o explorador de archivos en carpeta `claudeai-especializacion`:

```bash
# Copiar estos comandos (funciona en Mac/Linux)
# En Windows: crea carpetas manualmente

mkdir -p fase-1-skills
mkdir -p fase-2-agentes-simples
mkdir -p fase-3-agentes-multinivel
mkdir -p fase-4-capstone
mkdir -p utilities
mkdir -p aprendizajes

# Copiar archivos de programa
cp ~/Documentos/PROGRAMA_MAESTRIA_CLAUDE.md .
cp ~/Documentos/ROADMAP_PRIMERAS_4_SEMANAS.md .
cp ~/Documentos/especialista-ia-SKILL.md .
cp ~/Documentos/PROYECTO_HUB_MAESTRIA_SETUP.md .
cp ~/Documentos/INICIO_HOY_45MIN.md .
```

O **manualmente**:
1. Abre explorador de archivos
2. En carpeta claudeai-especializacion:
   - Nueva carpeta: "fase-1-skills"
   - Nueva carpeta: "fase-2-agentes-simples"
   - Nueva carpeta: "fase-3-agentes-multinivel"
   - Nueva carpeta: "fase-4-capstone"
   - Nueva carpeta: "utilities"
   - Nueva carpeta: "aprendizajes"
3. Copia los .md files aquí

✅ Checkpoint: ¿Ves estructura de carpetas?

---

## FASE C: GIT COMMIT INICIAL (8 minutos)

```bash
cd ~/Documentos/claudeai-especializacion

# Ver archivos
ls -la
# Deberías ver: PROGRAMA*.md, ROADMAP*.md, etc, carpetas

# Stage all
git add .

# Commit
git commit -m "Initial commit: setup maestría Claude 12 semanas"

# Push a GitHub
git push origin main
```

**Si algo falla aquí**: 
- No es crítico para comenzar
- Omite git por ahora, comienza sesión de 2 hrs
- Volvemos a git después

✅ Checkpoint: ¿GitHub muestra tus archivos? 
Ve a https://github.com/[tu-usuario]/claudeai-especializacion

---

## FASE D: TEST DEL SETUP (5 minutos)

### Test 1: ¿El Project funciona?

1. Ve a tu Claude Project: https://claude.ai/projects/[tu-project-id]
2. Abre una nueva chat
3. Escribe exactamente:
   ```
   Quiero comenzar mi sesión de especialización en Claude IA.
   ¿Cómo iniciamos?
   ```

**Esperado**: El skill "especialista-ia" debería triggerear y responder.

Ej de respuesta correcta:
```
[especialista-ia skill activated]

Bienvenido a tu maestría en Claude IA.

Tengo 3 preguntas clave para estructurar tu sesión:

1. ¿Qué día/sesión toca hoy? (ej: Semana 1, Sesión 1)
2. ¿Qué completaste ayer?
3. ¿Cuál es tu objetivo hoy?
```

Si NO triggerealready:
- Intenta escribir: "Inicia sesión especialista-ia"
- Si aún no: skill aún no está agregado (regresa a Fase A, paso 2)

✅ Checkpoint: ¿El skill respondió?

---

### Test 2: ¿GitHub está listo?

1. Ve a https://github.com/[tu-usuario]/claudeai-especializacion
2. ¿Ves tus archivos listados?
3. ¿Ves el commit "Initial commit"?

✅ Checkpoint: ¿Sí a ambas preguntas?

---

## 🚀 ¡ESTÁS LISTO! PRÓXIMOS PASOS

### Hoy (después de estos 45 min)

**En tu Claude Project**, abre nueva chat y escribe:

```
/sessión-nueva

Hoy es Semana 1, Sesión 1 (Lunes).
Ayer completé: Nada, es primer día.
Objetivo hoy: Auditar comunicacion-ejecutiva, alcanzar 85% precision en triggers.

¿Cómo estructuramos estos 120 minutos?
```

Yo me encargaré del resto. ✅

---

### Esta semana (próximas sesiones)

- **Martes**: Sesión 2 (Crear skill analisis-financiero)
- **Miércoles**: Sesión 3 (Trigger design profundo)
- **Jueves**: Sesión 4 (Skill validador-gastos)
- **Viernes**: Sesión 5 + Reflexión semanal

Cada sesión = 2 horas, 1 entregable

---

## 📋 CHECKLIST FINAL

- [ ] Claude Project "Hub de Maestría" creado
- [ ] Skill "especialista-ia" agregado en Project
- [ ] GitHub repo inicializado y clonado
- [ ] Carpetas de fase (1, 2, 3, 4) creadas
- [ ] Archivos de programa copiados a repo
- [ ] Git commit inicial hecho
- [ ] Test 1 pasado: skill respondió en Project
- [ ] Test 2 pasado: GitHub muestra archivos
- [ ] Leído el ROADMAP_PRIMERAS_4_SEMANAS.md
- [ ] Listo para Sesión 1 (Semana 1, Día 1-2)

**Si todo está ✅**: 
Felicidades, estás oficialmente dentro del programa. 

**Siguiente paso**: Abre tu Project, inicia sesión 1, y comencemos con auditoría de comunicacion-ejecutiva.

---

## 🆘 SI ALGO NO FUNCIONA

### "El skill no triggerealready en mi Project"

→ Ir a [PROYECTO_HUB_MAESTRIA_SETUP.md](PROYECTO_HUB_MAESTRIA_SETUP.md), Parte 11 Troubleshooting

### "No sé cómo crear el Project"

→ Screenshots paso a paso: https://help.claude.ai/projects (busca)
→ O escríbeme aquí, te ayudo

### "GitHub me da error"

→ Omite GitHub por ahora, comenzamos de todas formas
→ Agregamos después (no es crítico para Sesión 1)

### "Me tomó más de 45 min"

→ Eso está OK. No hay prisa
→ Mejor 1 hora de setup sólido que 45 min de rush

---

## ÉXITO

Cuando completes esto:
- Tienes tu workspace centralizado (Project)
- Tienes tu skill orquestador (especialista-ia)
- Tienes tu repo respaldado (GitHub)
- Estás listo para 2 horas de construcción real

**No es "listo para entender teoría".**
**Es "listo para CONSTRUIR tu primer skill mejorado".**

Eso es lo que hace este programa diferente.

---

**¡Ahora comienza!** 🚀

Abre tu Project → Nueva chat → Escribe `/sessión-nueva` → Responde 3 preguntas → Yo armo tu plan de 2 hrs → Construimos juntos

