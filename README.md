# OrigamiPay — Pitch Deck

Apresentação comercial interativa da OrigamiPay para sellers de e-commerce, otimizada para envio direto a prospects.

**Duas versões disponíveis:**

- **`/`** (`index.html`) — pitch completo de 12 slides para reuniões e calls
- **`/pocket`** (`pocket.html`) — teaser de 3 slides para WhatsApp, e-mail frio e social. 30 segundos de leitura.

12 slides cobrindo problema, diferencial (PIX Consignado), perfil do cliente CLT, fluxo de checkout, vantagens, comparativo cartão × BNPL × OrigamiPay, simulador interativo, segurança e parceiros, integração VTEX/API, verticais de clientes e CTA com agendamento via Calendly.

## Stack

Site estático: HTML + CSS + JavaScript vanilla. Sem framework, sem build step. Tudo em arquivos HTML únicos com assets em `public/assets/`.

- Tipografia: Inter + JetBrains Mono (Google Fonts)
- Tema: dark + neon green
- Calculadora interativa via JavaScript puro (versão completa)
- Mobile responsive (breakpoints em 1023px, 768px e 420px)
- Navegação por teclado (← →), scroll, touch swipe e cliques nas bordas

## Estrutura

```
.
├── public/
│   ├── index.html        # pitch completo de 12 slides
│   ├── pocket.html       # teaser de 3 slides (versão pocket)
│   └── assets/           # imagens, logos de parceiros, QR code
├── vercel.json           # config de deploy + cache headers
├── package.json
└── README.md
```

## Rodando localmente

Qualquer servidor estático funciona. Usando `npx serve`:

```bash
npx serve public -p 3000
```

Ou simplesmente abrir o `public/index.html` no navegador (algumas funcionalidades podem ter limitações por causa de CORS, mas o deck funciona).

## Deploy na Vercel

### Opção A — pelo dashboard da Vercel (recomendado)

1. Sobe esse repositório no GitHub
2. Em [vercel.com/new](https://vercel.com/new), importa o repositório
3. Na tela de configuração:
   - **Framework Preset:** Other
   - **Root Directory:** `./` (raiz)
   - **Build Command:** deixa vazio
   - **Output Directory:** `public`
4. Clica em **Deploy**

A Vercel detecta o `vercel.json` automaticamente e aplica os headers de cache.

### Opção B — pela CLI

```bash
npm i -g vercel
vercel
# follow prompts; quando perguntar output directory, responda "public"
```

### Domínio customizado

Após o deploy, na Vercel: **Project Settings → Domains** → adicionar `pitch.origamipay.com.br` (ou qualquer subdomínio que você quiser). A Vercel gera os registros DNS (CNAME) que você adiciona no painel do seu provedor de domínio.

## Como usar comercialmente

Você tem duas versões com finalidades diferentes:

**Pocket (`/pocket`)** — para abrir conversa
- Mande no WhatsApp, e-mail de prospecção, DM de LinkedIn
- 3 slides, ~30 segundos de leitura, formato vertical-mobile-friendly
- Estrutura narrativa: dor → solução → ação
- Tem botão "Pitch completo" no canto superior direito que leva pro deck longo

**Completo (`/`)** — para fechar negócio
- Use em calls com decisor, follow-ups depois do interesse, propostas formais
- 12 slides com calculadora interativa, comparativo, cases por vertical
- Carrega o storytelling profundo que já justifica o valor

**Fluxo recomendado:**
1. Mande o link do pocket no primeiro contato → quebra a barreira de "não tenho tempo agora"
2. Se o seller responder com interesse → mande o pitch completo
3. Se ele agendar a demo pelo Calendly → você abre o completo na call

- **Tracking opcional**: dá pra adicionar Vercel Analytics (gratuito) ou Google Analytics editando o `<head>` dos HTMLs.
- **Versões customizadas por prospect**: dá pra criar branches/forks com nome do cliente, simulação pré-preenchida no slide 8 e cases específicos do setor dele.

## Atualizando o conteúdo

Toda alteração de copy, número ou layout fica no arquivo `public/index.html`. Não tem build — basta editar, salvar, fazer commit e push. Vercel re-deploya automaticamente em poucos segundos.

## Browser support

Testado em Chrome, Safari, Firefox e Edge (versões recentes). Mínimo recomendado: navegadores com suporte a `clamp()`, `aspect-ratio` e CSS Grid (todos os navegadores 2021+).

## Licença

Material proprietário da OrigamiPay. Não distribuir publicamente sem autorização.
