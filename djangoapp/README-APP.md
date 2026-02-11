#### djangoapp/requeriments.txt
criado para colocar as dependecias que iremos usar para o container 🐳Docker

#### .dockerignore
Para ignorar arquivos e não serem enviado ao container 🐳Docker

#### dotenv_files/.env-example
Semelhante ao .env
Mas como exemplo de como pode subir o projeto em outro local

#### settings.py - Alterações para ler a informações do .env
##### settings.py / DEBUG
alterado o Debug para buscar as variaveis de ambiente
    import os
depois altere o DEBUG
    DEBUG = bool(int(os.getenv('DEBUG',0)))
Pegamos a variavel bool (1,0), e se não encontrado o aqruivo .env para carregar o DEBUG, ira carregar como False(0)

##### *settings.py / ALLOWED_HOSTS*
ALLOWED_HOSTS =  [
    h.strip() for h in os.getenv('ALLOWED_HOSTS', '').split(',')
    if h.strip() ]
ALLOWED_HOSTS é uma string, acima estamos tentando pegar ela da variavel de amnbiente
Garantingo que irão vir sem espaços extras(strip)

##### settings.py / SECRET_KEY
SECRET_KEY = os.getenv('SECRET_KEY','change-me')

##### settings.py / DATABASES
DATABASES = {
    'default': {
        'ENGINE': os.getenv('DB_ENGINE', 'change-me'),
        'NAME': os.getenv('POSTGRES_DB', 'change-me'),
        'USER': os.getenv('POSTGRES_USER', 'change-me'),
        'PASSWORD': os.getenv('POSTGRES_PASSWORD', 'change-me'),
        'HOST': os.getenv('POSTGRES_HOST', 'change-me'),
        'PORT': os.getenv('POSTGRES_PORT', 'change-me'),
    }
}