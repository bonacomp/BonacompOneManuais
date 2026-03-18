# Bonacomp One — Guia Rápido: Cadastros

> **Documento**: Cadastros Guia Rápido
> **Versão do App**: 1.0.493
> **Plataforma**: .NET MAUI 10.0.20
> **Última atualização**: 2026-03-18

---

## ⭐ Criar um Usuário do Sistema (passo a passo completo)

1. Menu → **Cadastros** → **Pessoas**
2. Toque em **Novo** (+) na toolbar
3. Preencha o **Nome** (obrigatório)
4. Marque o checkbox **Usuário** nos Papéis
5. Selecione a aba **Usuário**
6. Preencha o **Login API** (nome de login)
7. Preencha **Empresa Seletiva** (`0` = todas, ou IDs como `1,3,5`)
8. Preencha a **Senha** (mínimo 4 caracteres)
9. Repita a senha em **Repetir Senha**
10. Marque as **permissões** desejadas (checkboxes)
11. Toque em **Salvar** (💾)

> Pronto! O novo usuário já pode fazer login com as credenciais definidas.

---

## Listar Pessoas

1. Menu → **Cadastros** → **Pessoas**
2. A lista carrega automaticamente
3. Use **Pesquisar** (🔍) para filtrar por nome, fantasia ou documento

---

## Criar Nova Pessoa

1. Na lista de pessoas, toque em **Novo** (+)
2. Escolha **PF** ou **PJ**
3. Preencha o **Nome** (obrigatório)
4. Marque os **papéis** desejados (Cliente, Fornecedor, Vendedor, etc.)
5. Preencha as abas que apareceram (Endereços, Contatos, etc.)
6. Toque em **Salvar** (💾)

---

## Editar Pessoa

**Desktop**: clique duplo na pessoa da tabela ou selecione e toque em **Editar** (✏️)
**Mobile**: toque na pessoa no card

---

## Excluir Pessoa

1. Selecione a pessoa (ou marque checkboxes no desktop)
2. Toque em **Excluir** (🗑️)
3. Confirme → a pessoa é **desativada** (não é apagada)

---

## Gerenciar Permissões de um Usuário

1. Abra o formulário da pessoa (editar)
2. Certifique-se de que **Usuário** está marcado nos Papéis
3. Selecione a aba **Usuário**
4. Marque/desmarque as permissões nos checkboxes
5. Toque em **Salvar** (💾) — permissões são salvas junto

### Permissões principais

| Chave | Permite |
|-------|---------|
| `cadastros.menu` | Ver Cadastros no menu |
| `cadastros.pessoas.view` | Listar pessoas |
| `cadastros.pessoas.create` | Criar pessoa |
| `cadastros.pessoas.edit` | Editar pessoa |
| `cadastros.pessoas.delete` | Excluir pessoa |
| `analises.menu` | Ver Análises no menu |
| `analises.comercial.view` | Ver análises comerciais |
| `admin.users.manage` | Gerenciar usuários |
| `config.global.view` | Configurações globais |

---

## Alterar Senha de Usuário

1. Abra o formulário da pessoa
2. Aba **Usuário**
3. Preencha **Senha** (mínimo 4 caracteres)
4. Repita em **Repetir Senha**
5. **Salvar** — se deixar em branco, a senha anterior é mantida

---

## Campos da Pessoa

| Campo | Descrição |
|-------|-----------|
| Tipo | PF (física) ou PJ (jurídica) |
| Ativo | Se desmarcado, a pessoa fica inativa |
| Nome / Razão Social | **Obrigatório** |
| Nome Fantasia | Opcional |
| CPF / CNPJ | Documento principal |
| RG / IE | Documento secundário |

---

## Papéis e Abas

| Papel marcado | Aba que aparece |
|---------------|----------------|
| Cliente | Cliente |
| Fornecedor | Fornecedor |
| Vendedor | Vendedor |
| Comprador | Comprador |
| Empresa | Empresa |
| Usuário | Usuário (requer `admin.users.manage`) |

As abas **Endereços**, **Contatos** e **Detalhes** são sempre visíveis.

---

## Empresa Seletiva

| Valor | Significado |
|-------|-------------|
| `0` | Todas as empresas |
| `1` | Apenas empresa 1 |
| `1,3,5` | Empresas 1, 3 e 5 |
| Vazio | Mesmo que `0` |

---

## Referência Rápida

| Quero... | Faço... |
|----------|---------|
| Criar pessoa | Novo (+) → preencher → Salvar |
| Criar usuário | Novo → marcar "Usuário" → aba Usuário → login + senha + permissões → Salvar |
| Editar pessoa | Desktop: duplo-clique / Mobile: toque no card |
| Excluir pessoa | Selecionar → Excluir → Confirmar |
| Alterar permissões | Editar pessoa → aba Usuário → marcar/desmarcar → Salvar |
| Alterar senha | Editar pessoa → aba Usuário → nova senha → Salvar |
| Buscar por nome | Pesquisar (🔍) → digitar |
| Abrir ajuda | Toque em **?** na toolbar |
