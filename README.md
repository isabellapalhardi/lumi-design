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
| 07 | `pages/pedido-detalhe.html` | **Fechado** — detalhe do pedido · header com código + paciente clicável · hero do estágio atual + barra de progresso · timeline vertical de 6 estágios com sub-eventos do tracking Memphis · side col com paciente + produto + breakdown financeiro |
| 08 | `pages/anvisa.html` | **Fechado** — saúde operacional do bot Anvisa · alerta crítico de sessão Gov.br + 4 mini-stats + card do bot (sessão / fila pg-boss / taxa de sucesso / procuradora) + lista de protocolos com estados captcha-pendente, autorizada, em análise e renovação |
| 09 | `pages/pro-paciente.html` | **Fechado** — tela de validação do brand system · stats semânticos + alerta crítico Anvisa + prescrição + linha do tratamento |
| 10 | `pages/financeiro.html` | **Fechado** — gestão de cobranças Global Pace · a receber / vencidas / pagas · conciliação por webhook |
| 11 | `pages/pagamento-detalhe.html` | **Fechado** — cobrança de um pedido · link Global Pace · PIX / cartão / boleto · timeline e liberação da logística |
| 12 | `pages/logistica.html` | **Fechado** — torre de controle dos envios internacionais · transportadora Memphis · rota Paraguai → Brasil · envios ativos |
| 13 | `pages/logistica-detalhe.html` | **Fechado** — rastreio de um envio (#BR2934118) · linha do tempo do tracking Memphis · etapas e situação aduaneira |
| 14 | `pages/farmacovigilancia.html` | **Fechado** — pós-venda clínico · check-ins periódicos · evolução do tratamento · registro de efeitos adversos |
| 15 | `pages/produtos.html` | **Fechado** — catálogo dos produtos de cannabis importados do Paraguai · toggle grade ↔ tabela · 4 mini-stats · filtros por categoria · cards focados no texto com categoria por faixa de cor lateral, preço, badge de estoque (ok / baixo / esgotado / importação a caminho) e prescrições no mês |
| 16 | `pages/medicos.html` | **Fechado** — médicos prescritores · toggle grade ↔ tabela · 4 mini-stats · filtros por status · cards com avatar, CRM, especialidade (ponto colorido), pacientes e prescrições do mês · estados ativo / verificação de CRM / inativo |
| 17 | `pages/configuracoes.html` | **Fechado** — painel admin da operação · sub-navegação de settings (Geral, Equipe & permissões, Integrações, Faturamento, Segurança, Notificações) · tabela de membros com papel + último acesso + status (ativo / convite pendente) · cards de papéis & permissões por cor |
| 18 | `pages/relatorios.html` | **Fechado** — analytics da operação · 4 KPIs com variação · receita por mês (barras CSS, mês atual em coral) · funil de conversão regulatório (prescrição → entrega) · mix por categoria (donut conic-gradient) · rankings de prescritores e produtos |
| 19 | `pages/produto-detalhe.html` | **Fechado** — ficha do produto (CBD Full Spectrum 3000mg) · header com faixa de categoria · ficha técnica · estoque com ponto de reposição + importação Memphis · posologia & indicações · side col com preço/margem, desempenho e movimentação |
| 20 | `pages/medico-detalhe.html` | **Fechado** — ficha do prescritor (Dr. Carlos Andrade) · dados profissionais + CRM/RQE · pacientes vinculados (linkados) · prescrições recentes · side col com desempenho, áreas de atuação e contato |

Próximas telas a desenhar entram via `pages/` conforme avançamos.

> As listas de Produtos e Médicos linkam para suas telas de detalhe.

## Como abrir

Localmente, qualquer servidor HTTP estático serve:

```bash
# com node:
npx http-server -p 8765

# ou direto file:// (alguns navegadores bloqueiam — prefere o servidor)
```

Abra `http://localhost:8765/` ou clique em `index.html` direto se seu navegador permitir.
