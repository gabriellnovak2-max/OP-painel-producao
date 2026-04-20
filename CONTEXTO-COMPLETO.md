# CONTEXTO COMPLETO — OP Painel de Produção
## Patrocínio Café Indústria e Comércio de Café LTDA

**Versão:** Abril/2026  
**Sistema:** OP Painel de Produção (GitHub Pages + Vercel)  
**Proprietário:** Judson Gabriel Martins (Gabriell)  
**CNPJ:** 36.236.772/0001-30  
**Email:** grupojirehcafes@hotmail.com  
**Cidade:** Goiânia/GO

---

## 1. LINKS DO SISTEMA

| Ambiente | URL |
|----------|-----|
| GitHub Pages | https://gabriellnovak2-max.github.io/OP-painel-producao/ |
| Vercel | https://op-painel-producao.vercel.app |
| Repositório | https://github.com/gabriellnovak2-max/OP-painel-producao |

---

## 2. ARQUITETURA TÉCNICA

### Tecnologia
- **Arquivo único:** `index.html` (~7.000 linhas) — HTML + CSS inline + JavaScript vanilla
- **Zero dependências locais** — CDN para Chart.js e html2canvas
- **Sem backend, sem framework, sem build step**
- **Persistência:** `localStorage` (chave `painel_torrefacao`)
- **Deploy automático:** GitHub Pages (branch `main`) + Vercel (mesmo repositório)

### Arquivos do projeto
```
OP-painel-producao/
├── index.html                    # Aplicação principal (~7.000 linhas)
├── relatorio-estoque.html        # Relatório standalone para impressão PDF
├── CLAUDE.md                     # Memória permanente do projeto (447 linhas)
├── MEGA-PROMPT-PESQUISA-ERP.md   # Prompt para pesquisa em outras IAs
└── CONTEXTO-COMPLETO.md          # Este arquivo
```

### Estrutura do index.html
- **Linhas 1-325:** `<head>` com CSS inline, CDN Chart.js e html2canvas
- **Linhas 326-2600:** HTML das 30+ abas (tab0 a tab30)
- **Linhas 2600-7000+:** `<script>` com todo o JavaScript

---

## 3. ABAS DO SISTEMA (COMPLETO)

| Tab | Nome | Conteúdo |
|-----|------|----------|
| 0 | Home | KPIs, calendário feriados, 8 gráficos, fluxo rastreabilidade, widget workflow |
| 1 | Ordem de Produção | OP completa com 12 etapas |
| 2 | Bateladas de Torra | Registro por batelada |
| 3 | Controle de Silos | 3 silos visuais 3D |
| 4 | Blendagem Pós-Torra | Silos visuais + simulador blend |
| 5 | Moagem e Embalagem | Registro moagem + envase |
| 6 | Controle de Tempos | Tempos por etapa/operador |
| 7 | Quebra e Fiscal | Controle de quebras + MAPA |
| 8 | Cadastro de Clientes | Benevita, Café Vida, Junior, Jireh, Della etc. |
| 9 | Estoque Café Verde Cru | Lotes com peneira, volumes, peso, umidade, defeitos |
| 10 | Estoque Embalagens | Almofada 250g/500g, vácuo 500g |
| 11 | Estoque Lenha | Controle de lenha para torra |
| 12 | Fichas Clientes/Produtos | Fichas técnicas |
| 13 | Selos e Certificados | Selo Puro Lote INPI |
| 14 | AGB Maquinação | Controle AGB |
| 15 | Histórico de OPs | Histórico completo |
| 16 | Descarregamento Torrefação | Controle descarregamento |
| 17 | Estoque Café Grão Torrado | Lotes torrados com peneira e tipo |
| 18 | Estoque Café Torrado em Pó | Lotes em pó por marca |
| 19 | Simulador de Blend MAPA | Impureza ponderada (limite 1%) |
| 20 | Workflow Editor | Editor visual drag-and-drop |
| 21 | Workflow Etapas | Etapas configuráveis |
| 22 | Workflow Templates | Templates prontos |
| 23 | Workflow Histórico | Log de eventos |
| 24 | Workflow Configurações | Gatilhos automáticos |
| 25 | Produto Acabado | Café embalado pronto pra venda |
| 26 | Cadastro de Fornecedores | Fornecedores de café cru |
| 27 | Cadastro de Operadores | Equipe da produção |
| 28 | Cadastro de Produtos | Produtos e marcas |
| 29 | Cadastro de Prestadores | Serviços terceirizados |
| 30 | Compra de Café Cru | Início do processo — pedido de compra |

