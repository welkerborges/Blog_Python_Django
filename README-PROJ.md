## ⚙️ Configuração Inicial do Projeto

Antes de iniciar o desenvolvimento da aplicação, foi realizada toda a configuração do ambiente para garantir organização, padronização e compatibilidade futura com Docker.

### 📁 1. Configuração do VS Code

O primeiro passo foi configurar o ambiente de desenvolvimento no VSCode.

Foi criada uma pasta chamada:

.vscode
Dentro dela, foi configurado o arquivo:
    settings.json


Esse arquivo contém configurações personalizadas do meu VS Code (formatação).

### 🐍 2. Criação do Ambiente Virtual (Venv)

Em seguida, foi criado um ambiente virtual Python:

.venv

Esse ambiente foi criado apenas para evitar erros de interpretação do VS Code (como alertas de interpretador Python não configurado).
#### ⚠️ Porém, este não será o ambiente principal do projeto.
O ambiente oficial será gerenciado via Docker, garantindo Independência do sistema operacional

📌 O diretório .venv foi configurado como untracked para o GitHub.

### 🚫 3. Configuração do .gitignore

Na raiz do projeto foi criado o arquivo:

.gitignore

Foi utilizado um modelo amplamente adotado na comunidade (baseado em projetos Python).
Foram adicionadas as seguintes entradas personalizadas:

.venv/

Isso garante que:
    Configurações locais do editor não sejam versionadas
    Ambientes virtuais locais não sejam enviados ao repositório
    Apenas o código relevante da aplicação seja versionado

### 🐳 4. Estratégia de Ambiente com Docker

Embora exista uma .venv local, o ambiente oficial do projeto será construído utilizando Docker.

Isso permite:

Criar um ambiente virtual isolado dentro do container

Garantir que qualquer pessoa consiga rodar o projeto

Facilitar deploy futuro

### 💻Apos criar o App (djangoapp)
Criado o App dentro de uma pasta chamada djangoapp
Para depois ser enviada ao Docket

Runserver
▶python djangoapp/manage.py runserver
Ira criar o db.sqlite3, pode apaga-lo, apaguei pois ira ser rodado em outro banco



### Script/commands.sh
Execulta o

▶python manage.py collectstatic

▶python manage.py migrate

▶python manage.py runserver


