# MEGA-PROMPT — PESQUISA PROFUNDA: FUNCIONALIDADES DE ERP PARA TORREFAÇÃO DE CAFÉ

---

## SUA MISSÃO

Você é um consultor especialista em ERP industrial, sistemas MES e gestão de produção para indústria alimentícia. Sua missão é fazer uma PESQUISA PROFUNDA e EXAUSTIVA nos principais sistemas ERP do Brasil e do mundo, extraindo TODAS as funcionalidades relacionadas a ORDEM DE PRODUÇÃO, MANUFATURA e CHÃO DE FÁBRICA.

O resultado será usado como BASE DE CONHECIMENTO para construir um sistema de Ordem de Produção personalizado para uma torrefação de café. Quanto mais detalhado, melhor. Não resuma — DETALHE TUDO.

---

## QUEM VAI USAR ESTE RESULTADO

- **Empresa**: Patrocínio Café Indústria e Comércio de Café LTDA
- **CNPJ**: 36.236.772/0001-30
- **Local**: Goiânia/GO
- **Proprietário**: Judson Gabriel Martins (Gabriell)
- **ERP atual**: SIGE Cloud
- **Marcas**: Pompojeré, Cremon (Kremon), Modão, Patrocínio
- **Certificação**: Selo Puro Lote (primeiro do Brasil, INPI, SENAI, NUGAP)

O sistema está sendo construído pelo **Claude Code** (IA da Anthropic) em arquivo HTML único com JavaScript vanilla, hospedado no GitHub Pages e Vercel.

---

## PROCESSO PRODUTIVO DA TORREFAÇÃO (12 ETAPAS)

Pesquise como cada ERP abaixo resolve CADA UMA dessas etapas:

1. **Compra de café verde cru** — por peneira (P17/18, P15/16, P13/14, P10/12, FP10, FP8, FP5, PVA)
2. **Recebimento e conferência** — peso em balança aferida, coleta de amostras, umidade, defeitos, NF-e
3. **Estoque de matéria-prima** — segregado por peneira, qualidade (bom/ruim), FIFO/FEFO, PVA sempre separado
4. **Torra** — torrador 180-220kg/carga, CADA PENEIRA SEPARADA, 15-20min, 550°C+, quebra 13-18%
5. **Resfriamento e degas** — 8 a 24 horas
6. **Silos e blendagem** — 3 silos, mistura pós-torra se padrão e bebida iguais, PVA nunca mistura
7. **Moagem** — moinho martelo Jocar 400kg/h, peneira 1,4mm (almofada) ou 1,6mm (vácuo), quebra 2-4%
8. **Envase/embalagem** — Amazon Pack, almofada 250g (fardo 20un=5kg), 500g (fardo 10un=5kg), vácuo 500g (caixa 20un=10kg)
9. **Paletização** — identificação lote, data fab, validade, quantidade
10. **Controle de qualidade** — peso INMETRO, rótulo com ponto de torra, selagem, laudo
11. **Lançamento no ERP** — baixa matéria-prima, entrada produto acabado, NF-e, custos
12. **Expedição** — conferência 100%, assinatura operador + supervisor + PCP

---

## SISTEMAS PARA PESQUISAR (TODOS OBRIGATÓRIOS)

### ERPs brasileiros
1. **SIGE Cloud** — sigecloud.com.br (ERP da empresa, pesquisar em profundidade)
2. **TOTVS Protheus** — módulo SIGAPCP (PCP e Manufatura)
3. **TOTVS Datasul** — módulo SFC (Chão de Fábrica)
4. **Bling** — bling.com.br (ordem de produção para pequena indústria)
5. **Nomus ERP Industrial** — nomus.com.br (especializado em indústria)
6. **Maxiprod** — maxiprod.com.br (PCP com carga-fábrica)
7. **Sankhya** — sankhya.com.br (módulo de produção)
8. **Senior ERP** — senior.com.br (gestão industrial)
9. **WebMais** — webmaissistemas.com.br (ERP para indústria)
10. **ADV Tecnologia** — advtecnologia.com.br (ERP específico para café)

### ERPs internacionais
11. **SAP PP** — Production Planning (manufatura discreta)
12. **SAP PP-PI** — Process Industries (indústria de processo/alimentos)
13. **Oracle NetSuite** — Manufacturing/Work Orders
14. **Microsoft Dynamics 365** — Supply Chain Management
15. **Odoo** — Manufacturing (open source)

