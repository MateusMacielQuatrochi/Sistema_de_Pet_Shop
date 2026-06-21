# 🐾 Sistema Web de Adoção de Pets

Este é um sistema de gerenciamento de adoção de animais desenvolvido como aplicação web. O software foi construído utilizando o ambiente **Node.js** com o framework **Express**, implementando controle de sessões de usuário, persistência temporária de dados na memória do servidor e gerenciamento de cookies para rastreamento de acessos.

O fluxo do sistema integra o cadastro de **Interessados (Adotantes)**, o cadastro de **Pets** disponíveis e o **Registro de Manifestações de Interesse/Desejo de Adoção**.

---

## 🛠️ Tecnologias Utilizadas

* **Runtime:** Node.js
* **Framework Web:** Express.js (v4.19.2)
* **Controle de Sessão:** `express-session` (v1.18.0)
* **Manipulação de Cookies:** `cookie-parser` (v1.4.6)
* **Front-End:** HTML5, CSS3 integrado e Bootstrap 5

---

## 📂 Estrutura de Arquivos do Projeto

```text
├── index.js                     # Arquivo principal do servidor (Rotas e Regras de Negócio)
├── package.json                 # Definição de dependências e scripts do projeto
├── package-lock.json            # Árvore de dependências trancada do npm
├── publico/                     # Diretório público (Acesso livre)
│   └── login.html               # Tela de autenticação do sistema
└── protegido/                   # Diretório protegido (Exige login ativo)
    ├── index.html               # Menu principal e painel do sistema
    ├── cadastroUsuario.html     # Formulário de novos adotantes interessados
    └── cadastroPets.html        # Formulário de inclusão de novos animais
```

🔐 Segurança e Regras de Autenticação
---
O sistema possui uma camada de proteção por meio de Middleware (usuarioEstaAutenticado). Caso uma rota protegida seja acessada sem uma sessão válida, o usuário é imediatamente redirecionado para a tela de login.
Credenciais Padrão de Teste:

    Usuário: admin

    Senha: 123

    💡 Rastreamento por Cookies: Ao efetuar o login, o sistema gera um cookie seguro (dataUltimoAcesso) com expiração automática para 30 dias, exibindo a data e hora do seu último acesso em todas as páginas visitadas.

⚙️ Funcionalidades Implementadas
---
* Autenticação Avançada: Login seguro com expiração de sessão inativa após 30 minutos.

* Validação de Formulários Server-Side: Os métodos POST de cadastro analisam se há campos vazios e renderizam alertas dinâmicos em Bootstrap na tela do usuário caso faltem dados.

* Mapeamento Relacional de Adoção: Na tela de Manifestação de Desejo, o sistema consome os vetores em memória para alimentar caixas de seleção dinâmicas (<select>), permitindo associar qualquer adotante       cadastrado a um animal específico.

* Listagens em Tempo Real: Exibição estruturada em formato de tabelas responsivas para todos os dados inseridos em tempo de execução.

🚀 Como Executar o Projeto
---
Pré-requisitos

Certifique-se de possuir o Node.js (versão 18 ou superior recomendada) instalado em seu computador.
1. Instalar as Dependências

Abra o terminal na pasta raiz do projeto e instale os pacotes listados no package.json:

    npm install

2. Iniciar o Servidor

Execute o comando padrão para subir a aplicação:

    node index.js

3. Acessar o Sistema

Abra o seu navegador web e digite o endereço local configurado:
Plaintext

    http://localhost:3000

📄 Licença
---

Este projeto é distribuído sob a licença ISC.