---

## 4. MENU LATERAL (SIDEBAR)

```
PRINCIPAL
├── Home
├── Workflow (submenu)
│   ├── Editor Visual
│   ├── Etapas
│   ├── Templates
│   ├── Histórico
│   └── Configurações
├── Compra de Café Cru          ← NOVO
├── AGB Recebimento (submenu)
│   └── Descarregamento Torrefação
└── Estoque (submenu)
    ├── Café Verde Cru
    ├── Café Grão Torrado
    ├── Café Torrado em Pó
    └── Produto Acabado          ← NOVO

PRODUÇÃO
├── OP
├── Bateladas
├── Silos
├── Blendagem (submenu)
│   └── Simulador MAPA
├── Moagem
└── Tempos

GESTÃO
├── Fichas
├── Quebra
├── Cadastros (submenu)         ← REESTRUTURADO
│   ├── Clientes
│   ├── Fornecedores
│   ├── Operadores
│   ├── Produtos
│   └── Prestadores de Serviço
├── Selos
└── Histórico
```

---

## 5. DADOS DE ESTOQUE — AUDITORIA FÍSICA ABRIL/2026

### 5.1 Café Verde Cru (2 lotes)

| # | Lote | Peneira | Volumes | Peso Líquido |
|---|------|---------|---------|--------------|
| 1 | Lote Sr. Carlos | Resíduo PVA | 10,5 | 495,50 kg |
| 2 | Estrelinha Pedro | P17/18 | 77 | 3.103,10 kg |
| **TOTAL** | | | **87,5** | **3.598,60 kg** |

### 5.2 Café Grão Torrado (6 lotes)

| # | Lote | Peneira | Tipo | Volumes | Peso Líquido |
|---|------|---------|------|---------|--------------|
| 1 | 15/16 Peneirado Zé Maria — Bom | P15/16 | Puro | 6 | 117,30 kg |
| 2 | 15/16 Peneirado Zé Maria — Ruim | P15/16 | Puro | 5 | 86,10 kg |
| 3 | Devolução Renata Inhumas | — | Puro | 29 | 496,40 kg |
| 4 | Grão Torrado Recente 15/16 | P15/16 | Puro | 28 | 560,00 kg |
| 5 | Grão Torrado (Carlos) | — | Puro | 6 | 137,80 kg |
| 6 | Café Torrado Grão 15/16 | P15/16 | Puro | 97 | 591,00 kg |
| **TOTAL** | | | | **171** | **1.988,60 kg** |

> **Obs:** Lote nº6 — Torra em 18/12/2025

### 5.3 Café Torrado em Pó (3 lotes)

| # | Marca/Produto | Volumes | Peso Líquido |
|---|---------------|---------|--------------|
| 1 | Perdeu Essência | 32 | 860,00 kg |
| 2 | Devolução Prefeitura Alto Horizonte | 6 | 185,00 kg |
| 3 | Café Moído Modão | 27 | 137,80 kg |
| **TOTAL** | | **65** | **1.182,80 kg** |

### 5.4 Produto Acabado (7 itens)

