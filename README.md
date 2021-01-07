<h1 align="center">
    Geração de Matrícula || Curso Alura
<h1 align="center">Django Rest Framework  
</h1>
<p align="center">
  <a href="#💻-tecnologias">Tecnologias</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#🔥-como-executar">Como Executar</a>&nbsp;&nbsp;&nbsp;

</p>

## 💻 Tecnologias 
-  [Python](https://www.python.org/)
-  [Django](https://djangoproject.com)
-  [Django-Rest-Framework](https://django-rest-framework.org/)

<hr />

## 🔥 Como Executar

### **Pré-requisitos**

  - É **necessário** possuir o **[Python](https://python.org/)** instalado no computador
  - É **necessário** possuir o **[Git](https://git-scm.com/)** instalado e configurado no computador
  - Também, é **preciso** ter um gerenciador de pacotes **[PIP](https://www.pypi.org/)**

#### Para executar o servidor da aplicação, abra o terminal do seu sistema operacional, navegue até a pasta do projeto, entre no diretório server e execute:

    pip install -r requirements.txt

#### Esse comando fará com que o python instale todas as dependências de seu projeto.

#### Para executar as migrations.

    python manage.py migrate

#### Para rodar o servidor digite:

    python manage.py runserver

Pronto!!! Agora seu sistema estará rodando na porta 8000 do seu computador.

#  Rotas

## A API utiliza de BASIC AUTH para se autenticar. Crie um super usuário através do comando:

    python manage.py createsuperuser

## Aluno

Para o método POST e GET, acesse a rota: 

    http://localhosts:8000/alunos

- o Body da requisição POST:

     - Body

            {  
              "nome": "Albert Einstein"  ,
              "rg": "M13131313",
              "cpf": "0000000000",
              "data_nascimento":  "14/01/1879"
            }

Para ver, alterar ou deletar um aluno específico, adicione o id à rota, assim;
        
        http://localhosts:8000/alunos/1


## Curso

Para o método POST e GET, acesse a rota: 

    http://localhosts:8000/cursos

- o Body da requisição POST:

     - Body

            {  
              "codigo_curso": "FIS001"  ,
              "descricao": "Curso de Física",
              "nivel": "B",
            }

Para declarar o nível, existe esta configuração por default, siga o código de cada nível na requisição.

    NIVEL = (
        ('B', 'Básico'),
        ('I', 'Intermediário'),
        ('A', 'Avançado')
    )


Para ver, alterar ou deletar um curso específico, adicione o id à rota, assim;
        
        http://localhosts:8000/cursos/1

## Matrículas

Para o método POST e GET, acesse a rota: 

    http://localhosts:8000/matriculas

- o Body da requisição POST:

     - Body

            {  
              "aluno": 1  ,
              "curso": 1,
              "periodo": "M",
            }

Para declarar o período, existe esta configuração por default, siga o código de cada período na requisição.

    PERIODO = (
        ('M', 'Matutino'),
        ('V', 'Vespertino'),
        ('N', 'Noturno')
    )

Para ver, alterar ou deletar uma matrícula específico=a, adicione o id à rota, assim;
        
        http://localhosts:8000/matriculas/1

## Matrículas por aluno

Para ver as matrículas específicas de um aluno, acesse:

    http://localhosts:8000/aluno/1/matriculas

- A resposta da requisição:

               {
                    "curso": "Curso Django Rest Framework",
                    "periodo": "Noturno"
                }

## Matrículas por curso

Para ver os alunos matriculados em um curso, acesse:

    http://localhosts:8000/curso/1/matriculas

- A resposta da requisição:
        
        [
            {
                "aluno_nome": "Albert Einstein"
            },
            {
                "aluno_nome": "Nikola Tesla"
            },

        ]