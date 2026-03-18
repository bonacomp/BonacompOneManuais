# Bonacomp One — Manual do Usuário: Menu e Configuração Inicial

> **Documento**: Menu Manual Do Usuário
> **Versão do App**: 1.0.477
> **Plataforma**: .NET MAUI 10.0.20
> **Última atualização**: 2026-03-18

## Sumário

- [Visão Geral](#visão-geral)
- [Configuração da Conexão](#configuração-da-conexão)
- [Tela de Login](#tela-de-login)
- [Tela Inicial (Home)](#tela-inicial-home)
- [Menu Lateral (Flyout)](#menu-lateral-flyout)
- [Sair e Fechar](#sair-e-fechar)
- [Dicas e Perguntas Frequentes](#dicas-e-perguntas-frequentes)

---

## Visão Geral

O Bonacomp One é um aplicativo que funciona em **desktop (Windows)** e **celular (Android/iOS)**. Antes de usar qualquer módulo, você precisa configurar a conexão com o servidor e fazer login. Este manual explica esse fluxo inicial — da configuração até a tela principal.

---

## Configuração da Conexão

Ao abrir o app pela primeira vez, não há nenhuma conexão cadastrada. Você precisa criar pelo menos uma para se conectar ao servidor.

### Como acessar a configuração

1. Na tela de Login, toque no **ícone de engrenagem** (⚙️) no canto superior direito
2. Você será levado à tela **Configuração Local**
3. Toque em **Conexões**
4. Toque no botão **+** (adicionar) para criar uma nova conexão

### Campos do formulário de conexão

| Campo | Obrigatório? | O que preencher |
|---|---|---|
| **Descrição** | ✅ Sim | Nome para identificar a conexão (ex: "Servidor Produção", "Rede Local") |
| **Conexão padrão** | Opcional | Marque para que esta conexão seja selecionada automaticamente no login |
| **Endereço Externo HTTPS** | ✅ Sim* | URL da API com HTTPS (ex: `https://api.suaempresa.com.br`) |
| **Endereço Local HTTP** | ✅ Sim* | URL da API em rede local com HTTP (ex: `http://192.168.1.100:5000`) |
| **Identificador** | — | **Não utilizado no momento** — pode deixar em branco |
| **Identificador Senha** | — | **Não utilizado no momento** — pode deixar em branco |
| **Usuário** | Opcional | Seu usuário do sistema (será salvo localmente se **Salvar senha** estiver ativo) |
| **Senha** | Opcional | Sua senha do sistema (será salva localmente se **Salvar senha** estiver ativo) |
| **Empresa** | Opcional | Código(s) da empresa. `0` = todas. Para empresas específicas: `1,2,5` (separadas por vírgula) |
| **Salvar senha** | Opcional | Ativa o salvamento do usuário e senha no dispositivo para preenchimento automático |
| **Usar biometria** | Opcional | Ativa login por impressão digital/reconhecimento facial (somente celular) |

> **Importante**: Pelo menos um dos endereços (HTTPS ou HTTP) deve ser preenchido. Você pode preencher ambos — o app tentará primeiro o HTTPS e, se não conectar, tentará o HTTP automaticamente.

### Testar a conexão

Antes de salvar, você pode testar se o endereço está respondendo:

1. Preencha pelo menos um endereço (HTTPS ou HTTP)
2. Toque no botão **Testar** (ícone de play/build na toolbar)
3. O app exibirá o resultado para cada endereço preenchido:
   - **OK** — o servidor respondeu
   - **Não respondeu** — verifique o endereço ou a conexão de rede
   - **Erro** — problema na comunicação (detalhes são exibidos)

### Salvar a conexão

Após preencher os campos, toque no botão **Salvar** (ícone de disquete na toolbar). Você voltará para a lista de conexões.

### Gerenciar conexões

Na lista de conexões, você pode:
| Ação | Como fazer |
|---|---|
| **Editar** | Toque na conexão desejada |
| **Excluir** | Selecione a conexão → toque no botão **Excluir** (ícone de lixeira) |
| **Duplicar** | Selecione a conexão → toque em **Duplicar** → edite os dados → Salve |
| **Adicionar nova** | Toque no botão **+** |

---

## Tela de Login

Após configurar pelo menos uma conexão, volte à tela de Login.

### Campos do login

| Campo | Descrição |
|---|---|
| **Conexão** | Selecione a conexão desejada no picker (a conexão marcada como padrão já vem selecionada) |
| **Usuário** | Digite seu nome de usuário (preenchido automaticamente se **Salvar senha** estiver ativo na conexão) |
| **Senha** | Digite sua senha (campo oculto por padrão — segure o ícone do olho para visualizar) |
| **Empresas** | Código(s) da empresa. `0` = todas as empresas que você tem acesso |

### Como fazer login

1. Selecione a **Conexão** no picker
2. Preencha **Usuário** e **Senha**
3. Toque em **Entrar**
4. Aguarde — o app tentará conectar ao servidor (primeiro HTTPS, depois HTTP se necessário)
5. Se o login for bem-sucedido, você será levado à **Tela Inicial (Home)**

### Login por biometria (celular)

Se a conexão tiver **Salvar senha** e **Usar biometria** ativos:

1. No **Android**, a autenticação por digital é disparada automaticamente ao abrir o app
2. Valide sua digital ou reconhecimento facial
3. O login será feito automaticamente com o usuário e senha salvos

> **Nota**: No desktop (Windows), a biometria não está disponível. Use usuário e senha normalmente.

### Erros comuns no login

| Mensagem | Causa | O que fazer |
|---|---|---|
| "Nenhuma conexão selecionada" | O picker está vazio | Acesse ⚙️ e configure uma conexão |
| "Nenhum endereço de API configurado" | A conexão não tem HTTPS nem HTTP | Edite a conexão e preencha um endereço |
| "Não foi possível conectar à API" | O servidor não respondeu | Verifique o endereço, a rede ou se a API está online |
| "Login inválido" | Usuário ou senha incorretos | Verifique as credenciais |

---

## Tela Inicial (Home)

Após o login, você verá a **Tela Inicial** com botões para os módulos disponíveis. Os botões que aparecem dependem das **permissões do seu usuário**.

### Módulos possíveis

| Botão | Descrição | Permissão necessária |
|---|---|---|
| **Cadastros** | Módulo de cadastros gerais | `cadastros.menu` |
| **Análises** | Módulo de análises de dados (estilo Power BI) | `analises.menu` |
| **Configurações Globais** | Configurações do sistema (ex: paleta de cores, dados gerais) | `configglobal.view` |

> **Nota**: Se nenhum botão aparecer, significa que seu usuário não tem permissão para nenhum módulo. Fale com o administrador do sistema.

Cada módulo tem seu próprio manual:
- **Análises**: consulte o [Manual do Usuário — Análises](AnalisesManualDoUsuario.md)

---

## Menu Lateral (Flyout)

O menu lateral (Flyout) permite navegar entre os módulos a qualquer momento, sem voltar à Tela Inicial.

### Como abrir o menu

| Plataforma | Como abrir |
|---|---|
| **Desktop (Windows)** | Clique no ícone **☰** (três linhas horizontais) no canto superior esquerdo da tela |
| **Celular (Android/iOS)** | Deslize o dedo **da esquerda para a direita** na borda da tela, ou toque no ícone **☰** |

### Itens do menu

O menu lateral mostra:

| Item | Descrição |
|---|---|
| **Cabeçalho** | Nome do app ("Bonacomp One") + versão do APP e da API |
| **Home** | Volta para a Tela Inicial |
| **Configurações** | Acessa as Configurações Globais (se tiver permissão) |
| **Cadastros** | Abre o módulo de Cadastros (se tiver permissão) |
| **Análises** | Abre o módulo de Análises (se tiver permissão) |
| **Sair** | Faz logout e volta para a tela de Login |
| **Fechar** | Encerra o aplicativo completamente |

> **Nota**: Os itens **Cadastros**, **Análises** e **Configurações** só aparecem se o seu usuário tiver a permissão correspondente.

### Cabeçalho do menu

No topo do menu lateral, você verá:
- **Bonacomp One** — nome do aplicativo
- **APP: v1.0.477 | API: v1.0.0** — versão do app instalado e da API conectada

Essa informação é útil para suporte — se tiver algum problema, informe essas versões ao administrador.

### Navegação pelo Flyout

- Ao tocar em um módulo no menu, ele é aberto diretamente
- O menu fecha automaticamente após selecionar um item
- Você pode abrir o menu a qualquer momento para trocar de módulo
- Não é necessário voltar à Home para navegar entre módulos

---

## Sair e Fechar

| Ação | O que faz |
|---|---|
| **Sair** | Faz logout — desconecta do servidor e volta para a tela de Login. Você pode fazer login novamente com outro usuário ou outra conexão. |
| **Fechar** | Encerra o aplicativo completamente. |

Ambas as ações estão disponíveis no **menu lateral (Flyout)**.

---

## Dicas e Perguntas Frequentes

**Como trocar de conexão?**
Faça **Sair** (logout) pelo menu lateral → na tela de Login, selecione outra conexão no picker → faça login novamente.

**Como trocar de empresa?**
Faça **Sair** → na tela de Login, altere o campo **Empresas** (ex: de `0` para `3`) → faça login novamente.

**O app diz "Não foi possível conectar à API" — o que fazer?**
- Verifique se o servidor está ligado e acessível
- Verifique se o endereço está correto na configuração da conexão
- Se estiver em rede local, verifique se o Wi-Fi ou cabo está conectado
- Tente usar o botão **Testar** na configuração da conexão para diagnosticar

**O que é o endereço HTTPS vs HTTP?**
- **HTTPS** (Endereço Externo): usa criptografia, funciona pela internet. É o recomendado.
- **HTTP** (Endereço Local): sem criptografia, funciona apenas na rede local da empresa. Útil quando o HTTPS não está disponível.
- Se ambos estiverem preenchidos, o app tenta HTTPS primeiro. Se falhar, tenta HTTP automaticamente.

**Posso ter mais de uma conexão?**
Sim. Você pode criar várias conexões (ex: uma para produção, outra para testes, outra para rede local) e alternar entre elas no login.

**Para que serve a biometria?**
No celular, permite fazer login usando sua digital ou reconhecimento facial em vez de digitar a senha toda vez. Para funcionar, a conexão precisa ter **Salvar senha** e **Usar biometria** ativos.

**Os campos "Identificador" e "Identificador Senha" — preciso preencher?**
Não. Esses campos **não são utilizados no momento** e podem ser deixados em branco.

**Esqueci minha senha — como recuperar?**
O aplicativo não tem recurso de recuperação de senha. Fale com o administrador do sistema para redefinir sua senha.