| # | Produto | Gramatura | Peso | Status | Obs |
|---|---------|-----------|------|--------|-----|
| 1 | Café Vida | 500g | 395,00 kg | Disponível | |
| 2 | Café Jireh | 500g | 395,00 kg | Disponível | Litografia Nova |
| 3 | Café Jireh | 250g | 90,00 kg | Disponível | |
| 4 | Café Della | 500g | 330,00 kg | Disponível | |
| 5 | Café Della | 250g | 200,00 kg | Disponível | |
| 6 | Café Empacotado Transparente | 500g | 35,00 kg | Disponível | |
| 7 | Café Kremon a Vácuo | 500g | 6.879,00 kg | Disponível | Devolução MT |
| **TOTAL** | | | **8.324,00 kg** | | |

### RESUMO GERAL

| Categoria | Itens | Peso Total |
|-----------|-------|-----------|
| Café Verde Cru | 2 | 3.598,60 kg |
| Café Grão Torrado | 6 | 1.988,60 kg |
| Café Torrado em Pó | 3 | 1.182,80 kg |
| Produto Acabado | 7 | 8.324,00 kg |
| **TOTAL GERAL** | **18** | **15.094,00 kg** |

---

## 6. EQUIPE DA EMPRESA

| Setor | Responsável | Backup |
|-------|-------------|--------|
| Gestão/Direção | Judson Gabriel Martins (Gabriell) | — |
| Financeiro/Faturamento | Lucas | Diogo |
| Estoque/Expedição | Valtinho | — |
| Produção (torra/moagem/envase) | Equipe chão de fábrica | — |
| PCP/Apontamento | Setor administrativo | — |
| Qualidade/Laudos | Setor de qualidade | — |

---

## 7. SISTEMAS INTEGRADOS

| Sistema | Função | Status |
|---------|--------|--------|
| SIGE Cloud | ERP principal (NF-e, estoque, cadastros) | Ativo |
| GitHub Pages | Hospedagem painel | Ativo |
| Vercel | Hospedagem backup (mesmo repo) | Ativo |
| Supabase | Banco de dados nuvem | **Passo 2 — A CONTRATAR** |
| n8n | Automação (WhatsApp, alertas) | **Passo 5 — FUTURO** |

---

## 8. ROADMAP — 6 PASSOS (ORDEM OBRIGATÓRIA)

```
✅ PASSO 0 → Sistema base funcionando (GitHub Pages)
🔄 PASSO 1 → Terminar sistema de Ordem de Produção   ← ESTAMOS AQUI
⏳ PASSO 2 → Contratar Supabase (banco de dados nuvem, plano gratuito)
⏳ PASSO 3 → Conectar sistema ao Supabase (trocar localStorage por Supabase)
⏳ PASSO 4 → Configurar domínio próprio no Vercel (comprar patrociniocafe.com.br)
⏳ PASSO 5 → Ligar n8n (automação: WhatsApp, alertas, integração SIGE)
⏳ PASSO 6 → Agentes IA nos tablets (cada setor guiado por IA)
```

---

## 9. GUIA DE PRODUÇÃO — 12 ETAPAS

### Dados obrigatórios da GP
- GP_ID (código único), Data, Cliente/Órgão, CNPJ do cliente
- Marca do café, Pedido/Contrato
- Padrão ABIC: Tradicional / Extraforte / Superior / Gourmet
- Ponto de torra: clara / média / média-escura / escura
- Granulometria: 1,4mm (almofada) ou 1,6mm (vácuo)
- Tipo de embalagem: 250g almofada / 500g almofada / 500g vácuo
- Peso da embalagem: 4,5g (250g alm.) / 5,5g (500g alm.) / 12g (500g vácuo)

### As 12 etapas

