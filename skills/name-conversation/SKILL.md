---
name: name-conversation
description: Generate a very short title based strictly on the first substantive topic discussed in a new AI conversation, so the chat is easy to identify in Recent chats. Use when a chat begins, when the user asks to name or rename a conversation, or when an existing title is unnecessarily long. Preserve the original topic even if later messages discuss something else. Apply the title through a supported conversation-renaming action when available; otherwise suggest it without claiming the chat was renamed.
---

# Name Conversation

Create one compact title that represents what the user first came to discuss.

## Rules

1. Base the title on the first substantive request or topic, not on later turns.
2. Keep it to 3–5 words whenever possible, with a hard maximum of 7 words.
3. Retain the clearest distinctive term, product, project, vehicle, place, or subject.
4. Remove filler such as “Help with,” “Question about,” “I need to know,” “How can I,” or “New conversation,” including their equivalents in the conversation language.
5. Use the language of the first substantive message unless the user requests another language.
6. Preserve meaningful names and identifiers such as REGBUS, Toyota Coaster, Wilcom, or Arma Reforger.
7. Do not add dates, emojis, numbering, or “Chat:” unless they are essential to the original topic.

Examples:

- Agenda administrativa de REGBUS
- Potencia de Toyota Coaster
- Dirección del bordado Wilcom
- Autómata binario par
- Casa sobre una loma

## Ambiguity

- Ignore greetings and introductory filler when finding the first topic.
- If the initial request is too vague to identify a topic, wait for the first clarifying message.
- Once the original topic is clear, do not replace it merely because the conversation later branches elsewhere.

## Apply the title

- If the host exposes a supported action for renaming the current conversation, use it and verify success.
- Do not automate browser clicks or private APIs unless the user explicitly authorized that mechanism.
- If renaming is unavailable, never claim it succeeded. When the user explicitly asks for a title or invokes this skill, return only: Título sugerido: <título>.
- When invoked implicitly and no rename action exists, do not interrupt the main answer just to display the suggested title.
