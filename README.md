
> ## 💻Basic commands
>### criando venv (caso erro de 'ExecutionPolicy')

 ▶ python -m venv venv

 ▶ Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process

 ▶ .\venv\Scripts\activate



> ### Importante

Atualizar o PIP apos criar o venv

▶ pip install pip --upgrade

ou

▶ python.exe -m pip install --upgrade pip

> ### Instalando Django

▶ pip install django
 
▶ pip freeze (para verificar instalações no ambiente)

> ### criar o projeto e startar

▶ django-admin startproject project .
> ### iniciar server

▶ python djangoapp/manage.py runserver