1. **Recebimento do pedido** — Cliente, marca, quantidade, embalagem, padrão ABIC, ponto de torra, prazo
2. **Seleção de lotes do cru** — Escolher por peneira/qualidade. PVA proibido. Reservar no ERP
3. **Torra** — Torrador 180-220kg/carga. Cada peneira separada. 15-20min, 550°C+. Registrar lote, hora, temperatura, operador
4. **Resfriamento e degas** — Descanso 8-24h antes de moer/embalar
5. **Silos e blend** — 3 silos para separar torrado. PVA nunca mistura
6. **Moagem** — Moinho Jocar 400kg/h. Almofada 1,4mm, vácuo 1,6mm. Quebra 2-4%
7. **Silo de pó** — Pó cai no silo para alimentar envase
8. **Envase** — Amazon Pack. Registrar quebras, fardos/caixas
9. **Paletização** — Pallet com identificação: lote(s), data fab., validade, quantidade
10. **Controle de qualidade** — Peso INMETRO, rótulo com ponto de torra, selagem
11. **Lançamento no sistema** — ERP + NF-e. Fechar GP com rendimentos reais. Vincular laudos
12. **Expedição** — Conferência 100% vs GP. Assinatura: Operador + Supervisor + PCP

### Quebras de torra (% perda de peso)
| Ponto | Quebra |
|-------|--------|
| Clara | 13-13,5% |
| Média | 14,5-15% |
| Escura | 16,5-18% |

### Fórmulas de rendimento
```
Peso_torrado = Peso_cru × (1 − %perda_torra)
Peso_pó = Peso_torrado × (1 − %perda_moagem)
Pacotes_500g = INT(Peso_pó / 0,5)
Pacotes_250g = INT(Peso_pó / 0,25)
Fardos_5kg (500g) = Pacotes / 10
Fardos_5kg (250g) = Pacotes / 20
Caixas_vácuo_10kg = INT(Peso_pó / 10)
Embalagem_total_kg = (Pacotes × Peso_embalagem_g) / 1000
Torras_necessárias = CEILING(Peso_cru / Carga_por_torra)
Lenha_total = Torras_necessárias × Lenha_por_torra
```

---

## 10. REGRAS DO NEGÓCIO

### Classificação por peneiras (tamanho do grão)
P5 (quebradinho) → P8 → P10 → P10/12 → P13/14 → P15/16 → P17/18 → PVA (resíduo)

**PVA = PROIBIDO no produto final. SEMPRE segregado.**

### Regra MAPA — Impureza
- Limite oficial: **< 1%**
- Tolerância com aviso: até 1,2%
- Sistema calcula impureza ponderada do blend
- Simulador MAPA na Tab 19

### Marcas
- **Pompojeré, Cremon (Kremon), Modão, Patrocínio**
- Selo Puro Lote: primeiro do Brasil, registro INPI, laudo SENAI + NUGAP

### FIFO/FEFO
- Primeiro a entrar = primeiro a sair (FIFO)
- Primeiro a vencer = primeiro a sair (FEFO)

---

## 11. EQUIPAMENTOS

| Equipamento | Capacidade | Observações |
|-------------|-----------|-------------|
| Torrador | 180-220 kg/carga | Temperatura 550°C+, tempo 15-20min |
| Moinho Jocar | 400 kg/hora | Martelo, peneiras 1,4mm e 1,6mm |
| Amazon Pack | — | Almofada e vácuo |

### Embalagens
| Tipo | Gramatura | Fardo/Caixa | Peso embalagem |
|------|-----------|-------------|----------------|
| Almofada | 250g | 20 pac = 5kg | 4,5g |
| Almofada | 500g | 10 pac = 5kg | 5,5g |
| Vácuo | 500g | 20 pac = 10kg | 12g |

---

## 12. CLIENTES PRINCIPAIS

Benevita, Café Vida, Junior Ceresino, Jireh, Della, Prefeitura (Alto Horizonte), Renata Inhumas

---

## 13. FUNCIONALIDADES TÉCNICAS DO SISTEMA

