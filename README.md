# pricing-research

> Tres referencias y una recomendación: cuánto cuesta, cuánto cobra el mercado y cuánto vale.

**Investigación de precios** · Skill para agentes de código de la comunidad [nvvdev](https://github.com/nvv-dev). Funciona en Claude Code como plugin o como skill suelta, y en cualquier agente compatible con el formato abierto [`SKILL.md`](https://agentskills.io).

*English summary at the end.*

## Qué hace

Por cada producto o servicio junta el piso de costo (con las cifras que tú das), el rango de la competencia (cada precio con fuente y fecha, solo de páginas públicas) y el techo de valor para el comprador. Recomienda un precio con su supuesto y una prueba con métrica y regla de decisión. No publica ni cambia precios y, en impuestos, dice "validar con un contador".

## Objetivo

Poner precio con evidencia y una forma de equivocarse barato, en lugar de copiar a la competencia o adivinar.

## Cuándo usarla

- Antes de lanzar un producto o servicio y fijar su precio
- Cuando un precio parece alto o bajo, o la competencia cambió el suyo

## Cuándo no

- Asesoría tributaria o contable: validar con un contador
- Subir precios a clientes actuales: la skill propone, tú decides y avisas

## Ejemplo

```text
/pricing-research para tres paquetes de un estudio web freelance, con tres competidores citados con fuente y fecha.
```

## Cómo se activa

Esta skill **solo se activa a mano** (`disable-model-invocation: true`): no ocupa contexto en cada sesión y la invocas cuando la necesitas:

- Instalada como plugin: `/pricing-research:pricing-research`
- Copiada a `.claude/skills/`: `/pricing-research`

## Instalación

### Opción 1: Claude Code, como plugin (recomendada)

Dentro de Claude Code:

```text
/plugin marketplace add nvv-dev/claude-plugins
/plugin install pricing-research@nvvdev
```

La primera línea agrega el catálogo de nvvdev una sola vez; la segunda instala esta skill. Si prefieres el paquete completo, instala `growth-workflow@nvvdev` en su lugar (incluye esta skill y las demás de [growth-workflow](https://github.com/nvv-dev/growth-workflow)); no instales los dos a la vez.

### Opción 2: Claude Code, copiando la skill

Para un solo proyecto (se comparte con tu equipo por git):

```bash
git clone --depth 1 https://github.com/nvv-dev/pricing-research.git /tmp/pricing-research
mkdir -p .claude/skills
cp -R /tmp/pricing-research/skills/pricing-research .claude/skills/
```

Para todos tus proyectos, cópiala en `~/.claude/skills/` en lugar de `.claude/skills/`.

### Opción 3: otros agentes

Copia la carpeta `skills/pricing-research/` en la carpeta de skills de tu agente (cada agente documenta la suya). Con la CLI [skills](https://github.com/vercel-labs/skills) de Vercel Labs:

```bash
DISABLE_TELEMETRY=1 npx skills add nvv-dev/pricing-research
```

### Verificar

Abre una sesión nueva y pregunta "¿qué skills tienes disponibles?"; `pricing-research` debe aparecer. Con el plugin, `/plugin` la muestra como instalada.

### Actualizar o desinstalar

- Plugin: `/plugin marketplace update nvvdev` para actualizar; `/plugin uninstall pricing-research@nvvdev` para quitarla.
- Copia manual: repite la copia para actualizar, o borra la carpeta `.claude/skills/pricing-research`.

Antes de instalar cualquier skill, incluida esta, conviene leerla: es un solo archivo, [`skills/pricing-research/SKILL.md`](skills/pricing-research/SKILL.md). Ver [vetting-external-skills](https://github.com/nvv-dev/vetting-external-skills).

## Contenido

| Ruta | Qué es |
|---|---|
| `skills/pricing-research/SKILL.md` | La skill: instrucciones en inglés para que los escáneres de seguridad las analicen completas; el agente responde en tu idioma |
| `.claude-plugin/plugin.json` | Manifiesto para instalarla como plugin |
| `.github/workflows/` | Validación de estructura y escaneo con SkillSpector en cada cambio |

## Contribuir

Este repo se **genera** desde [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow), donde vive la versión canónica. Abre issues y PRs allí. La mejor contribución es un caso real en la sección *Known failures* de la skill, con la regla que lo evita.

## Origen

Escrita desde cero por nvvdev. Inspirada en: [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) (pricing, offers: price between the next-best alternative and perceived value, cost as a floor only, test on new customers).

## Licencia

MIT.

---

## English

**pricing-research** — Per product or service: cost floor, competitor range with source and date, value ceiling, and one recommended price with its assumption and a test. Never publishes or changes prices; no tax advice.

Install in Claude Code with `/plugin marketplace add nvv-dev/claude-plugins` and `/plugin install pricing-research@nvvdev`, or copy `skills/pricing-research/` into `.claude/skills/` (project) or `~/.claude/skills/` (personal). Other agents: copy the folder into their skills directory, or run `DISABLE_TELEMETRY=1 npx skills add nvv-dev/pricing-research`. Manual-only skill: invoke it with `/pricing-research:pricing-research` (plugin) or `/pricing-research` (copied). Canonical source: [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow). License: MIT.
