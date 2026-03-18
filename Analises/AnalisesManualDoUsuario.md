# Bonacomp One — Manual do Usuário: Análises

> **Documento**: Análises Manual do Usuário
> **Versão do App**: 1.0.477
> **Plataforma**: .NET MAUI 10.0.20
> **Última atualização**: 2026-03-18
> **Público-alvo**: Usuários finais do Bonacomp One

---

## Sumário

1. [Visão Geral](#1-visão-geral)
2. [Acesso ao Módulo](#2-acesso-ao-módulo)
3. [Tela Principal — Categorias](#3-tela-principal--categorias)
4. [Tela de Análise (Dados)](#4-tela-de-análise-dados)
   - 4.1 [Seleção de Fonte (View)](#41-seleção-de-fonte-view)
   - 4.2 [Pré-Filtros](#42-pré-filtros)
   - 4.3 [Campos (Colunas)](#43-campos-colunas)
   - 4.4 [Gráficos](#44-gráficos)
   - 4.5 [KPIs (Indicadores)](#45-kpis-indicadores)
   - 4.6 [Botão Carregar](#46-botão-carregar)
   - 4.7 [Botão Limpar](#47-botão-limpar)
5. [Tabela de Dados (Desktop)](#5-tabela-de-dados-desktop)
   - 5.1 [Ordenação](#51-ordenação)
   - 5.2 [Funil de Coluna](#52-funil-de-coluna)
   - 5.3 [Paginação](#53-paginação)
6. [Cards de Dados (Mobile)](#6-cards-de-dados-mobile)
7. [Interação com Gráficos (Estilo Power BI)](#7-interação-com-gráficos-estilo-power-bi)
8. [Presets (Configurações Salvas)](#8-presets-configurações-salvas)
9. [Exportação (XLSX / CSV)](#9-exportação-xlsx--csv)
10. [Permissões Necessárias](#10-permissões-necessárias)
11. [Dicas e Perguntas Frequentes](#11-dicas-e-perguntas-frequentes)

---

## 1. Visão Geral

O módulo **Análises** permite consultar e visualizar dados da empresa de forma dinâmica, com tabelas, gráficos e indicadores (KPIs). Funciona como um painel analítico onde você pode:

- Consultar dados de diversas áreas (Comercial, Financeiro, Estoque, etc.)
- Filtrar por empresa, vendedor, período e outros critérios
- Escolher quais colunas, gráficos e KPIs exibir
- Interagir com gráficos clicando em fatias/pontos para filtrar dados (estilo Power BI)
- Exportar dados para Excel (XLSX) ou CSV
- Salvar configurações como presets para reutilizar

---

## 2. Acesso ao Módulo

1. Faça login no aplicativo com seu usuário e senha.
2. No menu principal, localize e toque/clique em **Análises**.
3. A tela de categorias será exibida.

> **Nota**: Você só verá o módulo Análises se possuir as permissões adequadas. Caso não apareça, entre em contato com o administrador do sistema.

---

## 3. Tela Principal — Categorias

Ao entrar no módulo Análises, você verá botões representando as categorias de análise disponíveis. Cada botão corresponde a uma área da empresa:

| Botão | Descrição |
|---|---|
| **Cadastros** | Análises sobre dados cadastrais (clientes, fornecedores, produtos, etc.) |
| **Comercial** | Análises sobre pedidos de venda, faturamento, vendedores |
| **Compras** | Análises sobre pedidos de compra e fornecedores |
| **Fiscal** | Análises sobre notas fiscais e dados tributários |
| **Financeiro** | Análises sobre contas a pagar, contas a receber, fluxo financeiro |
| **Estoque** | Análises sobre movimentações e saldos de estoque |
| **PCP** | Análises sobre produção e planejamento |
| **Atendimento** | Análises sobre atendimentos e chamados |
| **Projetos** | Análises sobre projetos e acompanhamento |

> **Importante**: Você só verá as categorias para as quais possui permissão de acesso.

**Para abrir uma análise**: toque/clique no botão da categoria desejada.

---

## 4. Tela de Análise (Dados)

Após escolher uma categoria, a tela de análise é aberta. Esta tela contém:
- Uma **barra de ferramentas** no topo (Fonte, Preset e botões de ação)
- Painéis expansíveis de **Filtros**, **Campos**, **Gráficos** e **KPIs**
- A **tabela de dados** (desktop) ou **cards** (mobile)
- A **barra de paginação** no rodapé (desktop)

### 4.1 Seleção de Fonte (View)

No topo da tela há o campo **Fonte** com um seletor (Picker).

1. Clique/toque no Picker de **Fonte**.
2. Aparecerá a lista de views (fontes de dados) disponíveis na categoria escolhida.
3. Selecione a view desejada.
4. Ao selecionar, os painéis de Filtros, Campos, Gráficos e KPIs serão abertos automaticamente para você configurar a análise antes de carregar.

> **Dica**: O nome da view indica o conteúdo dos dados. Por exemplo, `view_comercial_pedidos_base` contém dados de pedidos comerciais.

### 4.2 Pré-Filtros

O painel de **Filtros** permite restringir os dados antes de carregá-los. Os filtros disponíveis dependem da view selecionada (apenas filtros relevantes para as colunas existentes serão exibidos).

**Tipos de filtro**:

#### Filtro de Data (DateRange)
- Aparece com um **checkbox** para habilitar, um **label** com o nome do filtro e **dois DatePickers** (data início e data fim).
- **Como usar**:
  1. Marque o checkbox para habilitar o filtro.
  2. Selecione a data de início no primeiro DatePicker.
  3. Selecione a data de fim no segundo DatePicker.
- Exemplos: Dt. Emissão, Dt. Faturamento, Dt. Vencimento, Dt. Pagamento, Dt. Recebimento.

#### Filtro de Lista Pequena (PickerSmall)
- Aparece com um **checkbox** para habilitar, um **label** e um **Picker** com opções pré-carregadas.
- **Como usar**:
  1. Marque o checkbox para habilitar.
  2. Selecione o valor desejado na lista.
- As opções são carregadas automaticamente e **cascateiam**: ao selecionar um valor em um filtro, as opções dos outros filtros são atualizadas para refletir apenas combinações válidas.
- Exemplos: Empresa, Grupo, Família, Situação.

#### Filtro de Busca (LookupLarge)
- Aparece com um **checkbox** para habilitar, um **label** e um **campo de texto** para digitação.
- **Como usar**:
  1. Marque o checkbox para habilitar.
  2. Digite pelo menos **2 caracteres** no campo de busca.
  3. Aguarde as sugestões aparecerem (até 30 resultados).
  4. Selecione a opção desejada na lista de sugestões.
- As sugestões também respeitam a cascata dos outros filtros habilitados.
- Exemplos: Cliente, Vendedor, Fornecedor, Produto.

> **Filtros cascateados**: Os filtros funcionam em conjunto, como no Power BI. Ao selecionar "Empresa X" no filtro de empresa, os outros filtros mostrarão apenas vendedores, clientes e produtos daquela empresa.

### 4.3 Campos (Colunas)

O painel de **Campos** permite escolher quais colunas serão exibidas na tabela.

- Cada coluna disponível aparece com um **checkbox** e o **nome da coluna**.
- **Marque** os campos que deseja ver na tabela.
- **Desmarque** os que não precisa, para simplificar a visualização.

**Ações rápidas**:
| Botão | Ação |
|---|---|
| **Todos** | Marca todas as colunas |
| **Nenhum** | Desmarca todas as colunas |

> **Dica**: Selecionar menos colunas deixa a tabela mais limpa e a consulta mais rápida.

### 4.4 Gráficos

O painel de **Gráficos** permite escolher quais gráficos serão exibidos após o carregamento.

- Cada gráfico disponível aparece com um **checkbox** e o **título**.
- **Marque** os gráficos que deseja ver.
- **Desmarque** os que não precisa.

**Ações rápidas**:
| Botão | Ação |
|---|---|
| **Todos** | Marca todos os gráficos |
| **Nenhum** | Desmarca todos os gráficos |

Os gráficos disponíveis dependem das colunas da view (ex.: gráfico por vendedor, por empresa, por data de faturamento).

### 4.5 KPIs (Indicadores)

O painel de **KPIs** permite escolher quais indicadores numéricos serão exibidos.

- Cada KPI aparece com um **checkbox** e o **título**.
- **Marque** os KPIs que deseja ver.

**KPIs disponíveis** (variam conforme a view):
- **Registros** — mostra a quantidade total e filtrada de registros.
- **Valor Total**, **Valor Faturado**, etc. — mostra somatórios (Todos vs. Filtrados).

Cada card de KPI exibe:
- **Título**: nome do indicador (ex.: "Registros", "Valor Total")
- **Todos**: valor total considerando apenas os pré-filtros
- **Filtrados**: valor após aplicar também os filtros de coluna/gráfico

Quando há diferença entre "Todos" e "Filtrados", o valor filtrado fica **em destaque** para facilitar a comparação.

### 4.6 Botão Carregar

Após configurar a fonte, filtros, campos, gráficos e KPIs:

1. Clique no botão **Carregar**.
2. Os painéis de configuração serão fechados automaticamente.
3. A tabela será preenchida com os dados.
4. Os KPIs e gráficos selecionados serão exibidos acima da tabela.

> **Nota**: O botão Carregar só funciona quando uma view (Fonte) está selecionada.

### 4.7 Botão Limpar

O botão **Limpar** (ao lado do Picker de Fonte) faz um reset completo:
- Remove todos os filtros aplicados
- Restaura todas as colunas, gráficos e KPIs
- Limpa os dados carregados
- Mantém a view selecionada (como se tivesse sido selecionada pela primeira vez)

Útil quando você quer recomeçar a análise do zero sem trocar de view.

---

## 5. Tabela de Dados (Desktop)

No desktop (Windows/Tablet), os dados são exibidos em uma **tabela** com cabeçalho de colunas.

### 5.1 Ordenação

- Clique no **cabeçalho de uma coluna** para ordenar os dados por aquela coluna.
- Clique novamente para alternar entre ordem **crescente** e **decrescente**.
- A ordenação é feita no servidor (API), garantindo resultados corretos mesmo com milhares de registros.

### 5.2 Funil de Coluna

Cada coluna da tabela possui um **ícone de funil** (filtro) no cabeçalho.

1. Clique no **ícone de funil** da coluna desejada.
2. Um painel de filtro será aberto com as opções disponíveis (valores distintos daquela coluna).
3. Use o **campo de busca** para localizar opções rapidamente.
4. **Marque/desmarque** as opções desejadas.
5. Use os botões auxiliares:
   - **Marcar Todos** — seleciona todas as opções
   - **Desmarcar Todos** — limpa a seleção
6. Clique em **Aplicar** para filtrar os dados.
7. Clique em **Limpar** para remover o filtro daquela coluna.
8. Clique em **Fechar** para fechar o painel sem alterar.

> **Importante**: Os filtros de funil funcionam em conjunto com os pré-filtros e a interação com gráficos. Todos se acumulam para refinar a análise.

### 5.3 Paginação

Na parte inferior da tela há a barra de paginação:

| Controle | Função |
|---|---|
| **\|<** | Ir para a primeira página |
| **<** | Página anterior |
| **Página X / Y** | Indica a página atual e total |
| **>** | Próxima página |
| **>\|** | Ir para a última página |
| **Picker de tamanho** | Alterar quantidade de registros por página (10, 20, 50 ou 100) |
| **Info de registros** | Mostra o intervalo exibido (ex.: "1-50 de 1.234") |

---

## 6. Cards de Dados (Mobile)

No celular (Android/iOS), em vez de tabela, os dados são exibidos como **cards** rolando verticalmente.

- Cada card mostra os campos selecionados da view.
- O **scroll infinito** carrega mais dados automaticamente ao chegar ao final da lista (sem necessidade de paginação manual).
- Um indicador de carregamento aparece no rodapé enquanto novos dados estão sendo baixados.
- Os **KPIs** e **gráficos** são exibidos acima dos cards.

---

## 7. Interação com Gráficos (Estilo Power BI)

Os gráficos do módulo Análises são **interativos**, funcionando de forma semelhante ao Power BI:

### Filtrando dados pelo gráfico

1. **Clique/toque em uma fatia** do gráfico de pizza ou em um **ponto** do gráfico de linha.
2. A fatia/ponto ficará **destacada** visualmente.
3. A tabela e os KPIs serão **atualizados automaticamente**, mostrando apenas os dados correspondentes ao item clicado.
4. Outros gráficos com colunas diferentes também podem ser clicados, **acumulando filtros** (ex.: clicar em "Empresa X" no gráfico de empresas e depois em "Jan/2026" no gráfico de datas).

### Removendo o filtro do gráfico

- **Clique/toque novamente** na mesma fatia ou ponto já selecionado.
- O destaque será removido e os dados voltarão ao estado anterior.

### Regras de acumulação

- Gráficos com **colunas diferentes** acumulam filtros (ex.: empresa + vendedor).
- Gráficos com a **mesma coluna de agrupamento** substituem a seleção (ex.: dois gráficos por empresa — ao clicar no segundo, o primeiro é desmarcado).

---

## 8. Presets (Configurações Salvas)

Presets permitem **salvar uma configuração completa** de análise para reutilizar depois, sem precisar reconfigurar filtros, campos, gráficos e KPIs toda vez.

### O que é salvo no preset
- Colunas selecionadas/ocultas
- Gráficos selecionados/ocultos
- KPIs selecionados/ocultos
- Filtros habilitados com seus valores (datas, seleções de empresa, vendedor, etc.)

### Salvando um preset

1. Configure a análise como desejar (filtros, campos, gráficos, KPIs).
2. Clique em **Salvar**:
   - Se **nenhum preset** estiver selecionado, será solicitado um nome para o novo preset.
   - Se um preset **já estiver selecionado**, ele será atualizado com a configuração atual.
3. Para salvar com um **nome diferente** (mantendo o original), clique em **Salvar Como** e informe o novo nome.

### Carregando um preset

1. No Picker de **Preset** (ao lado do campo Fonte), selecione o preset desejado.
2. As configurações serão aplicadas automaticamente (colunas, gráficos, KPIs e filtros).
3. Clique em **Carregar** para buscar os dados com a configuração do preset.

### Excluindo um preset

1. Selecione o preset que deseja excluir no Picker.
2. Clique em **Excluir**.
3. Confirme a exclusão na janela de confirmação.
4. O preset será removido e todas as configurações voltarão ao padrão (tudo visível).

> **Nota**: Presets são salvos por **usuário** e por **view**. Cada view pode ter seus próprios presets, e cada usuário tem os seus.

---

## 9. Exportação (XLSX / CSV)

Você pode exportar os dados da análise para arquivo Excel (XLSX) ou CSV.

### Como exportar

1. Carregue os dados da análise normalmente (Fonte → Filtros → Carregar).
2. Na barra de ferramentas superior da tela, localize os botões de exportação:
   - **XLSX** — Exporta para Excel (.xlsx)
   - **CSV** — Exporta para CSV (.csv)
3. Ao clicar, será exibido um diálogo com opções:
   - **Tudo** — Exporta todos os registros filtrados (todos que atendem os filtros, não apenas a página atual). Útil para extrações completas.
   - **Página** (desktop) / **Registros Carregados** (mobile) — Exporta apenas os registros visíveis na página atual ou carregados via scroll.
   - **Cancelar** — Cancela a exportação.
4. Escolha o local para salvar o arquivo.

### Sobre o arquivo gerado

- **Nome do arquivo**: `Export - {nome_da_view} - {data}.xlsx` (ou `.csv`).
  - Exemplo: `Export - view_comercial_pedidos_base - 2026-03-18.xlsx`
- **XLSX**: Formato Excel nativo, pode ser aberto diretamente no Excel, LibreOffice Calc, Google Sheets.
- **CSV**: Formato texto separado por vírgula/ponto-e-vírgula, abre diretamente no Excel.

> **Dica**: Use "Tudo" quando precisar de uma extração completa dos dados filtrados. Use "Página" para exportações rápidas de pequenos conjuntos.

---

## 10. Permissões Necessárias

O acesso às funcionalidades de Análises é controlado por permissões. A tabela abaixo lista as permissões e o que cada uma libera:

| Permissão | Descrição |
|---|---|
| `analises.menu` | Acesso ao módulo Análises no menu principal |
| `analises.main.view` | Acesso à tela principal de categorias |
| `analises.cadastros.view` | Acesso às análises de Cadastros |
| `analises.comercial.view` | Acesso às análises Comercial |
| `analises.compras.view` | Acesso às análises de Compras |
| `analises.fiscal.view` | Acesso às análises Fiscal |
| `analises.financeiro.view` | Acesso às análises Financeiro |
| `analises.estoque.view` | Acesso às análises de Estoque |
| `analises.pcp.view` | Acesso às análises de PCP |
| `analises.atendimento.view` | Acesso às análises de Atendimento |
| `analises.projetos.view` | Acesso às análises de Projetos |

> Se você não tem acesso a uma categoria, o botão correspondente **não aparecerá** na tela principal.

### Empresa Seletiva

- Se o seu usuário está vinculado a uma **empresa específica** (Empresa Seletiva), os dados serão filtrados automaticamente para essa empresa.
- O filtro de empresa ficará **travado** e não poderá ser alterado.
- Se estiver vinculado a **múltiplas empresas**, apenas essas aparecerão no filtro de empresa.
- Se não houver restrição (acesso total), todas as empresas estarão disponíveis.

---

## 11. Dicas e Perguntas Frequentes

### A tela mostra "Erro" ou "Conexão — Erro"
- Verifique sua conexão com a internet.
- Verifique se o servidor (API) está acessível.
- Se o problema persistir, faça logout e login novamente (o token de autenticação pode ter expirado).

### Os filtros não mostram opções
- Certifique-se de que a view está selecionada.
- Verifique se o filtro está **habilitado** (checkbox marcado).
- Para filtros de busca (Lookup), é necessário digitar pelo menos **2 caracteres**.

### A tabela aparece vazia após carregar
- Verifique se os filtros não estão restritivos demais (datas muito curtas, empresa sem dados, etc.).
- Use o botão **Limpar** para resetar tudo e tente novamente.
- Verifique se há colunas selecionadas no painel de **Campos**.

### Como ver mais registros por página?
- Na barra de paginação (rodapé), use o **Picker de tamanho de página** e selecione 50 ou 100.

### Posso usar no celular?
- Sim! No celular os dados aparecem como cards com scroll infinito. Os KPIs e gráficos funcionam normalmente.

### Como filtrar clicando no gráfico?
- Basta tocar/clicar em uma fatia do gráfico de pizza ou em um ponto do gráfico de linha. A fatia ficará destacada e os dados serão filtrados. Toque novamente para remover o filtro.

### Os presets são compartilhados entre usuários?
- Não. Cada usuário tem seus próprios presets. Eles ficam salvos no servidor e podem ser acessados de qualquer dispositivo.

### A exportação "Tudo" demora muito
- A opção "Tudo" baixa todos os registros filtrados do servidor. Em views com muitos dados, pode demorar. Use filtros para reduzir o volume antes de exportar.

### Posso imprimir os dados?
- A funcionalidade de impressão está desabilitada na versão atual. Use a exportação para XLSX/CSV e imprima pelo Excel.

---

> **Precisa de ajuda?** Entre em contato com o administrador do sistema ou com a equipe de suporte.