### Persistência de dados
```javascript
// Chaves no localStorage
'painel_torrefacao'    // Dados principais (todas as tabelas)
'workflow_definition'  // Definição do workflow
'workflow_log'         // Log de eventos
'tema-fosco'           // Tema escuro ativo/inativo
'wf_gatilhos_estados'  // Estados dos gatilhos
'estoque_versao'       // Versão dos dados de estoque (ESTOQUE_VERSAO = 3)
```

### Sistema de versão do estoque
```javascript
const ESTOQUE_VERSAO = 3;
// Se versão salva < ESTOQUE_VERSAO, limpa e recarrega dados auditados
// Evita problema de dados antigos "presos" no cache
```

### Auto-save
- A cada 30 segundos
- No evento `beforeunload` (ao fechar aba/janela)
- No evento `visibilitychange` (ao trocar de aba)

### Exportação de dados
- **Excel (CSV):** `showSaveFilePicker` → "Salvar Como" nativo do Windows
- **PDF:** `print-color-adjust: exact` → preserva cores verdes na impressão

### Funções principais
```javascript
abrirAba(n, btn)           // Troca aba principal
abrirAbaSub(n, btn)        // Troca aba de submenu
toggleSubmenu(el)           // Abre/fecha submenu
salvarDados(silencioso)     // Salva no localStorage
carregarDados()             // Restaura do localStorage
darBaixaCafeVerde(lote, kg) // Baixa automática no estoque verde
darBaixaGraoTorrado(lote,kg)// Baixa automática no grão torrado
darBaixaCafePo(marca, kg)   // Baixa automática no pó
preCarregarEstoqueInicial() // Inicializa com dados da auditoria
exportarTabelaExcel(tblId)  // Exporta tabela como CSV
exportarTabelaPDF(tblId)    // Exporta tabela como PDF colorido
```

### Gráficos (Chart.js)
8 gráficos na Home: barras, linhas, gauges, radar, doughnut

### Workflow automático
- 7 gatilhos automáticos
- Log de eventos com timestamp
- Beep sonoro nas notificações
- Editor visual drag-and-drop com conexões Bézier
- Export PNG/PDF
- Undo/redo

### Silos 3D
- 3 silos com nível de preenchimento animado
- Representação visual do café torrado em cada silo

---

## 14. HISTÓRICO DE ALTERAÇÕES DESTA SESSÃO

### Alterações realizadas (ordem cronológica)

1. **Atualização do estoque** com dados do inventário físico (imagens enviadas pelo Gabriell)
2. **Nova aba Tab 25 — Produto Acabado** no submenu Estoque
3. **Reestruturação Cadastros** — transformado em submenu com 5 sub-abas (Clientes, Fornecedores, Operadores, Produtos, Prestadores)
4. **Novas colunas no estoque** — Sacas, Volumes, Peso Bruto, Tara, Peso Líquido, Conferência em todas as 3 abas
5. **Sistema de baixa automática** — `darBaixaCafeVerde()`, `darBaixaGraoTorrado()`, `darBaixaCafePo()`
6. **Exportar Excel (CSV)** com `showSaveFilePicker` (dialog nativo do Windows)
7. **Exportar PDF** com cores (print-color-adjust: exact)
8. **Página relatorio-estoque.html** — relatório standalone para impressão
9. **Sistema de versão** — `ESTOQUE_VERSAO = 3` para atualizar dados automaticamente
10. **Nova aba Tab 30 — Compra de Café Cru** no menu principal
11. **Atualização CLAUDE.md** — adicionada base de conhecimento ERP completa (pesquisa em 10 sistemas)
12. **MEGA-PROMPT-PESQUISA-ERP.md** — prompt para pesquisa em ChatGPT, Grok e outras IAs

### Erros corrigidos

