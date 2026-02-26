⚙️ Configuração inicial do ambiente de desenvolvimento no VS Code, com a criação da pasta .vscode e do arquivo settings.json para manter padrões locais de formatação e organização do editor.

🐍 Criação de um ambiente virtual Python local .venv, utilizado apenas para evitar avisos do editor e facilitar testes rápidos.
⚠️ Este não é o ambiente oficial do projeto, pois a execução final será feita via Docker.
📌 O diretório foi marcado como untracked para não ser enviado ao GitHub.

🚫 Criação do arquivo .gitignore na raiz do projeto, baseado em modelos da comunidade Python, garantindo que arquivos locais, ambientes virtuais e configurações pessoais não sejam versionados — mantendo o repositório limpo e focado apenas no código da aplicação.

🐳 Definição da estratégia principal de ambiente com Docker, permitindo que o projeto rode em um ambiente isolado, padronizado e independente do sistema operacional, além de facilitar deploy futuro e colaboração com outros desenvolvedores.

📁 Criação da estrutura da aplicação Django dentro da pasta djangoapp, preparando o projeto para execução futura dentro dos containers Docker.

▶️ Execução inicial do servidor com
> python djangoapp/manage.py runserver,
⛏ o que gera automaticamente o banco db.sqlite3.
🗑️ Esse banco pode ser removido, pois o projeto usará outro banco posteriormente via container.

📜 Criação do script commands.sh, responsável por automatizar comandos essenciais do Django dentro do ambiente do projeto:

> collectstatic para arquivos estáticos

> migrate para aplicar migrações do banco

> runserver para iniciar a aplicação

🔐 Organização das variáveis de ambiente dentro da pasta dotenv_files, contendo os arquivos .env usados para configurações sensíveis do projeto.

🧱 Configuração do arquivo docker-compose.yml, responsável por construir e orquestrar os containers da aplicação e seus serviços auxiliares.

📝 Criação da aplicação blog dentro do projeto Django.

⚙️ Adição do app 'blog' ao INSTALLED_APPS no arquivo settings.py.

🌐 Inclusão da rota do app no project/urls.py usando include('blog.urls').

📁 Criação do arquivo djangoapp/blog/urls.py para centralizar as rotas do app.

🗂️ Dentro do arquivo criado no passo anterior, foi definido app_name = 'blog' para organizar o namespace das rotas do aplicativo.

🚪 Ainda no mesmo arquivo de rotas do app, foi criada a rota inicial path('', index, name='index'), apontando para a view principal

Criado os Htmls parciais, _header.html, _footer.html e _pagination.html, dentro da pasta 'blog(APPNAME)/templates/blog/partials/_head.html'

Ajustado no base.html, para dar um 'include', nas 3 partes dentro do corpo dele

Criado um novo APP chamado 'site_setep', para ter as configurações especificas do Blog

⚙️ Adição do app 'site_setep' ao INSTALLED_APPS no arquivo settings.py.