# AGENTS — Instrucciones para agentes de IA

Breve guía para que agentes de IA (Copilot/otros) sean productivos en este repositorio.

**Propósito**
- Ayudar a integrar y mantener una integración con un motor de búsqueda de Google.

**Qué debe saber el agente antes de ejecutar cambios**
- El repositorio actualmente está vacío salvo [README.md](README.md). No hay stack ni scripts de construcción.
- Antes de implementar, el agente debe preguntar o decidir el _stack_ objetivo (recomendado: Python o Node.js).

**Tareas repetibles y comandos**
- Inicializar el proyecto (crear `src/`, `tests/`, y manifiesto de dependencias). No ejecutar sin permiso.
- Usar variables de entorno para credenciales (archivo modelo: `.env.example`).

**Convenciones para integración con Google Search**
- Credenciales: no almacenarlas en el repositorio; usar `GOOGLE_API_KEY` y `GOOGLE_CX` en variables de entorno.
- Módulo sugerido: `src/google_search.py` (Python) o `src/googleSearch/index.js` (Node) con función clara `search(query, opts)`.
- Manejo de límites: implementar reintentos exponenciales y backoff para errores 429/503.

**Pruebas y CI**
- Añadir pruebas unitarias en `tests/` que mockeen llamadas HTTP a la API de Google.
- Proponer un workflow GitHub Actions en `.github/workflows/ci.yml` que instale dependencias y ejecute tests.

**Seguridad y secretos**
- Añadir `.env.example` con claves de entorno vacías y documentación en `README.md` sobre cómo obtener claves.

**Dónde buscar más información**
- Documentación existente: [README.md](README.md)

**Siguientes custom agents recomendados**
- `/create-skill search-integration`: genera el esqueleto del módulo de búsqueda y pruebas.
- `/create-instruction credentials`: crea `.github/copilot-instructions.md` con políticas de manejo de secretos.

---
Documento minimalista: enlaza a documentación más extensa cuando exista.
