Este projeto demonstra como usar o LlamaIndex com Pandas para criar uma interface de consulta em linguagem natural para dados tabulares. Ele permite que você faça perguntas sobre seus dados em português simples e obtenha respostas precisas baseadas em operações do pandas.

## Visão Geral

O projeto utiliza:

- LlamaIndex para processamento de linguagem natural
- Pandas para manipulação de dados
- Ollama para executar LLMs localmente
- Um conjunto de dados de vendas de exemplo (`vendas.csv`)

## Pré-requisitos

- Python 3.8+ (recomendado 3.13.2)
- Ollama instalado localmente ([Obter Ollama](https://ollama.com/))
- Git

## Configuração Passo a Passo

### 1. Clone o repositório

```bash
git clone <url-do-repositório>
cd qa_with_pandas
```

### 2. Crie um ambiente virtual

```bash
python -m venv .venv
```

Ative o ambiente:

- No macOS/Linux:
  ```bash
  source .venv/bin/activate
  ```
- No Windows:
  ```bash
  .venv\Scripts\activate
  ```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Configure o Ollama

1. Instale o Ollama seguindo as instruções em [ollama.com](https://ollama.com/)
2. Inicie o serviço Ollama
3. Faça o download do modelo necessário:
   ```bash
   ollama pull llama3.2:1b
   ```

### 5. Verifique se o Ollama está funcionando

Você pode testar se o Ollama está funcionando corretamente usando os exemplos em ollama_api_examples.md:

```bash
curl http://localhost:11434/api/chat -d '{
"model": "llama3.2:1b",
"messages": [
{ "role": "user", "content": "why is the sky blue?" }
]
}'
```

### 6. Execute o Jupyter Notebook

Inicie o Jupyter:

```bash
jupyter notebook
```

Abra o arquivo 01_pandas_query.ipynb no seu navegador e execute as células para ver as seguintes demonstrações:

- Carregamento dos dados de vendas do arquivo vendas.csv
- Configuração do motor de consulta LlamaIndex com Ollama
- Execução de consultas em linguagem natural contra o DataFrame do pandas

## Exemplos de Consultas

O notebook demonstra como consultar seus dados com perguntas em linguagem natural como:

- "Qual é a forma de pagamento mais utilizada pelos clientes?"

Você pode modificar as consultas para explorar suas próprias perguntas sobre os dados.

## Estrutura do Projeto

- 01_pandas_query.ipynb - Notebook Jupyter principal com código de exemplo
- vendas.csv - Dados de vendas de exemplo
- requirements.txt - Dependências Python
- ollama_api_examples.md - Exemplos de chamadas da API Ollama

## Solução de Problemas

- Certifique-se de que o Ollama esteja rodando na porta 11434 (padrão)
- Se encontrar timeouts, tente aumentar o parâmetro `request_timeout` na inicialização do Ollama
- Verifique se você tem o modelo correto baixado (`llama3.2:1b`)
