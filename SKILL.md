---
name: t2-design
description: Design system da T2 Educação (DS-T2 Clareza, dark-only). Use SEMPRE que for criar ou alterar qualquer interface, página, componente, peça visual ou material de marca da T2 — cores, tipografia, espaçamento, layout, ícones (Phosphor), motion, tom de voz e regras de marca.
---

# DS-T2 — Design System T2 Educação (dark-only)

Fonte da verdade consolidada em 2026-07-17 a partir do site em produção (t2.com.br, `site/app/globals.css`).

| Referência | Quando abrir |
|---|---|
| [references/tokens.css](references/tokens.css) | Copiar as variáveis CSS pra um projeto novo |
| [references/components.md](references/components.md) | Construir botão, card, seção, heading, badge — receitas com código real do site |
| [references/icons.md](references/icons.md) | Qualquer trabalho com ícones (Phosphor: pesos, SSR, mapa lucide→Phosphor) |

## Como trabalhar (workflow)

1. **Contexto antes de pixel**: defina audiência, objetivo da página e a ÚNICA ação principal antes de desenhar. Cada tela tem um CTA dominante; o resto é apoio.
2. **Estrutura antes de estilo**: hierarquia de informação primeiro (o que o olho vê em 1s, 5s, 30s), depois cor e decoração.
3. **Monte com os tokens e receitas** deste DS. Nunca invente cor, fonte, tamanho ou raio fora das escalas.
4. **Audite no final** com o checklist da última seção (e `/impeccable audit` se o impeccable estiver instalado).

## Quem é a T2

Preparatório online de certificações financeiras desde 2016. Visão: 10 milhões de alunos até 2034. Site: t2.com.br. NPS 91, +120 mil profissionais formados.

**Tom de voz**: profissional e acessível (sem juridiquês), direto e prático (fala do que muda na vida do aluno), humano e confiante (incentiva sem prometer resultado mágico). Frase canônica: *"Desde 2016, preparando os melhores profissionais para o mercado financeiro."*

**Padrões de copy que funcionam na T2**:
- Headline = transformação, não feature: "vire especialista em investimentos e lidere pela técnica" (não "curso com 190 aulas").
- Benefício antes de mecânica: "É o primeiro passo para ser escolhido pelo mercado" e só depois o como.
- Prova social específica: "+120 mil profissionais evoluíram com a T2", "NPS 91: nossos alunos recomendam".
- Garantia sem burocracia: "sem perguntas incômodas, sem burocracia".
- Voltado ao leitor: "você aprende", "você chega preparado" — nunca "nós oferecemos".

## Regras de marca — NUNCA quebre

- **Certificações**: só `CPA`, `CPRO-R`, `CPRO-I`, `CFP®`. NUNCA: CPA-10, CPA-20, CEA, CGA (descontinuadas), Pós-Graduação/Graduação (a T2 não tem). Grafia com hífen permitida só em nomes próprios: CPRO-R, CPRO-I, HP-12C.
- **Sem traço como conector de frase**: nunca `-`, `–` ou `—` ligando orações em conteúdo. Reescreva com vírgula, dois-pontos ou ponto.
- **Sem emojis** em materiais de marca.
- **Claims proibidos**: "corrigimos a banca/prova", "simulados ao vivo com profissionais", "mentoria semanal", quantidades fixas de questões (ex.: "240 questões"). Pode dizer: "preparatório com equipe acadêmica dedicada", "certificações ativas no mercado financeiro", "conteúdo prático e atualizado", "simulados ilimitados".
- **Logo**: sem gradiente, sem sombra/glow, respiro mínimo de 1× a altura do símbolo (2× em heros), mínimo 24px de altura em digital. Em fundo escuro use a variação negativa (branco + acento ciano); em selos, stamp só branco.

## Cores (tema dark — único tema)

Nenhuma cor fora desta paleta. Em código de componente, nunca hex solto: sempre token/variável (no site, a paleta default do Tailwind está desativada de propósito).

### Marca

| Token | HEX | Uso |
|---|---|---|
| `--t2-blue` (primário) | `#0097D9` | CTAs, links, destaques de marca |
| `--t2-dark` | `#001424` | Azul-marinho institucional (footer) |
| `--t2-cyan` (acento) | `#36C5FA` | Acento vivo, info, ícones, hover, seleção |
| `--t2-yellow` | `#FEE575` | Destaques e hovers |
| `--t2-teal` | `#36efc7` | Verde-menta terciário (checks em fundos escuros) |
| `--t2-green` | `#1FA98A` | Sucesso, aprovação |
| `--t2-amber` | `#E0A93C` | Atenção, alerta suave |
| `--t2-violet` | `#7B5BD6` | Premium, certificações |
| `--t2-coral` | `#E8663D` | Urgência, promoções |
| `--whatsapp` | `#25D366` | SÓ em CTAs de WhatsApp |

### Brand scale (ancorada no Curious-Blue)

