# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Projeto

**OP Painel de Produção** — Sistema de gestão de produção para a **Patrocínio Torrefação de Café**, empresa de torrefação de café localizada em Goiânia, GO. O dono é o **Gabriell**.

## Como falar com o Gabriell

- Fale como amigo íntimo de 40 anos, com intimidade e paciência
- NUNCA use linguagem formal ou técnica difícil
- Respostas curtas e diretas, sem rodeios
- Sempre explique passo a passo, clique por clique
- Use exemplos simples do dia a dia
- Se a resposta for longa, divida em etapas e pergunte se entendeu
- Gabriell está aprendendo do zero — explique tudo com didática
- Sempre dê contexto prático: "isso serve pra X no seu sistema"

## Arquitetura

Arquivo único `index.html` (~6.500 linhas) com HTML + CSS inline + JavaScript vanilla. Hospedado no GitHub Pages. Sem backend, sem framework, sem build. Dados persistidos em `localStorage`.

### Estrutura do index.html

- **Linhas 1-325**: `<head>` com CSS inline (`<style>`), CDN Chart.js e html2canvas
- **Linhas 326-2600**: HTML das 25 abas (tab0 a tab24)
- **Linhas 2600-6500+**: `<script>` com todo o JavaScript

### Abas (tabs)

Ver tabela completa na seção "Abas do sistema (atualizado)" abaixo — inclui tabs 0-30.

### Menu lateral (sidebar)

Usa `nav-group` com `toggleSubmenu()` para submenus expansíveis:
- **PRINCIPAL**: Home, Workflow (submenu), Compra de Café Cru, AGB Recebimento (submenu), Estoque (submenu com Produto Acabado)
- **PRODUÇÃO**: OP, Bateladas, Silos, Blendagem (submenu), Moagem, Tempos
- **GESTÃO**: Fichas, Quebra, Cadastros (submenu com 5 sub-abas), Selos, Histórico

### Navegação

- `abrirAba(n, btn)` — troca aba principal
- `abrirAbaSub(n, btn)` — troca aba de submenu
- `toggleSubmenu(el)` — abre/fecha submenu

### Persistência

- `salvarDados(silencioso)` — salva tudo em `localStorage` chave `painel_torrefacao`
- `carregarDados()` — restaura tudo do `localStorage`
- Auto-save a cada 30 segundos + `beforeunload` + `visibilitychange`
- Workflow salvo separado: chave `workflow_definition`
- Log de eventos: chave `workflow_log`
- Tema fosco: chave `tema-fosco`
- Estados gatilhos: chave `wf_gatilhos_estados`

### Funcionalidades especiais

- **Simulador de Blend MAPA**: calcula impureza ponderada (limite 1%), com 5 lotes, embalagem, fardo, impureza
- **Blend Proporcional**: calcula proporção pra produção parcial (ex: 250 kg de 2.895 kg total)
- **Registro de Produção**: abatimento do blend total, status OK/Pendente, barra de progresso
- **Calcular Todos os Clientes**: múltiplos clientes com impressão separada
- **8 gráficos interativos** (Chart.js): barras, linhas, gauges, radar, doughnut
- **Calendário de feriados**: Brasil + Goiás + Goiânia (Meeus/Jones/Butcher pra Páscoa)
- **Silos visuais 3D**: nível de preenchimento animado por silo
- **Motor de Workflow**: 7 gatilhos automáticos + log de eventos + beep sonoro
- **Editor Visual de Workflow**: drag-and-drop, conexões Bézier, templates, undo/redo, export PNG/PDF
- **Tema Fosco**: botão 🌙 no header, cinza escuro pra proteger os olhos
- **Impressão**: blend total + parcial em 1 folha, com quadradinhos de status

## Comandos

### Deploy
O site é publicado automaticamente pelo GitHub Pages a partir do branch `main`. Não há build step.

### Git
```bash
# Branch de trabalho
git checkout claude/create-production-order-app-fS7Of

# Após alterações, sempre fazer merge pro main e push
git add index.html
git commit -m "Descrição da alteração"
git push -u origin claude/create-production-order-app-fS7Of
git checkout main
git merge claude/create-production-order-app-fS7Of
git push -u origin main
git checkout claude/create-production-order-app-fS7Of
```

