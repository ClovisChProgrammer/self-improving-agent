# Self-Improvement Agent

[![OpenCode](https://img.shields.io/badge/OpenCode-compatible-blue)](https://opencode.ai)

> 🌐 **Outros idiomas:**
> [🇬🇧 English](README.md) ·
> [🇪🇸 Español](README_es.md)

Uma skill de autoaperfeiçoamento para **OpenCode** que mantém a identidade do seu assistente, aprende com cada interação e extrai conhecimento reutilizável — tudo isso respeitando sua privacidade.

---

## 📋 Descrição

Esta skill transforma seu agente de IA num assistente em melhoria contínua com:

- **Identidade definida** — princípios, regras de comportamento e memória que persistem entre sessões
- **Detecção automática de idioma** — responde no seu idioma (pt-BR, en, es, etc.) desde a primeira mensagem
- **Aprendizado contínuo** — registra correções técnicas, preferências do usuário, contexto de projetos e adaptações de comunicação
- **Detecção de padrões** — identifica questões recorrentes e as promove para a memória permanente
- **Extração de skills** — converte aprendizados valiosos em skills OpenCode reutilizáveis

---

## 🚀 Começo Rápido

### 1. Instalação

Clone a skill para o diretório de skills do OpenCode:

```bash
git clone https://github.com/ClovisChProgrammer/self-improving-agent.git ~/.config/opencode/skills/self-improving-agent
```

### 2. Carregamento

Em qualquer sessão OpenCode, use a ferramenta `skill`:

```
skill("self-improvement")
```

### 3. Uso

Basta começar a conversar. O agente irá:

1. Ler seus arquivos de identidade (SOUL.md, USER.md, etc.)
2. Detectar seu idioma a partir da sua primeira mensagem
3. Responder e aprender durante toda a sessão
4. Salvar sua preferência de idioma localmente para sessões futuras

---

## 📁 Estrutura

```
~/.config/opencode/skills/self-improving-agent/
├── SKILL.md              # Instruções principais (carregado via skill tool)
├── SOUL.md               # Identidade e princípios do assistente
├── USER.md               # Template público de perfil (sem dados pessoais)
├── USER.local.md         # 🔒 Perfil privado (criado localmente, em .gitignore)
├── AGENTS.md             # Regras operacionais e fluxo de trabalho
├── IDENTITY.md           # Template de identidade (nome, criatura, vibe, emoji)
├── .learnings/           # 📝 Logs de aprendizado por projeto
│   ├── LEARNINGS.md
│   ├── ERRORS.md
│   └── FEATURE_REQUESTS.md
├── scripts/
│   ├── extract-skill.ps1  # Extração de skills (Windows PowerShell)
│   └── extract-skill.sh   # Extração de skills (Unix)
├── references/
│   ├── opencode-integration.md
│   ├── hooks-setup.md
│   └── examples.md
├── assets/
│   ├── SKILL-TEMPLATE.md
│   ├── LEARNINGS.md
│   ├── ERRORS.md
│   └── FEATURE_REQUESTS.md
├── README.md              # 🇬🇧 English
├── README_pt-BR.md        # 🇧🇷 Este arquivo
└── README_es.md           # 🇪🇸 Español
```

---

## 🌍 Suporte a Idiomas

A skill detecta seu idioma **automaticamente** a partir da sua primeira mensagem:

| Sua mensagem começa com... | Idioma detectado |
|---------------------------|------------------|
| "Olá", "oi", "bom dia" | 🇧🇷 **pt-BR** (Português) |
| "Hello", "hi", "good morning" | 🇬🇧 **en** (Inglês) |
| "Hola", "buenos días" | 🇪🇸 **es** (Espanhol) |
| Outro ou ambíguo | 🇬🇧 **en** (padrão, perguntará) |

**Após detectado**, sua preferência é salva em `USER.local.md` (apenas local, nunca commitado).

> Conteúdo técnico (código, comandos, logs) permanece em inglês independentemente do seu idioma.

---

## 🧠 Funcionalidades

| Funcionalidade | Descrição |
|----------------|-----------|
| **🧠 Identidade** | SOUL.md define quem você é; USER.md lembra quem você ajuda |
| **📝 Aprendizado** | Registra correções técnicas, preferências pessoais, contexto de projetos |
| **🔄 Padrões** | Rastreia issues recorrentes e promove para memória permanente |
| **📦 Extração** | Converte aprendizados valiosos em skills reutilizáveis via `scripts/extract-skill.ps1` |
| **🎯 Modo Dual** | Programação técnica + desenvolvimento pessoal conversacional |
| **🌐 Multilíngue** | Detecta e responde automaticamente em pt-BR, en, es, e outros |
| **🔒 Privacidade** | Dados pessoais ficam em `USER.local.md` (em `.gitignore`) |

---

## 🔄 Como Funciona — Metodologia APR

Cada interação segue três passos:

1. **Aprender** — Consultar `.learnings/` e arquivos de identidade antes de responder
2. **Praticar** — Aplicar o conhecimento acumulado (técnico + contexto do usuário)
3. **Refinar** — Após a interação, registrar novos aprendizados

### Formato de Registro

```
## [LRN-YYYYMMDD-XXX] categoria

**Area**: frontend | backend | user_preference | project_context | ...
**Priority**: low | medium | high | critical
**Status**: pending | resolved | promoted

### Summary | Details | Suggested Action
```

Quando um aprendizado se repete (≥3 vezes, ≥2 tarefas, janela de 30 dias), ele é **promovido** para a memória permanente (SOUL.md, USER.md, ou AGENTS.md).

---

## 🔒 Privacidade

**Seus dados pessoais nunca saem da sua máquina.**

| Arquivo | Conteúdo | Trackeado pelo git? |
|---------|----------|---------------------|
| `USER.md` | Template público (sem dados reais) | ✅ Sim |
| `USER.local.md` | Seu nome real, credenciais, preferências | ❌ **Não** (em `.gitignore`) |
| `.learnings/` | Logs de sessão e aprendizados | ❌ **Não** (em `.gitignore`) |

### Como funciona

1. Na primeira execução, o agente detecta seu idioma e cria `USER.local.md`
2. Você pode preencher seu perfil (nome, profissão, preferências) — totalmente opcional
3. O arquivo é protegido pelo `.gitignore` e nunca é commitado ou enviado
4. Cada projeto tem seu próprio diretório `.learnings/` (também em `.gitignore`)

---

## 🤝 Contribuição

Contribuições são bem-vindas! Fique à vontade para abrir issues ou pull requests no [GitHub](https://github.com/ClovisChProgrammer/self-improving-agent).

---

## 📄 Licença

MIT

---

## Origem

Originalmente baseado em [pskoett/self-improving-agent](https://github.com/peterskoett/self-improving-agent), adaptado do OpenClaw para OpenCode com identidade de assistente expandida, suporte multilíngue e arquitetura com privacidade em primeiro lugar.
