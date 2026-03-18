# Bonacomp One — Guia Rápido: Menu e Configuração Inicial

> **Documento**: Menu Guia Rápido
> **Versão do App**: 1.0.477
> **Plataforma**: .NET MAUI 10.0.20
> **Última atualização**: 2026-03-18

## Sumário

- [Configurar a Conexão (primeira vez)](#configurar-a-conexão-primeira-vez)
- [Fazer Login](#fazer-login)
- [Login por Biometria (celular)](#login-por-biometria-celular)
- [Navegar pelos Módulos](#navegar-pelos-módulos)
- [Abrir o Menu Lateral](#abrir-o-menu-lateral)
- [Sair / Trocar de Usuário](#sair--trocar-de-usuário)
- [Testar a Conexão](#testar-a-conexão)
- [Referência Rápida](#referência-rápida)

---

## Configurar a Conexão (primeira vez)

1. Abra o app → na tela de Login, toque no **⚙️** (engrenagem, canto superior direito)
2. Toque em **Conexões** → toque em **+** (adicionar)
3. Preencha os campos obrigatórios:

| Campo | O que preencher |
|---|---|
| **Descrição** | Nome da conexão (ex: "Produção") |
| **Endereço Externo HTTPS** | `https://api.suaempresa.com.br` |
| **Endereço Local HTTP** | `http://192.168.1.100:5000` (se aplicável) |

> Preencha **pelo menos um** dos endereços (HTTPS ou HTTP). Os demais campos são opcionais. Os campos **Identificador** e **Identificador Senha** não são utilizados no momento.

4. (Opcional) Marque **Conexão padrão** para selecionar automaticamente no login
5. (Opcional) Preencha **Usuário** e **Senha** → ative **Salvar senha** para preencher automaticamente no login
6. (Opcional) Ative **Usar biometria** para login por digital no celular
7. Toque em **Salvar** (ícone de disquete)
8. Volte para a tela de Login

## Fazer Login

1. Selecione a **Conexão** no picker
2. Preencha **Usuário** e **Senha**
3. Toque em **Entrar**
4. Pronto — você está na **Tela Inicial (Home)** com os módulos disponíveis

## Login por Biometria (celular)

1. A conexão precisa ter **Salvar senha** + **Usar biometria** ativos
2. Ao abrir o app, a autenticação por digital é disparada automaticamente
3. Valide sua digital → login feito automaticamente

## Navegar pelos Módulos

Na **Tela Inicial (Home)**, toque no botão do módulo desejado:
- **Cadastros** — módulo de cadastros gerais
- **Análises** — análises de dados
- **Configurações Globais** — configurações do sistema

> Os botões dependem das permissões do seu usuário. Se nenhum botão aparecer, fale com o administrador.

## Abrir o Menu Lateral

| Plataforma | Como abrir |
|---|---|
| **Desktop** | Clique no **☰** (canto superior esquerdo) |
| **Celular** | Deslize o dedo **da esquerda para a direita** ou toque no **☰** |

O menu mostra: **Home**, **Configurações**, módulos (Cadastros, Análises), **Sair** e **Fechar**.

> No topo do menu: versão do APP e da API (útil para suporte).

## Sair / Trocar de Usuário

1. Abra o **menu lateral** (☰)
2. Toque em **Sair**
3. Você volta para a tela de Login
4. Selecione outra conexão ou preencha outro usuário → **Entrar**

## Testar a Conexão

1. Na tela de Login, toque no **⚙️** → **Conexões** → toque na conexão
2. Toque no botão **Testar** (ícone de play/build)
3. O resultado aparece: **OK**, **Não respondeu** ou **Erro**

---

## Referência Rápida

| Quero... | Faço... |
|---|---|
| Configurar conexão pela primeira vez | ⚙️ → Conexões → **+** → preencher endereço(s) → Salvar |
| Fazer login | Selecionar conexão → Usuário → Senha → **Entrar** |
| Login por digital (celular) | Abrir o app → autenticar digital automaticamente |
| Abrir um módulo | Home → tocar no botão do módulo |
| Trocar de módulo | Menu lateral (☰) → tocar no módulo |
| Sair (logout) | Menu lateral (☰) → **Sair** |
| Fechar o app | Menu lateral (☰) → **Fechar** |
| Trocar de conexão | Sair → selecionar outra conexão → Entrar |
| Trocar de empresa | Sair → alterar campo Empresas → Entrar |
| Testar conexão | ⚙️ → Conexões → selecionar → **Testar** |
| Ver versão do app/API | Abrir menu lateral → ver cabeçalho no topo |