`50 #f0faff · 100 #dff4fe · 200 #b8e8fd · 300 #7dd8fc · 400 #36c5fa · 500 #0097D9 (primário) · 600 #007ab8 (hover) · 700 #065e86 · 800 #07314a · 900 #052539 · 950 #021015`

### Superfícies (família Dark Knight)

| Token | HEX | Uso |
|---|---|---|
| `--bg` | `#171b2f` | Fundo principal (e `themeColor` do site) |
| `--bg-2` | `#1c2138` | Seções alternadas |
| `--bg-3` | `#232a47` | Cards, inputs |
| `--bg-4` | `#2a3255` | Hover de itens |
| `--fg` | `#f8f9fc` | Texto principal |
| `--fg-2` | `#b8c0d4` | Texto secundário |
| `--fg-3` | `#7a8298` | Placeholder, texto mudo |
| `--border` | `#2f3654` | Bordas padrão |
| `--border-strong` | `#3e4670` | Bordas de destaque |
| `--accent` | `#36c5fa` | Acento (= t2-cyan) |
| `--accent-ink` | `#8fdcff` | Texto de link sobre fundo escuro |
| `--accent-soft` | `#07314a` | Fundo suave do acento |

Truque recorrente no site: sobre fundos escuros, cards e bordas também usam alpha de branco: `border-white/10`, `bg-white/[0.025]`, texto `text-white/65`. É permitido e idiomático.

### Semânticas (soft = fundo ESCURO da cor, nunca pastel claro)

`--success #059669` / `--success-soft #06402b` · `--warning #d97706` / `--warning-soft #46320a` · `--danger #dc2626` / `--danger-soft #450e0e`

### Acento por página (site)

Cada página de produto tem uma cor de acento própria, usada em CTAs (`CTAButton color=`), selos e detalhes. O resto da página continua nos tokens neutros.

| Página | Acento |
|---|---|
| CPA | `#00E676` |
| CPRO-R (e módulo) | `#1D69C7` |
| CPRO-I | `#F2921C` |
| CFP® | `#878787` |
| ANCORD | `#00A7D0` |
| Assinatura | `#0097D9` (primário) |

Página nova de produto: escolha UM acento (idealmente da paleta de marca), exporte como `<PAGINA>_ACCENT` no `content/<pagina>.ts` e use consistente na página inteira.

## Tipografia

Só **Geist** (sans) e **JetBrains Mono** (mono). Nenhuma outra fonte, nunca. No Next, Geist self-hosted via `next/font` (nada de fonte externa por CWV).

| Nome | px | lh | Uso |
|---|---|---|---|
| caption | 12 | 1.45 | Labels, badges |
| body-sm | 13 | 1.55 | Textos auxiliares |
| body | 15 | 1.60 | Corpo padrão |
| body-lg | 16 | 1.55 | Corpo de destaque |
| h6 | 16 | 1.40 | Títulos menores |
| h5 | 18 | 1.35 | Subtítulos de seção |
| h4 | 22 | 1.30 | Títulos de card |
| h3 | 28 | 1.20 | Títulos de seção |
| h2 | 36 | 1.10 | Títulos de página |
| h1 | 48 | 1.05 | Hero |
| display | 76 | 0.96 | Landing, capa |
| display-xl | 150 | 0.95 | SÓ números/heros gigantes (ex.: 404) |

**Pesos — regra do Rafael (inegociável)**: corpo em **regular (400)**; títulos até **semibold (600)**; medium (500) para labels/UI; **bold (700) quase nunca** (só micro-elementos tipo número de destaque). Se o layout parece fraco sem bold, o problema é hierarquia/tamanho, não peso.

Títulos grandes (h1/display) levam `tracking-tight`. Uppercase só em labels/eyebrows pequenos com `tracking-wide`.

## Layout e ritmo

- **Container**: `mx-auto w-[89%] max-w-[1720px]` — a MESMA largura do header, sempre. Nunca crie outro container.
- **Seção**: `py-16 md:py-24`. Alterne fundos `bg` → `bg-2` entre seções pra criar ritmo; nunca duas `bg-2` coladas.
- **Ordem canônica de página de produto**: hero → prova social → dor/promessa → método → currículo/módulos → preço (`#matricula`) → garantia → FAQ → SupportCta. **SupportCta vem SEMPRE abaixo do FAQ.**
- **Espaçamento base-4**: `4 · 8 · 12 · 16 · 20 · 24 · 28 · 32 · 40 · 48 · 56 · 64 · 80 · 96 · 128px`. Dentro de card: 24–28px de padding (p-6/p-7).
- **Raios**: xs 4 (badges) · sm 6 (inputs) · md 8 (botões) · lg 12 (cards) · xl 16 (cards grandes) · 2xl 24 (painéis) · pill 999 (tags marketing).
- Grids de cards: `gap-4`/`gap-6`; feature cards podem variar de span pra quebrar monotonia (bento), mas no máximo 2 tamanhos de célula.

