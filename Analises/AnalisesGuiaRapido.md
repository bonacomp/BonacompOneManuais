# Bonacomp One — Guia Rápido: Análises

> **Documento**: Análises Guia Rápido
> **Versão do App**: 1.0.477
> **Plataforma**: .NET MAUI 10.0.20
> **Última atualização**: 2026-03-18

---

## ⭐ Comece por aqui: Presets (sua análise salva em 1 clique)

Presets salvam **toda** a sua configuração (filtros, colunas, gráficos e KPIs) para você reutilizar sem reconfigurar nada. **Crie presets antes de tudo** — depois é só selecionar e carregar.

### Criando seu primeiro preset

1. **Fonte** → selecione a view desejada
2. **Filtros** → configure os filtros que usa no dia a dia
3. **Campos** → desmarque colunas que não precisa
4. **Gráficos** / **KPIs** → desmarque os que não precisa
5. Clique em **Salvar** → digite um nome descritivo → confirme
6. Pronto! O preset ficará disponível no Picker de **Preset**

### Usando um preset salvo

1. **Fonte** → selecione a view
2. **Preset** → selecione o preset desejado (os filtros, colunas, gráficos e KPIs serão configurados automaticamente)
3. Clique em **Carregar**

> **1 clique no preset + 1 clique em Carregar = análise pronta.**

### Ideias de presets por view

Você pode criar **vários presets para a mesma view**, cada um com uma visão diferente:

#### View de Pedidos Comerciais
| Nome do Preset | O que configura |
|---|---|
| **Pedidos Hoje** | Filtro: Dt. Emissão = hoje. Colunas: pedido, cliente, valor, vendedor |
| **Pedidos Mês Atual** | Filtro: Dt. Emissão = mês atual. Todos os gráficos visíveis |
| **Pedidos por Vendedor** | Filtro: vendedor específico. KPI: valor total. Gráfico: por data |
| **Pedidos Empresa X** | Filtro: empresa = X. Colunas resumidas, sem gráficos |
| **Exportação Mensal** | Filtro: mês anterior. Todas as colunas (para exportar XLSX completo) |

#### View de Faturamento
| Nome do Preset | O que configura |
|---|---|
| **Faturamento Semana** | Filtro: últimos 7 dias. KPIs: valor total e registros |
| **Faturamento por Empresa** | Sem filtro de data. Gráfico por empresa visível |
| **Faturamento Detalhado** | Todas as colunas, sem gráficos (foco na tabela) |

#### View de Financeiro
| Nome do Preset | O que configura |
|---|---|
| **A Receber Vencido** | Filtro: dt. vencimento até hoje. Situação = aberto |
| **A Pagar Semana** | Filtro: dt. vencimento = próximos 7 dias |
| **Fluxo Mensal** | Filtro: mês atual. Gráfico de linha por data |

#### View de Estoque
| Nome do Preset | O que configura |
|---|---|
| **Estoque Resumido** | Poucas colunas: produto, grupo, saldo. Sem gráficos |
| **Estoque por Grupo** | Gráfico por grupo visível. KPI: valor total |

> **Dica**: nomeie os presets de forma clara (ex: "Pedidos - Mês - Vendedor João"). Cada view tem seus próprios presets e cada usuário tem os seus.

### Gerenciando presets

| Ação | Como fazer |
|---|---|
| **Criar novo** | Configure tudo → **Salvar** → digite nome |
| **Atualizar existente** | Selecione o preset → altere a configuração → **Salvar** |
| **Criar cópia** | Com um preset carregado → **Salvar Como** → novo nome |
| **Excluir** | Selecione o preset → **Excluir** → confirme |

---

## Consultar dados (sem preset)

1. **Fonte** → selecione a view desejada no Picker
2. *(opcional)* **Filtros** → habilite os filtros desejados (checkbox) e preencha valores
3. *(opcional)* **Campos** → desmarque colunas que não precisa ver
4. Clique em **Carregar**

> Pronto! A tabela, KPIs e gráficos aparecerão.

---

## Filtrar por data

1. Clique em **Filtros** (se o painel estiver fechado)
2. Marque o **checkbox** do filtro de data desejado (ex: Dt. Emissão)
3. Selecione **data início** e **data fim**
4. Clique em **Carregar**

---

## Filtrar por empresa / vendedor / cliente

**Se o filtro for um Picker (lista pequena)**:
1. Marque o **checkbox** → selecione o valor no Picker → **Carregar**

**Se o filtro for de busca (campo de texto)**:
1. Marque o **checkbox** → digite pelo menos **2 letras** → selecione na lista de sugestões → **Carregar**

> Os filtros cascateiam: ao selecionar empresa, os outros filtros mostram apenas dados daquela empresa.

---

## Filtrar clicando no gráfico

1. **Clique em uma fatia** do gráfico de pizza (ou ponto do gráfico de linha)
2. A tabela e KPIs serão atualizados automaticamente
3. Para **remover** o filtro: clique na mesma fatia novamente

> Pode clicar em gráficos diferentes para acumular filtros (ex: empresa + vendedor).

---

## Filtrar pelo funil da coluna (tabela desktop)

1. Clique no **ícone de funil** (▼) no cabeçalho da coluna
2. Marque/desmarque os valores desejados
3. Clique em **Aplicar**

---

## Ordenar dados

- Clique no **cabeçalho da coluna** → ordena crescente
- Clique novamente → ordena decrescente

---

## Escolher colunas, gráficos e KPIs visíveis

1. Clique em **Campos**, **Gráficos** ou **KPIs**
2. Marque/desmarque os itens desejados
3. Clique em **Carregar**

> Atalhos em cada painel: **Todos** (marca tudo) · **Nenhum** (desmarca tudo)

> **Dica**: Após configurar, salve como preset para não precisar repetir!

---

## Exportar dados

1. Carregue os dados normalmente
2. Na toolbar, clique em **XLSX** ou **CSV**
3. Escolha:
   - **Tudo** → exporta todos os registros filtrados
   - **Página** → exporta só a página atual
4. Escolha onde salvar o arquivo

---

## Limpar tudo e recomeçar

- Clique no botão **Limpar** (ao lado do Picker de Fonte)
- Todos os filtros, seleções e dados serão resetados

---

## Paginação (desktop)

| Botão | Ação |
|---|---|
| **\|<** | Primeira página |
| **<** | Anterior |
| **>** | Próxima |
| **>\|** | Última |
| **Picker** | Registros por página (10/20/50/100) |

---

## Mobile (celular)

- Dados aparecem como **cards** (sem tabela)
- Role para baixo → novos dados carregam automaticamente
- KPIs e gráficos funcionam normalmente

---

## Referência rápida

| Quero... | Faço... |
|---|---|
| Análise rápida com preset | Fonte → Preset → Carregar |
| Criar preset | Configurar tudo → Salvar → nome |
| Consultar sem preset | Fonte → (filtros) → Carregar |
| Filtrar por data | Filtros → checkbox → datas → Carregar |
| Filtrar por empresa | Filtros → checkbox → selecionar → Carregar |
| Filtrar pelo gráfico | Clicar na fatia/ponto |
| Filtrar pela coluna | Funil (▼) → marcar → Aplicar |
| Ordenar | Clicar no cabeçalho da coluna |
| Ocultar colunas | Campos → desmarcar → Carregar |
| Exportar Excel | Toolbar → XLSX → Tudo ou Página |
| Recomeçar do zero | Limpar |