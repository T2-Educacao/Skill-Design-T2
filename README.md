<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://t2.com.br/brand/horizontal-negativa.png">
  <img src="https://t2.com.br/brand/horizontal-padrao.png" alt="T2 Educação" width="420">
</picture>

# Skill Design T2

**Design system da T2 Educação empacotado como skill de IA — DS-T2 Clareza, dark-only**

[![Skill](https://img.shields.io/badge/Claude_Code-skill-d97757?style=flat-square&logo=anthropic&logoColor=white)](https://docs.anthropic.com/en/docs/claude-code)
[![Phosphor](https://img.shields.io/badge/Phosphor-icons-3d2eff?style=flat-square)](https://phosphoricons.com)
[![impeccable](https://img.shields.io/badge/impeccable-quality_layer-black?style=flat-square&logo=github&logoColor=white)](https://github.com/pbakaus/impeccable)
[![Dark only](https://img.shields.io/badge/theme-dark--only-171b2f?style=flat-square)](#cores)

</div>

---

## O que é

A fonte da verdade do design da T2 em formato que agentes de IA (e humanos) consomem direto: cores, tipografia, layout, ícones, motion, tom de voz e regras de marca num único pacote. Consolidada a partir do site em produção ([t2.com.br](https://t2.com.br)) e usada como skill do Claude Code (`/t2-design`) em qualquer projeto da T2.

Qualquer interface, página, componente ou material de marca da T2 nasce seguindo este DS. Em conflito com documentação antiga, **valem os valores daqui**.

### O que tem

| Arquivo | O que faz |
|---------|-----------|
| [`SKILL.md`](SKILL.md) | A skill: workflow, paleta, tipografia, layout, marca, motion, regras de engenharia e checklist de auditoria |
| [`references/tokens.css`](references/tokens.css) | Variáveis CSS prontas pra copiar no `:root` de qualquer projeto T2 |
| [`references/components.md`](references/components.md) | Receitas de componentes com código real do site: botões, cards, seções, badges, forms |
| [`references/icons.md`](references/icons.md) | Guia de ícones Phosphor: pesos, imports SSR/client e mapa lucide → Phosphor |

---

## Cores

Tema **dark-only**, família Dark Knight, primário Curious-Blue.

| | Token | HEX | Uso |
|---|-------|-----|-----|
| ![#0097D9](https://placehold.co/16x16/0097D9/0097D9.png) | `--t2-blue` | `#0097D9` | Primário: CTAs, links, destaques |
| ![#36C5FA](https://placehold.co/16x16/36C5FA/36C5FA.png) | `--t2-cyan` | `#36C5FA` | Acento vivo, ícones, hover |
| ![#001424](https://placehold.co/16x16/001424/001424.png) | `--t2-dark` | `#001424` | Institucional (footer) |
| ![#171b2f](https://placehold.co/16x16/171b2f/171b2f.png) | `--bg` | `#171b2f` | Fundo principal |
| ![#FEE575](https://placehold.co/16x16/FEE575/FEE575.png) | `--t2-yellow` | `#FEE575` | Destaques e hovers |
| ![#1FA98A](https://placehold.co/16x16/1FA98A/1FA98A.png) | `--t2-green` | `#1FA98A` | Sucesso, aprovação |
| ![#7B5BD6](https://placehold.co/16x16/7B5BD6/7B5BD6.png) | `--t2-violet` | `#7B5BD6` | Premium, certificações |
| ![#E8663D](https://placehold.co/16x16/E8663D/E8663D.png) | `--t2-coral` | `#E8663D` | Urgência, promoções |

Paleta completa (brand scale 50–950, semânticas, superfícies e acentos por página) no [`SKILL.md`](SKILL.md).

---

## Fundamentos

```
Tipografia     →  Geist (sans) + JetBrains Mono · corpo 400, títulos até 600, bold quase nunca
Escala         →  caption 12 … body 15 … h1 48 … display 76 (display-xl 150 só pra números gigantes)
Espaçamento    →  base-4 (4 · 8 · 12 … 128px)
Raios          →  xs 4 · md 8 (botões) · lg 12 (cards) · pill 999
Ícones         →  Phosphor, peso regular · SSR: @phosphor-icons/react/dist/ssr
Motion         →  cubic-bezier(0.2,0,0,1) · 120/160/240ms · nunca bounce
Layout         →  Container w-[89%] max-w-[1720px] · seções py-16 md:py-24 alternando bg/bg-2
Qualidade      →  anti-patterns do impeccable + checklist de auditoria embutido
```

---

## Como usar

### Como skill do Claude Code

No monorepo da T2 a skill já está registrada (loader em `.claude/skills/t2-design/`). Em outro projeto:

```bash
git clone https://github.com/T2-Educacao/Skill-Design-T2.git .claude/skills/t2-design
```

O agente invoca `/t2-design` (ou carrega sozinho ao mexer em UI) e segue as regras à risca.

### Como referência manual

Cole o [`SKILL.md`](SKILL.md) no início da conversa com qualquer IA, ou copie o [`references/tokens.css`](references/tokens.css) pro `:root` do projeto novo.

---

## Regras que nunca quebram

1. Nenhuma cor fora da paleta; nenhum hex solto em componente (só tokens)
2. Só Geist e JetBrains Mono; corpo regular, títulos até semibold
3. Certificações: só `CPA` · `CPRO-R` · `CPRO-I` · `CFP®` (nunca CPA-10/20, CEA, CGA, pós/graduação)
4. Sem emoji e sem traço como conector de frase em conteúdo de marca
5. Só ícones Phosphor, peso regular por padrão
6. Nunca texto cinza sobre fundo colorido, card dentro de card, preto puro ou bounce easing
7. Um único CTA dominante por tela

---

## Relacionados

- [`site/DESIGN.md`](https://t2.com.br) — DS-T2 Clareza v1.0 original (este repo é a versão consolidada)
- [impeccable](https://github.com/pbakaus/impeccable) — camada de qualidade de design adotada pela T2
- [Phosphor Icons](https://phosphoricons.com) — biblioteca oficial de ícones
