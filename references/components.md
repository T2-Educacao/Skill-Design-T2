# Receitas de componentes T2

Padrões extraídos do site em produção (`site/components/`). Ao trabalhar NO site, use os componentes prontos de `components/ui/` — nunca recrie. Fora do site, use estas receitas como referência de estilo.

## Container e Section (esqueleto de toda página)

```tsx
// Container — mesma largura do header, SEMPRE
<div className="mx-auto w-[89%] max-w-[1720px]">…</div>

// Section — ritmo vertical + alternância de fundo
<section className="py-16 md:py-24">…</section>
<section className="bg-bg-2 py-16 md:py-24">…</section>  // variante alternada
```

No site: `<Container>` e `<Section variant="default" | "alt">` de `components/ui/`.

## Heading

Escala mapeada pra classes, sempre semibold (500 nos menores):

```tsx
<Heading as="h1">…</Heading>            // text-h1 font-semibold tracking-tight
<Heading as="h2" size="h3">…</Heading>  // tag semântica ≠ tamanho visual quando preciso
```

Padrão de cabeçalho de seção: eyebrow (caption, uppercase, tracking-wide, cor de acento) + título (h2/h3, semibold) + descrição (`text-fg-2`, máx. ~60ch).

## Botões

### Button (UI geral — 4 variantes)

```
primary:   bg-brand-500 text-white hover:bg-brand-600
secondary: border border-border-strong text-fg hover:bg-bg-3
ghost:     text-fg-2 hover:bg-bg-3 hover:text-fg
ink:       bg-fg text-bg hover:bg-fg-2
```

Base comum: `inline-flex items-center gap-2 rounded-md font-semibold transition-colors duration-150 ease-standard focus-visible:ring-3 focus-visible:ring-accent/40 disabled:opacity-50`.

Tamanhos: sm `px-3 py-1.5 text-caption` · md `px-4.5 py-2.5 text-body-sm` · lg `px-5.5 py-3 text-body` · xl `px-7 py-4 text-body-lg`. Em lg/xl, envolva com `<Magnetic>`.

Todo botão de ação real leva `trackKey`.

### CTAButton (CTA de marketing com acento de página)

Anatomia: wrapper `Magnetic` com borda 2px na cor de acento + link interno com fundo no acento, texto preto uppercase semibold, e círculo com `ArrowUpRight` que gira 45° no hover:

```tsx
<a className="group flex items-center gap-3 rounded-lg border-2 border-black px-5 py-3.5
              text-[14px] font-semibold uppercase tracking-wide text-black"
   style={{ backgroundColor: accent }}>
  {label}
  <span className="flex size-7 items-center justify-center rounded-full border-2 border-black
                   transition-transform duration-200 group-hover:rotate-45">
    <ArrowUpRight className="size-4" />
  </span>
</a>
```

`style={{ backgroundColor }}` aqui é a EXCEÇÃO permitida: acento dinâmico vindo de `content/`.

## Cards

### Card padrão (dark, com hover)

```tsx
<div className="group relative flex flex-col overflow-hidden rounded-2xl
                border border-white/10 bg-white/[0.025] p-7
                transition-all duration-300 will-change-transform
                hover:-translate-y-1 hover:border-brand-500/40 hover:bg-white/[0.045]
                motion-reduce:transition-none">
```

Elementos internos idiomáticos:
- **Chip de ícone**: `flex size-11 items-center justify-center rounded-xl border border-brand-500/20 bg-brand-500/10 text-t2-cyan` com Phosphor `size-5` dentro.
- **Marca d'água**: mesmo ícone gigante decorativo `absolute -right-5 -top-5 size-28 text-white/[0.035]` + `group-hover:scale-110`, sempre `aria-hidden`.
- Título `text-[18px] font-semibold text-white`, descrição `text-white/65`.

### Lista de features com check

```tsx
<li className="flex items-start gap-2">
  <CheckCircle className="mt-0.5 size-4 shrink-0" weight="bold" style={{ color: accent }} />
  {feature}
</li>
```

Check verde `#00E676` nas comparações da CPA; `--t2-teal` em fundos escuros; `text-success` em contexto semântico.

### Card em superfície (sem alpha)

Para conteúdo denso (FAQ, pricing): `rounded-lg border border-border bg-bg-3 p-6`. Hover: `hover:bg-bg-4`.

## Badges e selos

- Badge informativo: `rounded-[4px] bg-accent-soft px-2 py-0.5 text-caption font-medium text-accent-ink`.
- Badge de prova social (garantia): texto curto e específico ("NPS 91: nossos alunos recomendam").
- Tag pill de marketing: `rounded-full border border-white/15 px-3 py-1 text-caption uppercase tracking-wide`.
- Selos de certificação (ANBIMA): imagens de `public/courses/`, nunca redesenhe.

## Formulários

- Input: `rounded-sm border border-border bg-bg-3 px-3.5 py-2.5 text-body text-fg placeholder:text-fg-3 focus-visible:ring-3 focus-visible:ring-accent/40`.
- Label: `text-body-sm font-medium text-fg-2`.
- Erro: borda e texto `danger`, fundo `danger-soft`; mensagem curta e humana.
- Sucesso de captura: pode comemorar (o site usa confetti), mas sem bloquear o próximo passo.

## Seções recorrentes

- **Hero de produto**: social proof (linha pequena) → h1 com transformação → subtítulo em 2 tons (`lead` + `strong`) → preço (12x + PIX) → CTA com acento da página.
- **Pricing (`#matricula`)**: eyebrow "Matrícula" → heading → descrição com prazo de acesso → card de compra com features + garantia logo abaixo.
- **Garantia**: badge NPS → "15 dias para testar sem risco" → parágrafo sem burocracia.
- **FAQ**: cards accordion (client component folha); dados descem de `content/`. SupportCta SEMPRE depois.
- **Combos**: cards com selos das certificações, parcelado + à vista, prazo de acesso, `buyTrackKey`.

## Efeitos especiais (usar com parcimônia)

- `Magnetic` — só CTAs grandes (strength ~0.18).
- `MovingBorderButton` — borda animada em CSS puro pra CTA de máximo destaque (1 por página).
- Glows de fundo — `absolute` + blur grande na cor de acento com alpha baixo; o PAI precisa de `overflow-x-clip`.
- `CountUp` — números de prova social.
- Scrollbar custom já vem dos tokens (thumb `brand-500`, hover `accent`).

## Acessibilidade (mínimo obrigatório)

- Decorativos: `aria-hidden`. Ícone informativo sem texto: `aria-label`.
- Foco visível em tudo que é interativo (ring padrão do DS).
- Contraste AA: texto essencial nunca abaixo de `white/65` sobre `bg`.
- `motion-reduce` em toda animação; reveal nunca esconde conteúdo permanentemente.