### Sincronizar com Cursor (IDE local do Gabriell)
No terminal do Cursor:
```bash
git pull origin main
```
Se der conflito:
```bash
git stash && git pull origin main
```

## Regras importantes

1. **NUNCA separar o código em múltiplos arquivos JS/CSS.** O Cursor já tentou isso e quebrou tudo. Manter tudo em `index.html` inline.
2. **SEMPRE fazer merge pro main E push** — GitHub Pages serve do main.
3. **Login está DESATIVADO** temporariamente (overlay com `display:none`). Será reativado no futuro.
4. **Não mexer** no calendário de feriados, nos 8 gráficos, ou no sistema de AGB sem autorização.
5. **Antes de remover HTML**, verificar se o JavaScript referencia os IDs (evitar crash como aconteceu com silos na Home).
6. **Testar no navegador** após cada alteração — Ctrl+Shift+R no link do GitHub Pages.
7. **Se o Cursor bagunçar o código**, restaurar com `git show <commit>:index.html` de um commit bom.

## Contexto do negócio

- **Empresa**: Patrocínio Café Indústria e Comércio de Café LTDA
- **CNPJ**: 36.236.772/0001-30
- **Local**: Goiânia/GO
- **Proprietário/Direção**: Judson Gabriel Martins (Gabriell)
- **Email**: grupojirehcafes@hotmail.com
- **ERP/Sistema**: SIGE Cloud
- **Marcas**: Pompojeré, Cremon (Kremon), Modão, Patrocínio
- Selo Puro Lote: primeiro do Brasil, registro INPI, laudo SENAI + NUGAP
- Regra MAPA: impureza do blend deve ser < 1% (tolerância até 1.2% com aviso)

### Equipe e funções

- **Financeiro/Cadastro/Crédito/Faturamento**: Lucas (titular) e Diogo (backup)
- **Estoque/Separação/Expedição**: Valtinho
- **Produção** (torra/moagem/envase): equipe de chão de fábrica
- **PCP/Apontamento**: setor administrativo
- **Qualidade/Laudos**: setor de qualidade
- **Gestão/Direção**: Judson Gabriel Martins

### Clientes

Benevita, Café Vida, Junior Ceresino, Jireh, Della, entre outros.

## Matéria-prima — Café Cru

### Classificação por peneiras (tamanho do grão)

P5 (quebradinho), P8, P10, P10/12, P13/14, P15/16, P17/18, PVA (resíduo — SEMPRE segregado, PROIBIDO no produto final)

### Qualidade

Cada lote recebe classificação: "bom" ou "ruim". Exemplo: P5 bom, P8 ruim, P10/12 bom.

### Recebimento do cru

1. Conferência de peso (balança aferida)
2. Coleta de amostras (umidade, defeitos)
3. Pegar nota fiscal
4. Lançar no SIGE Cloud (fornecedor, safra, origem, lote)
5. Armazenagem segregada e etiquetada (FIFO/FEFO)

## Guia de Produção (GP) — Processo completo

A Guia de Produção é o documento central que acompanha todo o processo de fabricação de um pedido. Contém todos os dados do pedido, parâmetros de processo, registros de perdas, consumos e assinaturas.

### Dados obrigatórios da GP

- GP_ID (código único), Data, Cliente/Órgão, CNPJ do cliente
- Marca do café (Pompojeré, Cremon, etc.)
- Pedido/Contrato, Quantidade de cru (kg)
- Padrão ABIC: Tradicional / Extraforte / Superior / Gourmet
- Ponto de torra: clara / média / média-escura / escura
- Granulometria: 1,4 mm (almofada) ou 1,6 mm (vácuo)
- Tipo de embalagem: 250g almofada / 500g almofada / 500g vácuo
- Peso da embalagem: 4,5g (250g alm.) / 5,5g (500g alm.) / 12g (500g vácuo)
- Perdas-alvo (torra, moagem, embalagem)
- Consumo de lenha por torra

### Fluxo de produção — 12 Etapas

**ETAPA 1 — Recebimento do pedido**: Cliente, marca, quantidade, embalagem, padrão ABIC, ponto de torra, prazo.

**ETAPA 2 — Seleção de lotes do cru**: Escolher lotes por peneira e qualidade. PVA proibido no blend final. Reservar no ERP (baixa do estoque de cru).

