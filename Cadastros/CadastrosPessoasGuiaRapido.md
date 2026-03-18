# Bonacomp One — Guia Rápido: Cadastro de Pessoas

> **Documento**: Cadastros Pessoas Guia Rápido
> **Versão do App**: 1.0.493
> **Plataforma**: .NET MAUI 10.0.20
> **Última atualização**: 2026-03-18

---

## ⭐ Criar um Usuário do Sistema

1. **Novo** (+) na toolbar
2. Preencha o **Nome** (obrigatório)
3. Marque **Usuário** nos Papéis
4. Aba **Usuário** → preencha **Login API**, **Empresa Seletiva**, **Senha** e **Repetir Senha**
5. Marque as **permissões** desejadas
6. **Salvar** (💾)

> Pronto! O novo usuário já pode fazer login.

---

## Criar Nova Pessoa

1. **Novo** (+) → Escolha PF ou PJ
2. Preencha o **Nome** (obrigatório)
3. Marque os papéis (Cliente, Fornecedor, Vendedor, etc.)
4. Preencha as abas que apareceram
5. **Salvar** (💾)

---

## Editar

- **Desktop**: duplo-clique na tabela, ou selecione + **Editar** (✏️)
- **Mobile**: toque no card

---

## Excluir

1. Selecione a pessoa (checkbox no desktop / toque no mobile)
2. **Excluir** (🗑️) → Confirme
3. A pessoa é **desativada** (não apagada)

---

## Pesquisar

**Pesquisar** (🔍) → digite nome, fantasia ou documento → a lista filtra automaticamente

---

## Alterar Permissões

1. **Editar** a pessoa
2. Aba **Usuário**
3. Marque/desmarque os checkboxes
4. **Salvar** (💾)

---

## Alterar Senha

1. **Editar** a pessoa → aba **Usuário**
2. Preencha **Senha** (mínimo 4 caracteres) + **Repetir Senha**
3. **Salvar** — em branco = mantém a senha atual

---

## Papéis e Abas

| Papel | Aba |
|-------|-----|
| Cliente | Cliente |
| Fornecedor | Fornecedor |
| Vendedor | Vendedor |
| Comprador | Comprador |
| Empresa | Empresa |
| Usuário | Usuário (requer permissão `admin.users.manage`) |

Abas **Endereços**, **Contatos** e **Detalhes** são sempre visíveis.

---

## Empresa Seletiva

| Valor | Significado |
|-------|-------------|
| `0` | Todas as empresas |
| `1,3,5` | Apenas empresas 1, 3 e 5 |
| Vazio | Mesmo que `0` |

---

## Permissões Principais

| Chave | Permite |
|-------|---------|
| `cadastros.menu` | Ver Cadastros no menu |
| `cadastros.pessoas.view` | Listar pessoas |
| `cadastros.pessoas.create` | Criar pessoa |
| `cadastros.pessoas.edit` | Editar pessoa |
| `cadastros.pessoas.delete` | Excluir pessoa |
| `analises.menu` | Ver Análises |
| `admin.users.manage` | Gerenciar usuários |
| `config.global.view` | Configurações globais |

---

## Referência Rápida

| Quero... | Faço... |
|----------|---------|
| Criar pessoa | Novo → preencher → Salvar |
| Criar usuário | Novo → "Usuário" → aba Usuário → login + senha + permissões → Salvar |
| Editar | Duplo-clique (desktop) / toque (mobile) |
| Excluir | Selecionar → Excluir → Confirmar |
| Alterar permissões | Editar → aba Usuário → checkboxes → Salvar |
| Alterar senha | Editar → aba Usuário → senha → Salvar |
| Buscar | Pesquisar (🔍) → digitar |
