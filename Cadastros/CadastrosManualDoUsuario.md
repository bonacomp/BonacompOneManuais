# Bonacomp One — Manual do Usuário: Cadastros

> **Documento**: Cadastros Manual do Usuário
> **Versão do App**: 1.0.493
> **Plataforma**: .NET MAUI 10.0.20
> **Última atualização**: 2026-03-18

---

## Sumário

- [1. Visão Geral](#1-visão-geral)
- [2. Acesso ao Módulo](#2-acesso-ao-módulo)
- [3. Lista de Pessoas](#3-lista-de-pessoas)
- [4. Formulário de Pessoa](#4-formulário-de-pessoa)
- [5. Criando um Usuário do Sistema](#5-criando-um-usuário-do-sistema)
- [6. Gerenciando Permissões](#6-gerenciando-permissões)
- [7. Permissões Necessárias](#7-permissões-necessárias)
- [8. Perguntas Frequentes](#8-perguntas-frequentes)

---

## 1. Visão Geral

O módulo **Cadastros** é responsável pelo cadastro e manutenção de **Pessoas** no Bonacomp One. Uma pessoa pode ter múltiplos papéis simultâneos: cliente, fornecedor, vendedor, comprador, funcionário, empresa e **usuário do sistema**.

A funcionalidade principal deste módulo é o **cadastro unificado**: uma única pessoa pode ser ao mesmo tempo cliente e vendedor, por exemplo. Ao marcar o papel "Usuário", a pessoa ganha credenciais de acesso ao sistema e permissões configuráveis.

---

## 2. Acesso ao Módulo

### Pela Tela Inicial (Home)
1. Faça login no sistema
2. Na tela inicial, toque em **Cadastros**
3. Toque em **Pessoas**

### Pelo Menu Lateral (Flyout)
1. Abra o menu lateral (ícone ☰ no desktop, ou deslize da esquerda no mobile)
2. Toque em **Cadastros**
3. Toque em **Pessoas**

> O botão "Cadastros" só aparece se você tem a permissão `cadastros.menu`. O botão "Pessoas" só aparece com `cadastros.pessoas.view`.

---

## 3. Lista de Pessoas

A lista de pessoas exibe todas as pessoas cadastradas no sistema.

### No Desktop (Windows)
- Exibição em **tabela** com colunas: Nome e Fantasia
- **Ordenar**: clique no cabeçalho da coluna
- **Filtrar**: use o ícone de funil no cabeçalho da coluna
- **Paginação**: navegue entre páginas na barra inferior (50 registros por página)

### No Mobile (Android)
- Exibição em **cards** com Nome e Nome Fantasia
- **Scroll infinito**: novos registros carregam automaticamente ao rolar

### Toolbar (barra de ações)

| Ícone | Ação | Permissão |
|-------|------|-----------|
| **+** (Novo) | Abre formulário para nova pessoa | `cadastros.pessoas.create` |
| ✏️ (Editar) | Abre formulário da pessoa selecionada | `cadastros.pessoas.edit` |
| 🗑️ (Excluir) | Desativa a pessoa selecionada | `cadastros.pessoas.delete` |
| 🔍 (Pesquisar) | Abre campo de busca por nome, fantasia ou CPF/CNPJ | Sempre visível |
| ❓ (Ajuda) | Abre o guia rápido no navegador | Sempre visível |

### Pesquisa
1. Toque no ícone de **Pesquisar** (🔍)
2. Digite o termo de busca (nome, fantasia ou documento)
3. A lista é filtrada automaticamente no servidor
4. Para limpar, apague o texto ou feche o painel de pesquisa

### Excluir no Desktop (múltipla seleção)
1. Marque os checkboxes das pessoas que deseja excluir
2. Toque em **Excluir** (🗑️)
3. Confirme na caixa de diálogo

---

## 4. Formulário de Pessoa

O formulário de pessoa possui uma **área fixa** (sempre visível) e **abas dinâmicas** que aparecem conforme os papéis marcados.

### Área Fixa

| Campo | Descrição | Obrigatório? |
|-------|-----------|-------------|
| **Tipo** | Pessoa Física (PF) ou Pessoa Jurídica (PJ) | Sim (padrão: PF) |
| **Ativo** | Checkbox — pessoa ativa no sistema | Não (padrão: marcado) |
| **Nome / Razão Social** | Nome completo ou razão social | **Sim** |
| **Nome Fantasia** | Nome fantasia ou apelido | Não |
| **CPF / CNPJ** | Documento principal | Não |
| **RG / IE** | RG (pessoa física) ou Inscrição Estadual (jurídica) | Não |

### Papéis (checkboxes)

Abaixo dos campos fixos, há checkboxes para definir os papéis da pessoa:

| Papel | Aba gerada | Descrição |
|-------|-----------|-----------|
| **Cliente** | Cliente | Dados específicos de cliente |
| **Fornecedor** | Fornecedor | Dados de fornecedor |
| **Vendedor** | Vendedor | Dados de vendedor |
| **Comprador** | Comprador | Dados de comprador |
| **Funcionário** | — | Apenas marca como funcionário |
| **Empresa** | Empresa | Vincula a uma empresa do sistema |
| **Usuário** | Usuário | Credenciais de login + permissões |

> Ao marcar ou desmarcar um papel, as abas correspondentes aparecem ou desaparecem automaticamente.

### Abas Sempre Visíveis

| Aba | Conteúdo |
|-----|----------|
| **Endereços** | Lista de endereços cadastrados (logradouro, número, bairro, cidade, UF, CEP) |
| **Contatos** | Telefones (tipo + número) e e-mails (tipo + e-mail) |
| **Detalhes** | Data de nascimento e observações |

### Salvar
- Toque em **Salvar** (💾) na toolbar
- O sistema valida o nome (obrigatório) e a senha (se preenchida)
- Se a pessoa é usuário com permissões alteradas, as permissões são salvas junto

### Cancelar
- Toque em **Cancelar** (✕) na toolbar
- Confirme que deseja sair sem salvar
- Retorna à lista de pessoas

---

## 5. Criando um Usuário do Sistema

Para que uma pessoa possa fazer login no Bonacomp One, ela precisa ter o papel **Usuário** com credenciais configuradas.

### Passo a passo

1. **Abra o formulário** — crie uma nova pessoa ou edite uma existente
2. **Marque o checkbox "Usuário"** na seção de Papéis
3. A aba **Usuário** aparecerá automaticamente (requer permissão `admin.users.manage`)
4. Selecione a aba **Usuário**

### Campos da aba Usuário

| Campo | Descrição | Observação |
|-------|-----------|-----------|
| **Login API** | Nome de usuário para login | Único no sistema |
| **Empresa Seletiva** | IDs das empresas que o usuário pode acessar | `0` = todas. Vários IDs separados por vírgula (ex: `1,3,5`) |
| **Senha** | Senha de acesso | Mínimo 4 caracteres. Em branco = mantém a senha atual (edição) |
| **Repetir Senha** | Confirmação da senha | Deve ser idêntica ao campo Senha |

### Sobre a Empresa Seletiva

A Empresa Seletiva controla **quais dados das empresas** o usuário consegue ver e operar:

| Valor | Significado |
|-------|-------------|
| `0` | Acesso a **todas** as empresas |
| `1` | Apenas empresa 1 |
| `1,3,5` | Empresas 1, 3 e 5 |
| Vazio | Mesmo que `0` (todas) |

### Visibilidade da senha
- Use o ícone de **olho** (👁️) ao lado do campo de senha para alternar entre mostrar/ocultar a senha
- O botão funciona nos dois campos simultaneamente

### Validações

| Regra | Mensagem |
|-------|---------|
| Senha com menos de 4 caracteres | "Senha deve ter pelo menos 4 caracteres" |
| Senhas não conferem | "As senhas não conferem" |
| Nome em branco | "Nome é obrigatório" |

---

## 6. Gerenciando Permissões

Ao abrir a aba **Usuário**, a lista de permissões é carregada automaticamente. Cada permissão é exibida como um **checkbox** com a chave da permissão.

### Como atribuir permissões

1. Abra o formulário da pessoa
2. Marque o checkbox **Usuário** (se ainda não estiver marcado)
3. Selecione a aba **Usuário**
4. Role até a seção **Permissões**
5. Marque os checkboxes das permissões desejadas
6. Toque em **Salvar** — as permissões são salvas junto com os demais dados

### Permissões disponíveis

As permissões seguem o padrão `modulo.recurso.acao`. Exemplos:

| Chave | O que permite |
|-------|-------------|
| `cadastros.menu` | Ver o módulo Cadastros no menu |
| `cadastros.pessoas.view` | Listar pessoas |
| `cadastros.pessoas.create` | Criar nova pessoa |
| `cadastros.pessoas.edit` | Editar pessoa existente |
| `cadastros.pessoas.delete` | Excluir/desativar pessoa |
| `analises.menu` | Ver o módulo Análises no menu |
| `analises.comercial.view` | Ver análises comerciais |
| `admin.users.manage` | Gerenciar usuários (aba Usuário aparece) |
| `config.global.view` | Ver Configurações Globais |

> **Importante**: ao criar uma pessoa nova como usuário, primeiro salve a pessoa (o sistema atribui um ID) e depois as permissões são salvas automaticamente na mesma operação.

### Pessoa nova vs. pessoa existente

| Cenário | Comportamento das permissões |
|---------|------------------------------|
| **Pessoa nova** | Catálogo completo (todas desmarcadas) |
| **Pessoa existente** | Catálogo com marcações reais do banco |

---

## 7. Permissões Necessárias

Para operar no módulo de Cadastros, o seu usuário precisa das seguintes permissões:

| Ação | Permissão necessária |
|------|---------------------|
| Ver "Cadastros" no menu/home | `cadastros.menu` |
| Listar pessoas | `cadastros.pessoas.view` |
| Criar pessoa | `cadastros.pessoas.create` |
| Editar pessoa | `cadastros.pessoas.edit` |
| Excluir/desativar pessoa | `cadastros.pessoas.delete` |
| Ver aba "Usuário" no formulário | `admin.users.manage` |

> Se você não vê algum botão ou módulo, peça ao administrador que verifique suas permissões.

---

## 8. Perguntas Frequentes

**Não vejo o botão "Cadastros" na tela inicial**
Você precisa da permissão `cadastros.menu`. Peça ao administrador.

**Não consigo criar novas pessoas**
O botão "Novo" (+) requer a permissão `cadastros.pessoas.create`.

**Não vejo a aba "Usuário" no formulário**
A aba aparece quando: (1) o checkbox "Usuário" está marcado E (2) você tem a permissão `admin.users.manage`.

**A senha não está sendo alterada**
Se o campo de senha estiver em branco ao salvar, a senha anterior é mantida. Preencha os dois campos de senha para alterar.

**A pessoa foi excluída mas continua aparecendo**
A exclusão **desativa** a pessoa (campo Ativo = desmarcado), não remove do banco de dados.

**Como dar acesso total a um novo usuário?**
Marque todas as permissões na aba "Usuário". Coloque `0` no campo Empresa Seletiva para acesso a todas as empresas.

**Posso ter um vendedor que também é usuário?**
Sim! Marque ambos os checkboxes: "Vendedor" e "Usuário". Cada papel tem sua aba independente.

**O campo "Empresa Seletiva" aceita texto?**
Sim, aceita IDs separados por vírgula. Exemplo: `1,3,5` restringe o acesso às empresas 1, 3 e 5.