## Ícones — Phosphor (phosphoricons.com)

- Biblioteca única: **Phosphor**. Em React: `@phosphor-icons/react`. Proibido lucide, heroicons, react-icons, font-awesome ou SVG avulso de outra família.
- **Peso padrão: `regular`** (default, não passe `weight`). `weight="fill"` para estados ativos/avaliações (estrelas, play). `weight="bold"` para checks pequenos que precisam de presença (padrão do site em listas de features).
- Tamanhos: 16 (inline), 20 (UI), 24 (destaque), 32+ (feature cards). Ícone decorativo gigante de fundo: `size-28 text-white/[0.035]` (marca d'água).
- Cor sempre via `currentColor` herdando classe de texto do DS.
- **Next.js**: server components importam de `@phosphor-icons/react/dist/ssr`; client components de `@phosphor-icons/react`. Tipo: `import type { Icon } from "@phosphor-icons/react"`.
- Detalhes e mapa lucide→Phosphor: [references/icons.md](references/icons.md).

## Motion

- Easings: `--ease-standard cubic-bezier(0.2,0,0,1)` (padrão) · `--ease-emphasis cubic-bezier(0.3,0,0,1)` (entradas de destaque). Durações: 120ms (hover), 160ms (padrão), 240ms (painéis). **Nunca bounce/elastic.**
- Micro-interações do site: hover de card `hover:-translate-y-1` + borda acesa; seta de CTA `group-hover:rotate-45`; efeito magnético (`Magnetic`) só em CTAs grandes.
- Reveal on scroll: uma vez só, curto (300–500ms), nunca esconde conteúdo de quem chega por âncora. Headings de seções críticas (preço, garantia) revelam imediatamente.
- **GSAP/ScrollTrigger** (site): pin horizontal SÓ em `md+`; no mobile, empilhe sem animação. Glows/decorações absolutas exigem `overflow-x-clip` no pai (senão criam scroll horizontal). Depois de layout dinâmico, use o `ScrollRefresh`.
- Sempre respeite `motion-reduce:transition-none` / `prefers-reduced-motion`.

## Regras de engenharia (projetos React/Next da T2)

- Só tokens do DS: nada de hex/`rgb()` em componente, `style={{ color }}` só para acento dinâmico de página (`card.accent`), nunca cor arbitrária tipo `bg-[#00A4E0]`.
- Zero texto hardcoded em página: conteúdo vive em `content/<pagina>.ts` tipado; componente recebe props.
- Server Component por padrão; `"use client"` só em folha pequena com estado/efeito.
- Componente nunca passa de 200 linhas; sem comentários no código (nomes são a documentação).
- Toda ação rastreável usa `trackKey` do mapa central `lib/tracking.ts` (padrão `site_<pagina>_<secao>_<acao>`); nunca `posthog.capture`/`gtag` direto.
- Imagens via `next/image` com `alt` descritivo; hero com `priority`; dimensões sempre definidas (zero layout shift).

## Camada de qualidade — impeccable + auditoria final

A T2 adota o [impeccable](https://github.com/pbakaus/impeccable) como padrão de qualidade. Se instalado, rode `/impeccable audit` no resultado. Instalado ou não, passe este checklist antes de entregar:

**Cor e contraste**
- [ ] Nenhuma cor fora da paleta; nenhum hex solto em componente.
- [ ] Nunca texto cinza sobre fundo colorido (escureça/clareie a cor do próprio fundo).
- [ ] Nunca preto `#000` ou cinza puro; use as superfícies do DS.
- [ ] Texto sobre `bg`/`bg-2` usa `fg`/`fg-2`/`fg-3`, nunca opacidade menor que `/60` pra texto que importa.

**Hierarquia e layout**
- [ ] Um único CTA dominante por tela; hierarquia clara em 1 segundo.
- [ ] Nenhum card dentro de card.
- [ ] Container e ritmo de seção respeitados; sem scroll horizontal em nenhum breakpoint.
- [ ] Mobile revisado: nav não sobrepõe título, cards não cortam, stats quebram linha.

**Tipografia**
- [ ] Só Geist/JetBrains Mono; tamanhos só da escala; corpo 400, títulos ≤600.
- [ ] Exatamente 1 `<h1>` por página; hierarquia sem pular níveis.

**Marca e conteúdo**
- [ ] Certificações válidas; sem claims proibidos; sem emoji; sem traço conectando orações.
- [ ] Copy voltada ao leitor, benefício antes de feature.

**Motion e ícones**
- [ ] Easings/durações do DS; sem bounce; `motion-reduce` respeitado.
- [ ] Só Phosphor, peso certo, cor via token.

## Princípios do DS

1. **Clareza** — informação primeiro, decoração depois. Se não comunica, não existe.
2. **Acolhimento no rigor** — técnico mas humano, sem jargão de banca.
3. **Progresso visível** — cada elemento aponta o próximo passo.
4. **Aplicação prática** — exemplo antes de definição, caso real antes de teoria.
