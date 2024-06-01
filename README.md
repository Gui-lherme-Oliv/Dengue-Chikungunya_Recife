<div align="justify">

# Criação de dashboard com dados de casos notificados de Dengue e Chikungunya no município de Recife durante os anos de 2020 e 2021

A Secretaria de Saúde do Recife disponibiliza o registro dos casos de Dengue, Zica e Chikungunya com registros nas unidades de saúde, públicas ou particulares ([link](http://dados.recife.pe.gov.br/dataset/casos-de-dengue-zika-e-chikungunya)). Esse dados são compostos por planilhas em formato CSV e metadados em formato JSON com informações detalhadas sobre as planilhas. Foram utilizados alguns desses dados, que foram baixados, analisados, tratados e utilizados na criação do dashboard utilizando Power BI. 

## 1. Dados utilizados
- Casos confirmados de Chikungunya em 2020 ('chikon2020_recife.csv')
- Casos confirmados de Chikungunya em 2021 ('chikon2021_recife.csv')
- Casos de Dengue 2020 ('dengon2020_recife.csv')
- Casos de Dengue 2021 ('dengon2021_recife.csv')
- Tabela de Bairros ('tabela-de-bairros.csv')
- Tabela Distrito ('tabela-distrito.csv')

## 2. Transformação dos dados com Python
2.1. Os arquivos CSV referentes aos casos de Dengue e Chikungunya foram lidos e transformados em DataFrames.
2.2. Foi adicionado o atributo 'doenca' para sinalizar qual doença está sendo tratada nos dados.
2.3. Foram selecionados apenas alguns atributos de cada planilha considerados relevantes para essa na análise, incluindo o atributo adicionado anteriormente.
2.4. Todos os arquivos foram concatenados em um único DataFrame.
2.4. Foi realizada uma análise inicial para identificar valores ausentes ou nulos e valores duplicados, além de uma análise estatística para entender o comportamento dos atributos.
2.5. O resultado do arquivo concatenado foi exportado em formato CSV, denominado 'planilha_chikon-dengon_concat'.


</div>
