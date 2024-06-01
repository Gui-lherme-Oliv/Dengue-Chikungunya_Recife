<div align="justify">

# Criação de dashboard com dados de casos notificados de Dengue e Chikungunya no município de Recife durante os anos de 2020 e 2021

A Secretaria de Saúde do Recife disponibiliza publicamente o registro dos casos de Dengue, Zica e Chikungunya com registros nas unidades de saúde, públicas ou particulares ([link](http://dados.recife.pe.gov.br/dataset/casos-de-dengue-zika-e-chikungunya)). Esse dados são compostos por planilhas em formato CSV e metadados em formato JSON contendo informações detalhadas sobre as planilhas. Foram utilizados alguns desses dados, que foram baixados, analisados, tratados e utilizados na criação do dashboard utilizando Power BI. 

**Informações sobre a Secretaria:** A Secretaria de Saúde do Recife é responsável pela elaboração e implantação de políticas, programas e projetos que visem promover, proteger e recuperar a saúde da população. Como gestora do Sistema Único de Saúde (SUS) na capital, também fica sob sua responsabilidade a articulação e o planejamento de ações desenvolvidas na rede de policlínicas, maternidades, unidades do Programa de Saúde da Família (PSF) e centros médicos espalhados em seis Distritos Sanitários. Sua estrutura organizacional é composta pelas Secretarias Executivas de Coordenação Geral, Gestão do Trabalho e Educação na Saúde, Atenção à Saúde, Vigilância à Saúde e Administração e Finanças, que têm o objetivo de formatar e executar as atividades preconizadas pelo SUS.

## 1. Dados utilizados
- Casos confirmados de Chikungunya em 2020 ('chikon2020_recife.csv')
- Casos confirmados de Chikungunya em 2021 ('chikon2021_recife.csv')
- Casos de Dengue 2020 ('dengon2020_recife.csv')
- Casos de Dengue 2021 ('dengon2021_recife.csv')
- Tabela de Bairros ('tabela-de-bairros.csv')
- Tabela Distrito ('tabela-distrito.csv')

## 2. Transformação dos dados com Python
**2.1.** Os arquivos CSV referentes aos casos de Dengue e Chikungunya foram lidos e transformados em DataFrames.  
**2.2.** Foi adicionado o atributo 'doenca' para sinalizar qual doença está sendo tratada nos dados.  
**2.3.** Foram selecionados apenas alguns atributos de cada planilha considerados relevantes para essa na análise, incluindo o atributo adicionado anteriormente.  
**2.4.** Todos os arquivos foram concatenados em um único DataFrame.  
**2.5.** Foi realizada uma análise inicial para identificar valores ausentes/nulos e valores duplicados, além de uma análise estatística para entender o comportamento dos atributos.  
**2.6.** O resultado do arquivo concatenado foi exportado em formato CSV, denominado 'planilha_chikon-dengon_concat'.

## 3. Importação no Power BI
**3.1.** Importado o arquivo consolidado com as doenças, juntamente com os arquivos CSV de bairro e distrito.  
**3.2.** Estabelecido os relacionamentos entre a tabela fato (ocorrências de doença) e as tabelas dimensão (bairro e distrito).

## 4. Tratamento de dados
**4.1.** Foi realizada uma correção dos dados que se encontravam com caracteres especiais ou com nome das observações errado.  
**4.2.** Feita a limpeza de dados para remover espaçamentos e caracteres indesejados.  
**4.3.** Realizada a conversão de tipos de dados.  
**4.4.** Criados diferentes tipos de colunas na tabela fato:
- Colunas para a conversão de dados numéricos em dados categóricos;
- Colunas para armazenar resultados de cálculos que serviram como novos atributos necessários para a análise.;
- Coluna 'periodo' para indicar se o período é seco ou chuvoso, considerando o mês da coluna 'dt_notificacao'. Mar-ago é o período chuvoso e set-fev é o período seco.

## Observações
**Obs. 1:** O atributo “tp_escolaridade” que representa a série e grau que a pessoa está frequentando ou frequentou considerando a última série concluída com aprovação ou grau de instrução do paciente por ocasião da notificação, foi o que apresentou a maior quantidade de valores nulos, quase 20% do valor total, porcentagem essa com grande discrepância em relação aos valores nulos encontrados em outros atributos. Utilizei esse atributo para a análise, pois se trata de um projeto pessoal, mas seria necessário entrar em contato com a gerência de negócios ou alguém responsável da Secretaria para saber se esse dado deveria ser usado em uma análise desse tipo.

**Obs. 2.:** O conhecimento de um profissional da área de saúde e de um profissional da área social é imprescindível na leitura dos indicadores e visuais presentes no dashboard, para poder compreender corretamente os resultados obtidos e elucidar suas causas e consequências.

Profissionais de saúde e da área social desempenham papéis distintos, porém igualmente cruciais, no enfrentamento das arboviroses. Os profissionais de saúde oferecem diagnóstico, tratamento e monitoramento epidemiológico das doenças, garantindo cuidados médicos especializados e intervenções clínicas precisas. Enquanto isso, os profissionais da área social focam nos determinantes sociais da saúde, promovendo engajamento comunitário, advocacia por políticas públicas e apoio psicossocial às comunidades afetadas. A contribuição independente de cada grupo é essencial: os profissionais de saúde garantem a eficácia dos tratamentos e a gestão clínica das arboviroses, enquanto os profissionais da área social abordam as raízes socioeconômicas da propagação das doenças, promovendo mudanças estruturais necessárias para a prevenção e controle a longo prazo. Juntos, esses profissionais formam uma equipe multidisciplinar capaz de enfrentar os desafios complexos das arboviroses, protegendo a saúde e o bem-estar das comunidades.

# Dashboard criado
![Projeto_SESAU-Recife-1](https://github.com/Gui-lherme-Oliv/Dengue-Chikungunya_Recife/assets/123426025/8ce4a305-56b0-4088-8b8b-4e7b14dde38b)


</div>
