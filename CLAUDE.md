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
| 8 | Cadastros (operadores, fornecedores, clientes) |
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
| 19 | Simulador de Blend — Impureza MAPA (com blend proporcional, registro produção, clientes) |
| 20 | Workflow — Editor Visual |
| 21 | Workflow — Etapas |
| 22 | Workflow — Templates |
| 23 | Workflow — Histórico de Fluxos |
| 24 | Workflow — Configurações (gatilhos ON/OFF) |

### Menu lateral (sidebar)

Usa `nav-group` com `toggleSubmenu()` para submenus expansíveis:
- **PRINCIPAL**: Home, Workflow (submenu), AGB Recebimento (submenu), Estoque (submenu)
- **PRODUÇÃO**: OP, Bateladas, Silos, Blendagem (submenu), Moagem, Tempos
- **GESTÃO**: Fichas, Quebra, Cadastros, Selos, Histórico

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

- Torrefação de café em Goiânia, GO
- Processo: Café Verde → AGB Maquinação (peneiras) → Torra (bateladas 60kg) → Silos → Blend → Moagem → Embalagem → Selo Puro Lote
- Regra MAPA: impureza do blend deve ser < 1% (tolerância até 1.2% com aviso)
- Selo Puro Lote: primeiro do Brasil, registro INPI, laudo SENAI + NUGAP
- Clientes: Benevita, Café Vida, Junior Ceresino, Jireh, etc.
- Peneiras: P17/18, P15/16, P13/14, P10/12, FP10, FP8, FP5, PVA