### Sistemas MES (chão de fábrica)
16. **Compact MES** — shapesolutions.com.br
17. **SYNECO** — ska.com.br/produtos/syneco
18. **FMS** — sistemafms.com.br
19. **TOTVS MES** — integração com Protheus/Datasul
20. **LiveMES** — livemes.com

---

## CATEGORIAS DE PESQUISA (PESQUISAR CADA UMA EM PROFUNDIDADE)

### CATEGORIA 1 — ORDEM DE PRODUÇÃO (OP)
- Como criar OP manualmente e automaticamente (MRP/MPS)
- Campos obrigatórios da OP (número, produto, quantidade, datas, armazém)
- Subordens de produção (quando matéria-prima precisa ser fabricada)
- Ciclo de vida da OP: Planejada → Firme → Liberada → Requisitada → Em Produção → Concluída → Encerrada → Cancelada
- O que acontece em CADA mudança de status
- Log de auditoria (quem mudou, quando, de qual status para qual)
- OP por pedido de venda vs OP por reposição de estoque
- OP parcial (produzir parte e concluir depois)
- Cancelamento de OP (o que acontece com materiais já requisitados)
- Impressão da OP para o chão de fábrica

### CATEGORIA 2 — BOM (LISTA DE MATERIAIS) / FICHA TÉCNICA / RECEITA
- Estrutura do produto (quais insumos compõem o produto final)
- BOM multinível (produto acabado → subproduto → matéria-prima)
- Quantidades por unidade de produção
- Perdas previstas por etapa (torra 15%, moagem 3%)
- Substitutos de matéria-prima (quando um insumo acaba, usar outro)
- Versões de BOM (receitas diferentes para o mesmo produto)
- Custo planejado vs custo real da BOM

### CATEGORIA 3 — ROTEIRO DE PRODUÇÃO / OPERAÇÕES
- Sequência de operações (etapa 1, 2, 3...)
- Tempo planejado por operação
- Máquina/centro de trabalho por operação
- Operador responsável por operação
- Operações paralelas vs sequenciais
- Setup de máquina (tempo de preparação)
- Roteiro alternativo (plano B se máquina quebrar)

### CATEGORIA 4 — APONTAMENTO DE PRODUÇÃO
- Apontamento por operação/etapa (início, fim, quantidade)
- Apontamento parcial (50% feito, continua amanhã)
- Apontamento via tablet/celular/terminal de chão de fábrica
- Código de barras / QR code para apontar
- Apontamento de tempo: planejado vs real
- Apontamento de quantidade: prevista vs produzida
- Apontamento de perdas/refugo/retrabalho
- Apontamento retroativo (esqueceu de registrar, faz depois)

### CATEGORIA 5 — ESTOQUE (BAIXA AUTOMÁTICA E EMPENHO)
- Empenho de materiais (reserva ao liberar OP)
- Estoque disponível vs estoque empenhado vs estoque livre
- Requisição de materiais (saída do almoxarifado para produção)
- Baixa automática proporcional (produziu 50%, baixa 50% dos insumos)
- Baixa na conclusão da OP (baixa tudo de uma vez)
- Entrada automática do produto acabado ao concluir OP
- Devolução de material não usado (volta pro estoque)
- Perdas e quebras (diferença entre previsto e real)
- Inventário rotativo e ajuste de estoque
- Estoque mínimo e ponto de pedido
- Estoque por local/armazém/silo
- Estoque por lote (rastreável)

### CATEGORIA 6 — RASTREABILIDADE E LOTES
- Número de lote automático na entrada de matéria-prima
- Número de lote automático na produção
- Rastreabilidade bidirecional (do grão ao pacote E do pacote ao grão)
- Genealogia de lote (quais lotes de MP foram usados em cada lote de PA)
- FIFO (First In, First Out) — usa o mais antigo primeiro
- FEFO (First Expired, First Out) — usa o que vence antes
- Bloqueio de lote (quarentena, vencido, reprovado)
- Alerta de validade próxima
- Código de barras por lote
- Rastreabilidade para recall (recolhimento de produto)

