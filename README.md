<p align="center">
  <img src="https://img.shields.io/badge/Claude_Code-Skill-blueviolet?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IndoaXRlIiBzdHJva2Utd2lkdGg9IjIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCI+PHBhdGggZD0iTTEyIDJMNiA3djEwbDYgNSA2LTV2LTEweiIvPjwvc3ZnPg==" alt="Claude Code Skill">
  <img src="https://img.shields.io/badge/-RAG_IA_Local-FF6B35?style=for-the-badge" alt="RAG IA Local">
  <img src="https://img.shields.io/badge/Por-PRYXIS-2ea44f?style=for-the-badge" alt="Por PRYXIS">
  <img src="https://img.shields.io/badge/Licencia-MIT-blue?style=for-the-badge" alt="Licencia MIT">
</p>

<h1 align="center">rag-local</h1>

<p align="center">
  <strong>De buscar durante horas a preguntar y saber.</strong><br>
  Skill de Claude Code para construir un asistente RAG privado sobre los documentos de tu empresa.
</p>

<p align="center">
  <a href="#el-problema">El problema</a> &bull;
  <a href="#que-construye">Que construye</a> &bull;
  <a href="#instalacion">Instalacion</a> &bull;
  <a href="#uso">Uso</a> &bull;
  <a href="#que-incluye">Que incluye</a>
</p>

---

## El problema

El conocimiento de tu empresa existe, pero esta repartido en Drive, correos, PDFs, el CRM y la cabeza de la gente. Cada consulta interna son horas buscando. Y ChatGPT generico no conoce tus datos: se los inventa.

**rag-local** le da a tu Claude Code el contexto para construir un asistente privado que responde desde TUS documentos, cita la fuente y no alucina.

---

## Que construye

Dile tu contexto y Claude Code construye el sistema entero:

```
       LO QUE LE DICES                     LO QUE CONSTRUYE
  ┌───────────────────────┐       ┌────────────────────────────────┐
  │                       │       │                                │
  │  Tus fuentes de datos │       │ 1. INGESTA                     │
  │  Quien consulta que   │       │    Chunking + embeddings       │
  │  Nube u on-premise    │       │    Base vectorial (pgvector)   │
  │                       │       │                                │
  └───────────────────────┘       │ 2. RETRIEVAL                   │
                                  │    Reranking + permisos        │
                                  │                                │
                                  │ 3. GROUNDING                   │
                                  │    Cita la fuente              │
                             ──>  │    No inventa: 'no lo se'      │
                                  │                                │
                                  │ 4. DESPLIEGUE                  │
                                  │    Nube u on-premise           │
                                  │                                │
                                  │ 5. INTEGRACIONES               │
                                  │    Slack / Teams / CRM         │
                                  │                                │
                                  │ 6. EVALUACION                  │
                                  │    Precision + adopcion        │
                                  │                                │
                                  └────────────────────────────────┘
```

---

## Instalacion

Clona el repo dentro de tu carpeta de skills de Claude Code:

```bash
git clone https://github.com/pryxis-ai/rag-local \
  ~/.claude/skills/rag-local
```

A partir de ahi, Claude Code carga la skill cuando le pidas construir un RAG (o menciones "IA local", "chat sobre documentos", "base vectorial", "embeddings", "on-premise").

---

## Uso

Pidele a Claude algo como:

> Ayudame a montar un asistente RAG privado sobre la documentacion de mi empresa, con respuestas que citen la fuente.

Seguira el workflow de construccion paso a paso, aplicara el grounding anti-alucinacion y consultara las referencias para el detalle tecnico.

---

## Que incluye

| Archivo | Que aporta |
|---------|-----------|
| `SKILL.md` | Definicion de la skill y workflow de construccion |
| `references/architecture.md` | Fases de ingesta y consulta, componentes |
| `references/data-preparation.md` | Fuentes, curacion y chunking |
| `references/retrieval-and-grounding.md` | Embeddings, pgvector, reranking, grounding |
| `references/deployment-and-eval.md` | Nube vs on-premise y evaluacion |
| `references/compliance.md` | RGPD, no-entrenamiento y control de acceso |

---

<p align="center">
  Hecho por <a href="https://pryxis.es"><strong>PRYXIS</strong></a> &bull; Licencia MIT
</p>
