# Ícones T2 — Phosphor

Biblioteca única de ícones da T2: [Phosphor](https://phosphoricons.com/). Em React use `@phosphor-icons/react`.

## Regras

- **Peso padrão: `regular`** (default, não passe `weight`). `weight="fill"` só para estados ativos e avaliações (estrelas preenchidas). `weight="bold"` só em micro-ícones ≤14px.
- Tamanhos: 16 (inline no texto) · 20 (UI padrão) · 24 (destaque) · 32+ (feature cards).
- Cor via `currentColor`: aplique classe de texto do DS no ícone ou no pai (`className="text-accent"`), nunca hex.
- Phosphor não tem `strokeWidth` (isso é lucide): o traço é controlado por `weight`.

## Next.js App Router

```tsx
// Server component (sem "use client") — evita bundle client
import { CheckCircle, ArrowUpRight } from "@phosphor-icons/react/dist/ssr";

// Client component ("use client")
import { CaretDown } from "@phosphor-icons/react";

// Tipo (equivale ao antigo LucideIcon)
import type { Icon } from "@phosphor-icons/react";
const ICONS: Icon[] = [CheckCircle, ArrowUpRight];
```

## Mapa lucide → Phosphor (nomes usados no site)

| lucide | Phosphor |
|---|---|
| Activity | Pulse |
| ArrowDownRight / ArrowRight / ArrowUpRight | (iguais) |
| Award | Medal |
| BadgeCheck | SealCheck |
| Ban | Prohibit |
| BookOpen | BookOpen |
| Brain | Brain |
| Briefcase | Briefcase |
| Building2 | Buildings |
| Calculator | Calculator |
| CalendarDays | CalendarDots |
| Check | Check |
| CheckCircle2 | CheckCircle |
| ChevronDown | CaretDown |
| ChevronRight | CaretRight |
| Clock | Clock |
| CreditCard | CreditCard |
| DollarSign | CurrencyDollar |
| FileSpreadsheet | FileXls |
| Flag | Flag |
| FolderOpen | FolderOpen |
| Gauge | Gauge |
| Gift | Gift |
| GraduationCap | GraduationCap |
| HelpCircle | Question |
| Landmark | Bank |
| Layers | Stack |
| Lightbulb | Lightbulb |
| LineChart | ChartLine |
| ListChecks | ListChecks |
| Loader2 | CircleNotch (com `animate-spin`) |
| Lock | Lock |
| Mail | EnvelopeSimple |
| Menu | List |
| MessageCircle | ChatCircle |
| MessageSquare | ChatText |
| Phone | Phone |
| PieChart | ChartPie |
| Play | Play |
| PlayCircle | PlayCircle |
| Receipt | Receipt |
| RefreshCw | ArrowsClockwise |
| ScrollText | Scroll |
| Send | PaperPlaneTilt |
| Shield | Shield |
| ShieldAlert | ShieldWarning |
| ShieldCheck | ShieldCheck |
| Star | Star |
| Target | Target |
| TrendingUp | TrendUp |
| User / UserCheck / Users | (iguais) |
| Wallet | Wallet |
| Wrench | Wrench |
| X | X |
| `type LucideIcon` | `type Icon` |