### CATEGORIA 7 — QUALIDADE E CONFORMIDADE
- Inspeção de recebimento (matéria-prima)
- Inspeção durante produção (em processo)
- Inspeção final (produto acabado)
- Laudo de qualidade vinculado ao lote
- Parâmetros de qualidade: umidade, impureza, granulometria, defeitos, Agtron
- Aprovação/reprovação com motivo
- Retrabalho (produto reprovado volta pra produção)
- Descarte (produto irrecuperável)
- Certificados: Selo Puro Lote, ABIC, MAPA
- Regra MAPA: impureza do blend < 1% (tolerância 1,2%)
- Conformidade INMETRO (peso dos pacotes)
- GMP (Boas Práticas de Fabricação)

### CATEGORIA 8 — CUSTOS INDUSTRIAIS
- Custo de matéria-prima por OP (café verde por kg)
- Custo de mão de obra por OP (horas × custo/hora)
- Custo de energia por OP (consumo ou rateio)
- Custo de embalagem por OP (plástico, fardo, caixa)
- Custo de lenha por OP (kg consumidos × preço/kg)
- Custo indireto (depreciação máquinas, aluguel, manutenção)
- Custo total da OP = soma de todos acima
- Custo por kg produzido = custo total ÷ kg produzidos
- Custo previsto vs custo real (variação)
- Formação de preço de venda (custo + margem)
- Margem de lucro por produto, por cliente, por marca
- Ponto de equilíbrio (break-even)

### CATEGORIA 9 — MES / CHÃO DE FÁBRICA (TABLET)
- Interface para tablet/celular do funcionário
- Apontamento por toque na tela
- Leitor de código de barras integrado
- Instruções da OP na tela do funcionário
- Sequência de operações visual (o que fazer agora, o que vem depois)
- Registro de parada de máquina com motivo
- Registro de refugo com motivo
- Foto obrigatória (balança, produto, defeito)
- Assinatura digital do operador
- Dashboard de produção em tempo real
- OEE em tempo real (disponibilidade × performance × qualidade)
- Eliminação de papel no chão de fábrica
- Alertas sonoros e visuais (estoque crítico, OP atrasada)

### CATEGORIA 10 — PLANEJAMENTO (MRP / MPS / CRP)
- MRP: calcula necessidade de materiais baseado nos pedidos
- MPS: plano mestre de produção
- CRP: planejamento de capacidade (máquinas e pessoas)
- Carga-fábrica: visualização de ocupação por máquina/dia
- Gráfico de Gantt de produção
- Programação finita vs infinita
- Nivelamento de produção
- Lead time por operação

### CATEGORIA 11 — KPIs E RELATÓRIOS
- OPs emitidas, em andamento, concluídas, atrasadas (por período)
- Consumo de materiais (previsto vs real)
- Perdas e quebras por etapa, por operador, por período
- OEE (Overall Equipment Effectiveness)
- Produtividade por operador
- Tempo de ciclo por produto
- Custos de produção por OP, produto, período
- Simulador de produção (quanto precisa de MP para X pedidos)
- Estoque atual por categoria
- Rastreabilidade por lote
- Paradas de máquina (motivo, duração, frequência)
- Curva ABC de produtos e materiais
- Dashboard gerencial com gráficos

### CATEGORIA 12 — INTEGRAÇÕES E API
- API REST para integração com sistemas externos
- Integração com n8n / Zapier / Make
- Integração com WhatsApp (notificações)
- Integração com SIGE Cloud (ERP da empresa)
- Integração com balança digital
- Integração com impressora de etiquetas
- Integração com leitor de código de barras
- Webhook para eventos (OP concluída, estoque baixo)

### CATEGORIA 13 — FISCAL E TRIBUTÁRIO
- NF-e de entrada (compra de matéria-prima)
- NF-e de saída (venda de produto acabado)
- CFOP para produção (5.101, 5.102, etc.)
- NCM dos produtos de café
- ICMS, PIS, COFINS na produção
- Livro de registro de produção
- Bloco K do SPED (controle de produção e estoque)

### CATEGORIA 14 — FUNCIONALIDADES ESPECÍFICAS PARA TORREFAÇÃO
- Perfil de torra (curva temperatura × tempo)
- Controle de Agtron (cor da torra)
- Registro de batelada (carga por carga)
- Blendagem com receita (quais peneiras, quanto de cada)
- Simulador de impureza MAPA (< 1%)
- Cálculo proporcional de blend para produção parcial
- Granulometria por tipo de embalagem
- Controle de degas (tempo de descanso pós-torra)
- Consumo de lenha por batelada
- Temperatura do moinho
- Conferência de peso INMETRO
- Selo Puro Lote vinculado ao lote de produção
- Classificação de bebida (prova de xícara / cupping)

