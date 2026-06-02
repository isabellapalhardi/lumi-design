# lumi · design

Brand system e mockups visuais da plataforma **lumi** — SaaS de cannabis medicinal.

Mockups estáticos em HTML/CSS, sem dependências de build. Abra `index.html` no navegador.

## Direção visual

**Mineral e quente.** Brasileiro sem caricatura.

- **Coral terroso** (`#C46850`) vive só na estética — wordmark, sidebar, botão primário.
- **Paleta semântica** (care, attention, regulatory) carrega informação funcional — stats, badges, alertas. Nunca coral.
- **Tema claro e escuro** nativos.
- **Inter** na UI, **Source Serif 4** apenas no wordmark/marca.

Detalhes em [`TOKENS.md`](./TOKENS.md).

## Estrutura

```
lumi-design/
├── index.html              # menu das telas
├── pages/
│   └── login.html          # tela de login (fechada)
├── styles/
│   ├── tokens.css          # cores, raios, tipografia, claro/escuro
│   └── components.css      # Button, Card, Badge, StatCard, Avatar, Sidebar, Form
└── TOKENS.md               # documentação do design system
```

## Telas

| # | Tela | Status |
|---|------|--------|
| 01 | `pages/login.html` | **Fechado** — moldura coral, painel em vidro fosco, wordmark central, form com border coral |
| 02 | `pages/dashboard.html` | **Fechado** — início do admin · sidebar + topbar + saudação + stats semânticos + alerta Anvisa + pipeline do módulo Pro + lista de atenção + atividade recente |
| 03 | `pages/pacientes.html` | **Fechado** — lista de pacientes · toggle grade ↔ tabela (persistido em localStorage) · busca + filtros por estágio · pulso de alerta nos vencimentos urgentes |
| 04 | `pages/paciente-detalhe.html` | **Fechado** — detalhe denso da paciente · identidade + badges + ações · stats semânticos · alerta crítico Anvisa · prescrição + linha do tratamento · histórico de pedidos |
| 05 | `pages/paciente-novo.html` | **Fechado** — form multi-step de cadastro (4 etapas) · stepper visual · radio pills · auto-save · footer com Voltar/Próximo |
| 06 | `pages/pedidos.html` | **Fechado** — lista de pedidos · 4 mini-stats · toggle grade/tabela · cards com mini-timeline horizontal de 6 estágios + produto destacado com border-left coral |

Próximas telas a desenhar entram via `pages/` conforme avançamos.

## Como abrir

Localmente, qualquer servidor HTTP estático serve:

```bash
# com node:
npx http-server -p 8765

# ou direto file:// (alguns navegadores bloqueiam — prefere o servidor)
```

Abra `http://localhost:8765/` ou clique em `index.html` direto se seu navegador permitir.