**ETAPA 3 — Torra**: Torrador capacidade 180-220 kg por carga. Torrar CADA PENEIRA SEPARADA. Tempo: 15-20 min. Temperatura: 550°C+. Quebra: clara 13-13,5%, média 14,5-15%, escura 16,5-18%. Registrar lote, peneira, carga, hora, temperatura, operador. Pesar na saída. Etiquetar LOTE TORRADO (LT).

**ETAPA 4 — Resfriamento e degas**: Descanso 8-24h antes de moer/embalar.

**ETAPA 5 — Silos e blend**: 3 silos para separar torrado. Depois de torrado, PODE misturar se padrão e bebida forem iguais. PVA nunca mistura.

**ETAPA 6 — Moagem**: Moinho Jocar (martelo), 400 kg/hora. Peneiras: almofada 1,4 mm, vácuo 1,6 mm. Quebra: 2-4%. Registrar hora, temperatura, lote. Etiquetar LOTE PÓ (LP).

**ETAPA 7 — Silo de pó**: Pó cai no silo para alimentar envase.

**ETAPA 8 — Envase/Empacotamento**: Máquina Amazon Pack. Almofada 250g: fardo 20 pac = 5 kg (emb 4,5g). Almofada 500g: fardo 10 pac = 5 kg (emb 5,5g). Vácuo 500g: caixa 20 pac = 10 kg (emb 12g). Registrar quebras.

**ETAPA 9 — Paletização**: Pallet com identificação: lote(s), data fab., validade, quantidade.

**ETAPA 10 — Controle de qualidade final**: Peso INMETRO, rótulo com ponto de torra (obrigatório), selagem. Se não conforme: retrabalho.

**ETAPA 11 — Lançamento no sistema**: Baixa no ERP + NF-e. Fechar GP com rendimentos reais. Custos: cru, lenha, embalagem, mão de obra, energia. Vincular laudos ao lote.

**ETAPA 12 — Expedição**: Conferência 100% vs GP. Assinatura: Operador + Supervisor + PCP.

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

### Checkpoints com assinaturas obrigatórias

1. Recebimento: peso e amostra (Ass.: Recebimento)
2. Torra: carga/descarga/perda/lenha (Ass.: Torrefador)
3. Moagem: peneira/peso/perda (Ass.: Moageiro)
4. Envase: checkweigher/fardos/quebras (Ass.: Envasador)
5. Liberação final: QC + PCP

## Abas do sistema (atualizado)

| Tab | Conteúdo |
|-----|----------|
| 0 | Home (KPIs, calendário feriados, 8 gráficos, fluxo rastreabilidade, widget workflow) |
| 1 | Ordem de Produção |
| 2 | Bateladas de Torra |
| 3 | Controle de Silos |
| 4 | Blendagem Pós-Torra (com silos visuais 3D) |
| 5 | Moagem e Embalagem |
| 6 | Controle de Tempos |
| 7 | Quebra e Fiscal |
| 8 | Cadastro de Clientes |
| 9 | Estoque Café Verde Cru |
| 10 | Estoque Embalagens |
| 11 | Estoque Lenha |
| 12 | Fichas Clientes/Produtos |
| 13 | Selos e Certificados |
| 14 | AGB Maquinação |
| 15 | Histórico de OPs |
| 16 | Descarregamento Torrefação |
| 17 | Estoque Café Grão Torrado |
| 18 | Estoque Café Torrado em Pó |
| 19 | Simulador de Blend — Impureza MAPA |
| 20-24 | Workflow (Editor, Etapas, Templates, Histórico, Configurações) |
| 25 | Produto Acabado |
| 26 | Cadastro de Fornecedores |
| 27 | Cadastro de Operadores/Funcionários |
| 28 | Cadastro de Produtos |
| 29 | Cadastro de Prestadores de Serviço |
| 30 | Compra de Café Cru |

## Próximos passos planejados

- **Supabase**: banco de dados na nuvem para persistir dados (substituir localStorage)
- **Vercel**: hospedar o sistema com link próprio para tablets dos funcionários
- **n8n**: automação de processos — conectar WhatsApp, sistema, estoque, alertas
- **Agentes IA**: cada setor da produção com IA guiando o funcionário etapa por etapa nos tablets
