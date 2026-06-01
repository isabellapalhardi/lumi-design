# lumi · Tokens do Design System

> Direção visual: **mineral e quente**. Brasileiro sem caricatura.
> Documento gerado a partir do `brand-system-claude-code.md` (Blocos 2–4). Valores **travados**.

---

## Regra de ouro do coral

> O **coral** (`--brand`) vive **apenas na estética**: sidebar, wordmark, botão primário, micro-detalhes.
>
> Em informação **funcional** — stats, badges, títulos de seção, alertas — usa-se a **paleta semântica por domínio** (care · attention · regulatory). **Nunca o coral.**

Se em algum momento o coral aparecer num stat-card, badge, status-dot ou alerta, está errado.

---

## Tema claro

| Token | Valor | Função |
|---|---|---|
| `--brand` | `#C46850` | Coral terroso — brand, primário, sidebar accent, micro-detalhes |
| `--brand-strong` | `#8A3D2A` | Terracota — hover/acento do coral |
| `--bg` | `#FBF6EE` | Fundo do conteúdo (miolo) |
| `--surface` | `#FFFFFF` | Cards e superfícies de leitura |
| `--sidebar` | `#ECE0CC` | Sidebar e chips secundários |
| `--text` | `#2D231D` | Carvão quente — texto principal |
| `--text-muted` | `rgba(45,35,29,0.62)` | Texto secundário (derivado) |
| `--text-faint` | `rgba(45,35,29,0.40)` | Labels e dicas (derivado) |
| `--divider` | `rgba(45,35,29,0.08)` | Divisor neutro (derivado) |

## Tema escuro

| Token | Valor | Função |
|---|---|---|
| `--brand` | `#C46850` | Mantém o coral |
| `--brand-soft` | `#E8B4A3` | Texto de destaque em fundo escuro |
| `--bg` | `#14110F` | Fundo |
| `--surface` | `#1F1A17` | Cards |
| `--sidebar` | `#221C18` | Sidebar |
| `--text` | `#F1E6D6` | Texto principal |

---

## Paleta semântica (cor encoda significado, não estética)

| Domínio | Quando usar | Base (claro/escuro) | Fill (claro/escuro) |
|---|---|---|---|
| **care** | Tratamento, saúde, sucesso, "deu certo" | `#7E9170` / `#A8BD96` | `#D8E0D0` / `rgba(126,145,112,0.13)` |
| **attention** | Tempo, atenção, financeiro, urgência leve | `#C99853` / `#E0B070` | `#F5DCAE` / `rgba(201,152,83,0.13)` |
| **regulatory** | Regulação, prescrição, info neutra, Anvisa | `#707682` / `#A8AEBA` | `#D5D8DE` / `rgba(112,118,130,0.16)` |

### Mapeamento PT → token

| Em português | Token |
|---|---|
| Tratamento / saúde / sucesso | `care` |
| Tempo / atenção / financeiro | `attention` |
| Regulação / prescrição / Anvisa / info | `regulatory` |

### Exemplos de uso

- **Stat "Tratamento · 6 meses"** → `stat-card--care`
- **Stat "Autorização Anvisa vence em 18 dias"** → `stat-card--attention` (o dominante é tempo)
- **Stat "Pedidos · 4"** → `stat-card--regulatory` (info neutra contábil)
- **Badge "Entregue"** → `badge--care`
- **Badge "Em trânsito"** → `badge--attention`
- **Badge "Anvisa autorizada"** → `badge--regulatory`
- **Alerta de vencimento** → `alert--attention`
- **Erro de regulação** → `alert--regulatory`

---

## Raios

| Token | Valor | Uso |
|---|---|---|
| `--radius-card` | `16px` | Cards, alertas, tabela (wrap) |
| `--radius-pill` | `999px` | Botões, badges, avatars, status dots, links de sidebar |
| `--radius-input` | `10px` | Inputs e elementos retangulares menores |

**Regra:** botões e badges são **pílula**. Cards são **16px**. Elementos circulares (avatar, status-dot, chip) ficam totalmente arredondados.

---

## Tipografia

| Token | Valor | Onde aplicar |
|---|---|---|
| `--font-serif` | `"Source Serif 4"` | **Apenas** wordmark/logo e materiais de marketing. Nunca na UI funcional. |
| `--font-sans` | `"Inter"` | Toda a UI funcional. |

### Pesos do Inter

| Peso | Onde |
|---|---|
| 400 | Corpo de texto |
| 500 | Labels, valores em destaque, nomes |
| 600 | Títulos de seção, ênfase, números grandes em stat-card |
| 700 | Reservado, raro |

### Por que Source Serif só no wordmark

Decisão testada e travada: serifada em UI densa fica datada e atrapalha leitura.
O serif aparece com optical-sizing automático nos lugares que **são** marca (wordmark grande), nunca em headers ou corpo de tabela.

---

## Componentes-primitiva (regras de identidade)

| Componente | Regra |
|---|---|
| **Button** | Pílula (`--radius-pill`). `btn--primary` usa `--brand`, hover `--brand-strong`. Stats nunca usam botão coral. |
| **Card** | `--radius-card` (16px), `--surface`, sombra sutil, divisor 0.5px se houver. |
| **Badge** | Pílula, paleta **semântica**, sem borda. |
| **StatCard** | Faixa fininha colorida no topo (3px) com cor do domínio. Número grande tabular. Nunca coral. |
| **StatusDot** | Círculo 8px. Pode pulsar (estado ativo). Cor da paleta semântica. |
| **Avatar** | Círculo. Pode usar tom da paleta semântica como background discreto. |
| **Sidebar** | Fundo `--sidebar`. Wordmark em serif. Links em pílula. Link ativo usa `--brand`. |
| **Alert** | 16px radius. Fill da paleta semântica. Sem borda. Ícone em círculo branco translúcido. |
| **Table** | Sem borda externa exceto 0.5px do wrap. Sem zebra. Divisores 0.5px. Hover row sutil. |

**SEM borda** em elemento colorido — fundo de baixa opacidade se sustenta sozinho.
**Borda só 0.5px** e só em divisor neutro (linhas de tabela, separador de card branco, divisor de seção).

---

## Espaçamento (escala 4)

```
--space-1: 4px    --space-5: 24px
--space-2: 8px    --space-6: 32px
--space-3: 12px   --space-7: 48px
--space-4: 16px   --space-8: 64px
```

---

## Motion

| Token | Valor | Quando |
|---|---|---|
| `--duration-fast` | `140ms` | Hover, focus, toggle |
| `--duration-base` | `220ms` | Transição de tema, reveal |
| `--ease-out` | `cubic-bezier(0.16, 1, 0.3, 1)` | Padrão |

Reveal escalonado no page-load (60ms de delay incremental) para sensação de entrada cuidada. Respeita `prefers-reduced-motion`.

---

## Detalhe assinatura · grão mineral

O `body::before` aplica uma textura SVG de ruído fractal sutil (`opacity: 0.42`, `mix-blend-mode: multiply` no claro, `screen` no escuro). É o **toque mineral**: nada que o usuário note conscientemente, mas que dá "matéria" ao fundo e diferencia de um SaaS B2B genérico.

Se for irritar em telas com gráficos detalhados, basta `body::before { display: none }`.

---

## Hierarquia de validação

A tela `pages/pro-paciente.html` é a **prova de carga** do sistema: foi escolhida por ser a página mais densa e de uso mais intenso. Se o sistema aguenta ela em claro e escuro com legibilidade impecável, aguenta qualquer outra.