| Problema | Causa | Solução |
|----------|-------|---------|
| Estoque não atualizava | Auto-save re-salvava dados antes do reload | Sistema de versão ESTOQUE_VERSAO |
| Excel abrindo no Cursor IDE | Extensão .xls/csv associada ao editor | showSaveFilePicker (dialog nativo) |
| PDF sem cores | Browser remove backgrounds na impressão | print-color-adjust: exact |
| Peso Kremon errado | Manuscrito: 268,60kg; cálculo: 259,60kg | Gabriell confirmou 259,60kg |
| Nome "Cruzeiro" no lote | Dados antigos em cache | Atualizado para "Estrelinha Pedro" |
| Café Della 250g mostrando 200.000 kg | Formato numérico | Confirmado 200,00 kg (correto) |

---

## 15. BASE DE CONHECIMENTO ERP — RESUMO

Pesquisa realizada em abril/2026 nos principais ERPs do Brasil e do mundo.

### Sistemas pesquisados
SIGE Cloud, TOTVS Protheus/Datasul, SAP PP/PP-PI, Oracle NetSuite, Bling, Nomus, Maxiprod, MES (Compact MES, SYNECO, FMS)

### Status da OP (ciclo de vida padrão)
```
Planejada → Firme → Liberada → Em Produção → Concluída → Encerrada
                                                         ↓
                                                     Cancelada
```

### Baixa automática de estoque — Como funciona
1. **Ao LIBERAR OP:** Sistema faz EMPENHO (reserva materiais)
2. **Durante produção:** Consumo registrado por etapa
3. **Ao CONCLUIR:** Baixa definitiva + entrada do produto acabado
4. **Devoluções:** Material não usado volta com registro

### Rastreabilidade bidirecional
- Do produto final → rastreia até o café verde de origem
- Do café verde → rastreia todos os produtos que usaram aquele lote

### Custo por kg produzido
```
Custo total = matéria-prima + mão de obra + energia + embalagem + lenha + depreciação
Custo/kg = Custo total ÷ quantidade produzida
Margem = Preço de venda − Custo/kg
```

---

## 16. REGRAS DE DESENVOLVIMENTO

1. **NUNCA separar em múltiplos arquivos JS/CSS** — manter tudo em `index.html` inline
2. **SEMPRE fazer merge pro main E push** — GitHub Pages serve do main
3. **Login DESATIVADO** temporariamente (overlay display:none) — será reativado no futuro
4. **Não mexer** no calendário de feriados, nos 8 gráficos, ou no sistema de AGB sem autorização
5. **Antes de remover HTML**, verificar se o JavaScript referencia os IDs
6. **Testar no navegador** após cada alteração — Ctrl+Shift+R no GitHub Pages
7. **Se o Cursor bagunçar**, restaurar com `git show <commit>:index.html`

### Comandos git
```bash
# Fazer alterações
git checkout claude/create-production-order-app-fS7Of
git add index.html
git commit -m "Descrição da alteração"
git push -u origin claude/create-production-order-app-fS7Of

# Publicar no GitHub Pages
git checkout main
git merge claude/create-production-order-app-fS7Of
git push -u origin main
git checkout claude/create-production-order-app-fS7Of
```

### Sincronizar no Cursor (IDE local)
```bash
git pull origin main
# Se der conflito:
git stash && git pull origin main
```

---

## 17. PRÓXIMOS PASSOS IMEDIATOS

### Tab 1 — Ordem de Produção (PRIORIDADE)
A OP precisa ser conectada com o estoque para:
- Ao liberar OP → EMPENHAR materiais no estoque (reserva)
- Ao confirmar etapa de torra → baixar café verde cru
- Ao confirmar etapa de moagem → baixar grão torrado
- Ao concluir OP → dar entrada no produto acabado

### Tab 25 — Produto Acabado
- Conectar com OP: ao concluir OP, produto acabado entra automaticamente
- Controle de lotes com validade
- Alerta de estoque mínimo

### Tabs de Estoque (9, 17, 18)
- Conectar botão "OK" da Blendagem com baixa automática no grão torrado
- Conectar envase com baixa automática no café pó

---

*Documento gerado em abril/2026 — Para uso interno e compartilhamento com agência*
