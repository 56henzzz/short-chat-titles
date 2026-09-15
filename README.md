# Name Conversation

> Nombres cortos y reconocibles para nuestras conversaciones con IA.

[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-compatible-6D5CE7)](https://agentskills.io)
[![Version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/56henzzz/short-chat-titles)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

Name Conversation crea un título breve basado exclusivamente en el primer tema real del chat. El objetivo es que la lista de conversaciones recientes sea fácil de revisar y no se llene de nombres largos o genéricos.

## Resultado

| Primer tema del chat | Título generado |
| --- | --- |
| “Necesito agregar una agenda para el administrador de REGBUS” | Agenda administrativa de REGBUS |
| “La Toyota Coaster pierde fuerza cuando sube” | Potencia de Toyota Coaster |
| “Quiero aprender a crear un autómata para números pares” | Autómata binario par |
| “Cambiar el comienzo del corrido en Wilcom” | Dirección del bordado Wilcom |

## Reglas principales

- Usa el primer tema real; ignora saludos y frases de relleno.
- Genera normalmente 3–5 palabras, con un máximo absoluto de 7.
- Conserva nombres distintivos como REGBUS, Toyota Coaster o Arma Reforger.
- Usa el idioma del primer mensaje.
- No reemplaza el título porque después el chat cambie de tema.
- No utiliza scripts, dependencias, conexión de red ni datos externos.

## Compatibilidad

| Plataforma | Instalación | Observación |
| --- | --- | --- |
| Claude Code | Plugin o skill manual | Compatible |
| Claude Desktop | Pestaña Code | Compatible mediante Claude Code |
| Codex CLI y escritorio | Plugin o skill manual | Compatible |
| ChatGPT / ChatGPT Work | Carga de la skill | Depende de que la cuenta tenga Skills |
| Gemini CLI | Extensión o skill manual | Compatible |
| Claude.ai y Gemini web | Sin instalación directa oficial desde GitHub | Puede usarse como instrucción personalizada |

## Instalación

### Claude Code

Ejecuta estos comandos como dos mensajes separados:

    /plugin marketplace add 56henzzz/short-chat-titles
    /plugin install name-conversation@name-conversation

En Claude Desktop, usa los mismos comandos dentro de la pestaña Code.

### Codex

    codex plugin marketplace add 56henzzz/short-chat-titles
    codex plugin add name-conversation@name-conversation

La misma instalación cubre Codex CLI y las superficies de Codex que admitan plugins.

### ChatGPT y ChatGPT Work

1. Descarga este repositorio como ZIP.
2. Abre Plugins → Skills, si está disponible en tu cuenta.
3. Importa la carpeta skills/name-conversation o adjunta el ZIP y solicita instalar la skill.
4. Actívala al iniciar una conversación nueva.

La disponibilidad de Skills puede depender del plan, la aplicación y la configuración del espacio de trabajo.

### Gemini CLI

    gemini extensions install https://github.com/56henzzz/short-chat-titles

También puede instalarse únicamente la carpeta de la skill:

    gemini skills install https://github.com/56henzzz/short-chat-titles

### Instalación manual

Clona el repositorio:

    git clone https://github.com/56henzzz/short-chat-titles.git
    cd short-chat-titles

Copia skills/name-conversation en la carpeta personal correspondiente:

| Agente | Carpeta |
| --- | --- |
| Claude Code | ~/.claude/skills/name-conversation |
| Codex | ~/.codex/skills/name-conversation |
| Gemini CLI | ~/.gemini/skills/name-conversation |

## Uso

La skill puede activarse automáticamente cuando el agente detecta que debe nombrar una conversación. También puede invocarse directamente:

- Claude Code: /name-conversation
- Codex y ChatGPT: @name-conversation
- Gemini CLI: pide “Usa name-conversation para nombrar este chat”.

Salida cuando la plataforma no permite cambiar el nombre directamente:

    Título sugerido: Skill para nombrar chats

## Limitación importante

Una skill puede decidir el título, pero no puede obligar a una aplicación web a modificar su barra lateral. El renombrado automático solo ocurre cuando el agente anfitrión ofrece una acción oficial para cambiar el nombre de la conversación. Si esa acción no existe, la skill devuelve una sugerencia clara y nunca afirma que el chat fue renombrado.

Esta versión no manipula páginas web, no usa APIs privadas y no renombra conversaciones antiguas en lote.

## Estructura

    short-chat-titles/
    ├── .claude-plugin/
    │   ├── marketplace.json
    │   └── plugin.json
    ├── .codex-plugin/
    │   └── plugin.json
    ├── skills/
    │   └── name-conversation/
    │       ├── agents/openai.yaml
    │       └── SKILL.md
    ├── AGENTS.md
    ├── gemini-extension.json
    ├── LICENSE
    └── README.md

## Seguridad

Name Conversation es una skill de instrucciones. No ejecuta código, no recopila conversaciones, no transmite datos y no necesita credenciales.

## Licencia

Distribuido bajo la licencia MIT.
