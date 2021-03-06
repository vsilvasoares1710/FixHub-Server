# FixHub - Servidor

Este reposítório contém o backend da aplicação FixHub

## Instalação

Para utilizar este projeto alguns pré-requisitos devem ser satisfeitos:

1. O Node.js versão 12.13.1 ou superior deve estar instalado em sua máquina;

2. Caso queira se conectar com um banco de dados MySQL local tenha o MySQL Server versão 8.18 ou superior instalado em sua máquina(Também recomendo que utilize alguma GUI para o MySQL como o MySQL Workbench ou phpMyAdmin);

3. Também provemos um arquivo .editorconfig já configurado, caso queira fazer uso do arquivo(algo que definitivamente recomendamos) instale a extensão EditorConfig em seu editor de texto preferido.

Satisfazendo os pré requisitos acima, baixe os arquivos do repositório clicando em no botão verde "clonar ou baixar" no canto superior direito da página ou por meio da linha de comando caso possua o GIT instalado:

```

git init
git clone https://github.com/vsilvasoares1710/FixHub-Server

```

Com os arqivos em sua máquina navegue até a pasta raíz do projeto e instale todas as dependências do projeto executando os seguintes comandos:

```javascript

npm install
npm install --save sequelize
npm install --save nodemon
npm install --save sucrase

```

A partir desse momento, na pasta raíz do projeto sera criada uma pasta chamada node_modules, que todas as dependências do projeto devidamente instaladas em sua máquina além de outras dependências provenientes do Node.js.

## Dependências Instaladas

* Axios: Facilita a realização de requisições HTTP(XmlHttpRequests);
* Bcrypt: Permite criptografar informações sensíveis(como senhas por exemplo), por meio da criação de hashes com um segredo;
* CORS: Garante que as APIs criadas com esse projeto possam ser acessadas por servidores diferentes do servidor de desenvolvimento;
* express: Framework que possibilita a criação de um servidor com diversos métodos utilizados para criar acessar e manipular endpoints na aplicação;
* JSON Web Token(também conhecido como JWT): Ferramenta de autenticação que gera tokens criptografados utilizados para controle de logins e autenticação de aplicações web em geral;
* mysql2: Pacote utilizado para a manipulação de bancos de dados MySQL, permite a realização de querys SQL;
* Nodemon: Dependência excenlente parao proceso de desenvolvimento que monitora diversos arquivos da aplicação, realizando reload automático do servidor uma vez que qualquer aruivo monitorado seja modificado;
* Sequelize: ORM utilizado para manipular bancos de dados relacionais, abstraindo a SQL, permitindo que o banco de dados possa ser manipulado por meio de puro JavaScript;
* Sucrase: Pacote que possibilita o desenvolvimento de aplicações com todas as características do ECMAScript 8, que possam ser executados pelo Node.js;
* YUP: Ferramenta para higienização de dados e validação de formulários.

## Estrutura do Projeto

    .
    ├── ..                      # Pasta raíz do projeto
    ├──node_modules             # Pasta de dependências do projeto
    │   └── ...                   # Pastas de cada dependência
    │
    ├──src                      # Pasta fonte do projeto
    │   ├──app                    # Pasta que contém o núcleo da aplicação
    │   │   ├──controllers          # Pasta dos controladores lógicos da aplicação
    │   │   ├──middlewares          # Pasta dos intermediadores da aplicação
    │   │   └──models               # Pasta dos modelos de dados da aplicação
    │   │
    │   ├──config                 # Pasta que amazena configurações do projeto, como segredo do token,
    │   │   │                     # credenciais de acesso ao banco de dados, etc...
    │   │   ├──db.js              # Arquivo que exporta credenciais de acesso ao banco de dados
    │   │   └──jwt.js               # Arquivo que exporta um objeto com as configurações do token JWT,
    │   │                             como segredo de criptografia e período de validade do token
    │   │
    │   ├──database               # Pasta contendo o núcleo do banco de dados a ser manipulado pelo Sequelize
    │   │   ├──migrations           # Pasta que contém todas as migrações(alterações na estrutura) no banco de dados
    │   │   └──index.js             # Arquivo que exporta classe com o banco de dados configurado, permitindo
    │   │                             trabalhar com o banco de dados como um objeto
    │   │
    │   ├──index.js               # Arquivo do ponto de entrada da aplicação, inicializa o servidor
    │   ├──routes.js              # Arquivo com as rotas da aplicação
    │   └──server.js              # Arquivo que exporta uma classe com o servidor da aplicação
    │
    ├──.editorconfig            # Arquivo utilizado pela extensão EditorConfig, garante homogeneidade textual
    │                             em todos os arquivos do projeto
    ├──.gitignore               # Arquivo que dispõe todos os arquivos a serem ignorados pelo repositório git
    ├──.sequelizerc             # Arquivo contendo as configurações necessárias para o sequelize acessar
    │                             o caminho de cada arquivo do projeto
    ├──package.json             # Arquivo que contém informações cruciais do projeto, como nome do projeto,
    │                             entry point da aplicação, versão do projeto, scripts a serem executados,
    │                             dependências a serem instaladas e etc...
    └──README.md                # Documentação do projeto
