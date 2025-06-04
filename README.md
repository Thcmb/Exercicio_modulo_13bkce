passo a passo de como fazer e configurar o projeto 

Instalando o poetry e adcionando o phaty
1-passo
C:\Users\VENDASS\a_a_a\bookstore>
python –-version
resposta
Python 3.12.3

2-passo
C:\Users\VENDASS\a_a_a\bookstore>
curl -sSL https://install.python-poetry.org | python –

3-passo Passo 3: Adicionar o Poetry ao PATH
1.	Abrir Configurações do Windows:
•	Pressione Win + R, digite sysdm.cpl e pressione Enter.
2.	Acessar Variáveis de Ambiente:
•	Na aba Avançado, clique em Variáveis de Ambiente.
3.	Editar a variável PATH:
•	Na seção Variáveis do sistema, encontre a variável Path e clique em Editar.
•	Clique em Novo e adicione o caminho onde o Poetry foi instalado. Geralmente, para o seu usuário, o caminho seria:
C:\Users\VENDASS\AppData\Roaming\Python\Scripts

Para achar o caminho do poetry via cmd
where poetry
resposta
C:\Users\VENDASS\AppData\Roaming\Python\Scripts\poetry.exe
Repare que uma parte não entra para o phath que foi a parte \poetry.exe
4-Salvar e fechar:
•	Clique em OK para fechar todas as janelas.
Passo 4: Verificar a instalação do Poetry
Feche e reabra o Prompt de Comando para garantir que as alterações no PATH foram aplicadas. Em seguida, verifique a instalação do Poetry:
C:\Users\VENDASS\a_a_a\bookstore>
poetry –version
resposta
Poetry (version 1.8.3)

Fim primeiro passo
1.	Instalação do Black:
•	Black é um formatador de código Python.
•	Instale-o globalmente com os seguintes comandos:
C:\Users\VENDASS\a_a_a\bookstore>
pip3 install black
resposta ok
Successfully installed black-24.4.2 mypy-extensions-1.0.0 packaging-24.0 pathspec-0.12.1 platformdirs-4.2.2
Inicialize um novo projeto Django com o Poetry:
C:\Users\VENDASS\a_a_a\bookstore>
poetry init --no-interaction
resposta ok
Instalação do Django:
•	Adicione Django como uma dependência ao projeto:
C:\Users\VENDASS\a_a_a\bookstore>
poetry add Django
resposta ok
Creating virtualenv bookstore-rqdEZk6x-py3.12 in C:\Users\VENDASS\AppData\Local\pypoetry\Cache\virtualenvs
Using version ^5.0.6 for django

Updating dependencies
Resolving dependencies... (0.9s)

Package operations: 4 installs, 0 updates, 0 removals

  - Installing asgiref (3.8.1)
  - Installing sqlparse (0.5.0)
  - Installing tzdata (2024.1)
  - Installing django (5.0.6)

Writing lock file

6-Criação do Projeto Django:
•	Crie um novo projeto Django chamado bookstore:
C:\Users\VENDASS\a_a_a\bookstore>
poetry run django-admin startproject bookstore .
resposta ok
Passo 5: Confirme a instalação
Para confirmar que tudo foi configurado corretamente, você pode executar o seguinte comando para ver as dependências instaladas e verificar o ambiente virtual:
C:\Users\VENDASS\a_a_a\bookstore>
poetry show
resposta ok
Passo 6: Ative o ambiente virtual
Se desejar ativar o ambiente virtual gerenciado pelo Poetry, use:
A testar o Código
poetry shell
Adicione pytest como uma dependência de desenvolvimento
C:\Users\VENDASS\a_a_a\bookstore>
poetry add pytest –dev
resposta ok
Se precisar adicionar mais dependências de desenvolvimento ou de produção, você pode usar o mesmo comando poetry add seguido do nome do pacote.
Aula 3: Instalando Django Rest Framework
1.	Instalação do Django Rest Framework:
•	Adicione DRF como uma dependência ao seu projeto:
C:\Users\VENDASS\a_a_a\bookstore>
poetry add djangorestframework
resposta ok
Using version ^3.15.1 for djangorestframework
Aula 4: Configurando Django Rest Framework
1.	Configurando o settings.py:
•	Abra o arquivo settings.py em bookstore/bookstore/settings.py e adicione 'rest_framework' ao INSTALLED_APPS:
2.	
3.	INSTALLED_APPS = [
4.	    ...
5.	    'rest_framework',
]
Como ficou após mudar o arquivo
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    'rest_framework',
]

Aula 6: Rodando Projetos em Django Rest Framework
1.	Criar aplicação Django:
•	Crie uma nova aplicação chamada api dentro do seu projeto:

C:\Users\VENDASS\a_a_a\bookstore>
poetry run python manage.py startapp api
resposta ok criou a pasta api dentro do projeto ok

migrações pendentes que precisam ser aplicadas antes que o projeto funcione corretamente.
C:\Users\VENDASS\a_a_a\bookstore>
poetry run python manage.py migrate
resposta ok para migrar tudo feito
Rodando o servidor Django:
•	Execute o servidor de desenvolvimento:

C:\Users\VENDASS\a_a_a\bookstore>
poetry run python manage.py runserver
resposta ok abre o Django comum do projeto padrão

exercício terminado
1.	Este comando lista todas as dependências, excluindo as dependências de desenvolvimento.
2.	Você pode redirecionar a saída para um arquivo de texto usando o operador >
C:\Users\VENDASS\a_a_a\bookstore>
poetry show --tree --no-dev > requirements.txt
cria o arquivo requirements.txt já com as dependências dentro dele
comando para criar o .gitgnore mais o requirements.txt e já instalar o código que ira ficar no projeto para ignorar o arquivo para não subir env  e o outro para iniciar o projeto ok
C:\Users\VENDASS\a_a_a\bookstore>
poetry show --tree --no-dev > requirements.txt && echo "__pypackages__/" >> .gitignore && echo ".venv/" >> .gitignore && echo "requirements.txt" >> .gitignore
Resposta ok tudo criado como pediu
Nome do meu git hub
git@github.com:JACKSON-96/Configurando-o-Django-Rest-Framework.git
git init
git add .
git commit -m "Initial commit"

git remote add origin git@github.com:JACKSON-96/Configurando-o-Django-Rest-Framework.git

git push -u origin master
