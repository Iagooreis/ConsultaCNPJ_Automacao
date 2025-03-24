# 🔍 Projeto de Busca de Dados de Empresas por CNPJ
Este projeto tem como objetivo buscar dados cadastrais de empresas a partir dos seus CNPJs utilizando a API pública da Receita Federal, processando as informações e armazenando-as em uma planilha Excel.

__🚀 Funcionalidades:__
---------------------------
O código realiza as seguintes etapas:

Leitura de CNPJs: O código lê uma lista de CNPJs de empresas a partir de uma planilha Excel (CNPJ.xlsx), especificamente da aba chamada "CNPJ".

Consulta à API: Para cada CNPJ listado, o código faz uma requisição à API pública da Receita Federal (via endpoint https://www.receitaws.com.br/v1/cnpj/{CNPJ}), que retorna dados detalhados sobre a empresa.

Tratamento dos Dados: Os dados obtidos da API são processados, sendo extraídas informações como:

- CNPJ

- Nome da empresa

- Telefone

- E-mail

- Endereço (logradouro, bairro, município, estado, CEP...)

- Atividade principal

✅Armazenamento em Excel: As informações extraídas são salvas em uma planilha Excel no formato .xlsx. Se a aba "Dados" já existir, os novos dados são adicionados à aba existente, mantendo as informações anteriores intactas.

__📂Estrutura do Repositório:__
-----
📄 buscarcnpj.py: O código principal que realiza todas as operações de consulta, processamento e salvamento dos dados.

📄 CNPJ.xlsx: Planilha Excel contendo uma lista de CNPJs. O arquivo precisa estar presente no mesmo diretório que o script.

📄 A planilha deve ter uma aba chamada "CNPJ" e uma coluna chamada "CNPJ" que contém os números de CNPJ a serem consultados.

__⚙️ Requisitos:__
--------
Este projeto foi desenvolvido com as seguintes dependências:

pandas, openpyxl, http.client, json

__🛠 Como Usar:__
------
1. Preparação do Arquivo Excel
Antes de rodar o código, você precisa garantir que o arquivo CNPJ.xlsx exista no mesmo diretório do script buscarcnpj.py. A planilha precisa ter uma aba chamada CNPJ e outra DADOS, Na aba CNPJ deve ter uma coluna chamada CNPJ contendo os CNPJs das empresas que você deseja consultar, os dados buscados serão salvos na aba DADOS. 

2. Instalando as Dependências
Para instalar as dependências necessárias, basta executar o comando abaixo, que vai instalar tudo o que está listado no arquivo requirements.txt:
pip install -r requirements.txt

4. Executando o Código
Após garantir que o arquivo CNPJ.xlsx esteja configurado corretamente e as dependências estejam instaladas, você pode executar o código com o seguinte comando no terminal:
python buscarcnpj.py

__📌 Observação:__
-----
A API utilizada possui limitação de requisições. O plano gratuito permite 3 buscas por minuto. 
