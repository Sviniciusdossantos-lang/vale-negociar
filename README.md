# Vale Negociar — Site Institucional + Assistente de IA

Protótipo completo do site institucional da **Vale Negociar**, plataforma fintech de antecipação de recebíveis.

## Funcionalidades

- **Landing page completa** com hero, como funciona, benefícios, simulação e FAQ
- **Protótipo iOS** com chatbot de IA integrado via Anthropic API
- **Formulário de simulação** com máscara de CNPJ e redirecionamento para WhatsApp
- **Botão flutuante WhatsApp** com mensagem pré-preenchida
- **Design responsivo** para mobile e desktop

## Estrutura

```
vale-negociar/
└── index.html      # Página única (single-file)
```

## Como usar

### 1. Clonar o repositório
```bash
git clone https://github.com/seu-usuario/vale-negociar.git
cd vale-negociar
```

### 2. Configurar a API Key da Anthropic

O chatbot usa a [API da Anthropic](https://www.anthropic.com). Para funcionar localmente, você precisa de uma API key.

> ⚠️ **Atenção**: Em produção, **nunca exponha sua API key no frontend**. Use um backend (Node.js, Python, etc.) como proxy.

Para desenvolvimento local, a API é chamada diretamente — funciona no ambiente Claude.ai por padrão.

### 3. Configurar o número de WhatsApp

No `index.html`, localize e substitua:
```javascript
const num = '5511999999999';
```
pelo número real da empresa (somente dígitos, com DDD e DDI).

### 4. Abrir no navegador
```bash
# Qualquer servidor local funciona, ex:
npx serve .
# ou
python3 -m http.server 8080
```

## Deploy sugerido

| Plataforma | Comando |
|---|---|
| GitHub Pages | Push para branch `gh-pages` |
| Vercel | `vercel --prod` |
| Netlify | Drag & drop da pasta |

## Customização

| O que mudar | Onde |
|---|---|
| Número WhatsApp | `const num = '...'` no script |
| Cores da marca | Variáveis CSS `:root { --green-700: ... }` |
| Dados estatísticos (hero) | Seção `.hero-stats` |
| System prompt do chatbot | Constante `SYSTEM_PROMPT` |
| Textos e conteúdos | Diretamente no HTML |

## Tecnologias

- HTML5 / CSS3 / JavaScript vanilla
- [Google Fonts](https://fonts.google.com) — Playfair Display + DM Sans
- [Anthropic Claude API](https://docs.anthropic.com) — claude-sonnet-4
- WhatsApp Business API (link direto)

## Próximos passos sugeridos

- [ ] Backend proxy para proteger a API key
- [ ] Integração com CRM (HubSpot, Pipedrive)
- [ ] Webhook para salvar leads do formulário
- [ ] Analytics (Google Analytics / Plausible)
- [ ] Versão PWA para instalar no celular

---

Desenvolvido como protótipo para o Vale Negociar.
