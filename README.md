
## ⚙️ Configuração Inicial do Projeto

Antes de iniciar o desenvolvimento da aplicação, foi realizada toda a configuração do ambiente para garantir organização, padronização e compatibilidade futura com Docker.

### 📁 1. Configuração do VS Code

O primeiro passo foi configurar o ambiente de desenvolvimento no VSCode.

Foi criada uma pasta chamada:

.vscode
Dentro dela, foi configurado o arquivo:
    settings.json


Esse arquivo contém configurações personalizadas do meu VS Code (formatação).

#### 📌 Importante:
A pasta .vscode foi marcada como untracked no GitHub, pois contém apenas configurações locais do ambiente de desenvolvimento, não sendo necessária para outros desenvolvedores ou para o ambiente de produção.

### 🐍 2. Criação do Ambiente Virtual (Venv)

Em seguida, foi criado um ambiente virtual Python:

.venv

Esse ambiente foi criado apenas para evitar erros de interpretação do VS Code (como alertas de interpretador Python não configurado).
#### ⚠️ Porém, este não será o ambiente principal do projeto.
O ambiente oficial será gerenciado via Docker, garantindo Independência do sistema operacional

📌 Assim como a pasta .vscode, o diretório .venv também foi configurado como untracked no GitHub.

### 🚫 3. Configuração do .gitignore

Na raiz do projeto foi criado o arquivo:

.gitignore

Foi utilizado um modelo amplamente adotado na comunidade (baseado em projetos Python).
Foram adicionadas as seguintes entradas personalizadas:

.vscode/
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

### ✅ Resultado

Com essa estrutura inicial:

Ambiente organizado

Configurações locais isoladas

Versionamento limpo

Base pronta para integração com Docker

O projeto está preparado para evoluir com boas práticas desde o início 🚀


## Comandos importantes


#### criando Venv, caso erro de 'ExecutionPolicy' rode 
▶ python -m venv venv
▶ Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
▶ .\venv\Scripts\activate


##### Importante
Atualizar o PIP apos criar o venv

▶ pip install pip --upgrade
ou
▶ python.exe -m pip install --upgrade pip

##### Instalando Django

▶ pip install django
▶ pip freeze (para verificar instalações no ambiente)

##### criar o projeto e startar

▶ django-admin startproject project .

##### iniciar server
▶ python djangoapp/manage.py runserver