---

## FORMATO OBRIGATÓRIO DA RESPOSTA

Entregue a resposta em **MARKDOWN (.md)** seguindo EXATAMENTE esta estrutura:

```markdown
# BASE DE CONHECIMENTO — FUNCIONALIDADES DE ERP PARA TORREFAÇÃO DE CAFÉ
# Pesquisa realizada em [data] por [nome da IA]
# Para uso como memória no Claude Code — Projeto Patrocínio Café

---

## 1. ORDEM DE PRODUÇÃO
### 1.1 Criação da OP
(como cada sistema faz, exemplos práticos)
### 1.2 Status e Ciclo de Vida
(detalhes de cada status)
### 1.3 Apontamento por Etapa
(como funciona em cada sistema)
### 1.4 Subordens
(quando usar, exemplos)

## 2. BOM / FICHA TÉCNICA / RECEITA
(detalhes de cada sistema)

## 3. ROTEIRO DE PRODUÇÃO
(detalhes)

## 4. APONTAMENTO
(detalhes)

## 5. ESTOQUE — BAIXA AUTOMÁTICA
### 5.1 Empenho
### 5.2 Requisição
### 5.3 Baixa Automática
### 5.4 Entrada de Produto Acabado
### 5.5 Devoluções
### 5.6 Perdas e Quebras

## 6. RASTREABILIDADE E LOTES
(detalhes)

## 7. QUALIDADE E CONFORMIDADE
(detalhes)

## 8. CUSTOS INDUSTRIAIS
(detalhes)

## 9. MES / CHÃO DE FÁBRICA
(detalhes)

## 10. PLANEJAMENTO (MRP/MPS)
(detalhes)

## 11. KPIs E RELATÓRIOS
(detalhes)

## 12. INTEGRAÇÕES
(detalhes)

## 13. FISCAL
(detalhes)

## 14. ESPECÍFICO TORREFAÇÃO DE CAFÉ
(detalhes)

## RESUMO — TOP 50 FUNCIONALIDADES ESSENCIAIS
(lista numerada das 50 funcionalidades mais importantes)

## RECOMENDAÇÕES PARA O SISTEMA DA PATROCÍNIO CAFÉ
(o que implementar primeiro, segundo, terceiro)
```

---

## REGRAS DE QUALIDADE DA PESQUISA

1. **PESQUISE EM PROFUNDIDADE** — Não aceito resumos superficiais. Quero detalhes de implementação.
2. **CITE FONTES** — Sites oficiais, documentação, vídeos do YouTube, artigos.
3. **DÊ EXEMPLOS REAIS** — "No SIGE Cloud, quando você clica em Concluir OP, o sistema automaticamente..."
4. **COMPARE SISTEMAS** — "O TOTVS faz X, mas o SAP faz Y porque..."
5. **FOQUE EM PRÁTICO** — Não quero teoria acadêmica. Quero o que o funcionário vê na tela.
6. **SEM LIMITE DE TAMANHO** — Quanto mais completo, melhor. 5.000 palavras? 10.000? Vai fundo.
7. **FORMATO MARKDOWN** — Para eu poder colar direto como memória no Claude Code.
8. **PESQUISE EM PORTUGUÊS E INGLÊS** — Muita documentação SAP/NetSuite é em inglês.
9. **INCLUA YOUTUBE** — Muitos tutoriais de SIGE Cloud, TOTVS, Nomus estão no YouTube.
10. **PESQUISE CASOS REAIS** — Café Orfeu usa TOTVS MES, ADV Tecnologia faz ERP para café.

---

## LEMBRETE FINAL

Este resultado será colado DIRETAMENTE no arquivo CLAUDE.md como **memória permanente** do Claude Code. Ele vai usar essas informações para construir cada funcionalidade do sistema de Ordem de Produção da Patrocínio Café.

Cada detalhe que você pesquisar agora = semanas de trabalho economizadas.

NÃO ECONOMIZE. VÁ FUNDO. DETALHE TUDO.
