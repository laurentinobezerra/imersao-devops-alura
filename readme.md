-----

# Imersão DevOps - Alura Google Cloud

Este projeto é uma **API desenvolvida com FastAPI** para gerenciar alunos, cursos e matrículas em uma instituição de ensino.

-----

## Pré-requisitos

Para colocar este projeto para rodar, você precisará ter o seguinte instalado em sua máquina:

  * **Python 3.10 ou superior:** [Baixe aqui](https://www.python.org/downloads/)
  * **Git:** [Baixe aqui](https://git-scm.com/downloads)
  * **Docker:** [Baixe aqui](https://www.docker.com/get-started/)

-----

## Passos para Subir o Projeto (Modo Tradicional)

Se você prefere subir o projeto sem o Docker inicialmente, siga estes passos:

1.  **Baixe o repositório:**
    [Clique aqui para fazer o download](https://github.com/laurentinobezerra/imersao-devops-alura/archive/refs/heads/main.zip)

2.  **Crie um ambiente virtual:**
    Abra seu terminal na pasta do projeto e execute:

    ```sh
    python3 -m venv ./venv
    ```

3.  **Ative o ambiente virtual:**

      * No Linux/Mac:
        ```sh
        source venv/bin/activate
        ```
      * No Windows (execute no PowerShell como administrador):
        ```sh
        Set-ExecutionPolicy RemoteSigned
        ```
        Depois, no terminal normal:
        ```sh
        venv\Scripts\activate
        ```

4.  **Instale as dependências:**

    ```sh
    pip install -r requirements.txt
    ```

5.  **Execute a aplicação:**

    ```sh
    uvicorn app:app --reload
    ```

6.  **Acesse a documentação interativa:**
    Abra seu navegador e acesse: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
    Aqui você pode testar todos os endpoints da API de forma interativa.

-----

## Passos para Subir o Projeto (Com Docker)

Para uma experiência mais padronizada e isolada, use o Docker\! Ele garante que seu ambiente de desenvolvimento seja idêntico ao ambiente de produção.

1.  **Certifique-se de ter o Docker instalado:** Se ainda não tem, [baixe-o aqui](https://www.docker.com/get-started/).

2.  **Baixe o repositório:** Se ainda não fez, [clique aqui para fazer o download](https://github.com/laurentinobezerra/imersao-devops-alura/archive/refs/heads/main.zip) e descompacte.

3.  **Navegue até a pasta do projeto:** Abra seu terminal e vá para o diretório raiz do projeto, onde você encontrará o `Dockerfile` e o `docker-compose.yml`.

4.  **Construa e execute os contêineres:**
    No terminal, execute o seguinte comando:

    ```sh
    docker-compose up
    ```


5.  **Acesse a documentação interativa:**
    Abra seu navegador e acesse: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
    A API estará rodando dentro do Docker, pronta para ser testada\!

6.  **Para parar os contêineres:**
    No terminal onde o `docker-compose up` está rodando, pressione `Ctrl+C`.
    Se quiser parar e remover os contêineres, redes e volumes criados, execute:

    ```sh
    docker-compose down
    ```

-----

## Estrutura do Projeto

  * `app.py`: O arquivo principal da aplicação FastAPI.
  * `models.py`: Define os modelos do banco de dados usando SQLAlchemy.
  * `schemas.py`: Contém os schemas de validação usando Pydantic.
  * `database.py`: Gerencia a configuração do banco de dados SQLite.
  * `routers/`: Diretório que organiza os arquivos de rotas (alunos, cursos, matrículas).
  * `requirements.txt`: Lista todas as dependências Python do projeto.
  * `Dockerfile`: Contém as instruções para construir a imagem Docker da aplicação.
  * `docker-compose.yml`: Define como o Docker Compose deve orquestrar e rodar a aplicação.

-----

### Observações Importantes

  * O banco de dados SQLite (`escola.db`) será **criado automaticamente** na primeira execução do projeto, seja de forma tradicional ou via Docker.
  * Para reiniciar o banco de dados (apagando todos os dados), basta **excluir o arquivo `escola.db`**. Quando o projeto for executado novamente, um novo arquivo vazio será criado.

-----