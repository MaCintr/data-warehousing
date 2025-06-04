# Resumo de Enterprise Analytics and Data Warehousing

## 1. Introdução a Data Warehousing
- **Definição**: Um Data Warehouse (DW) é um repositório de dados orientado a assuntos, integrado, não volátil e com séries temporais, projetado para suportar a tomada de decisão.
- **Características**:
  - **Orientado a assuntos**: Organizado por temas como vendas, clientes, etc.
  - **Integrado**: Dados de diversas fontes são consolidados em um esquema unificado.
  - **Não volátil**: Dados são carregados e acessados para leitura, sem modificações frequentes.
  - **Séries temporais**: Mantém histórico de dados para análise de tendências.

## 2. Arquitetura de Data Warehouse
- **Arquitetura de Fluxo de Dados**:
  - **Stage**: Repositório interno para preparação e transformação de dados.
  - **NDS (Normalized Data Store)**: Repositório interno com dados normalizados para integração.
  - **ODS (Operational Data Store)**: Repositório híbrido com dados operacionais atualizados.
  - **DDS (Dimensional Data Store)**: Repositório user-facing com formato dimensional para consultas analíticas.
- **Arquitetura de Sistemas**: Configuração física de servidores, rede, software e storage.

## 3. Modelagem Dimensional
- **Tabelas Fato**: Armazenam medições numéricas do negócio (ex.: quantidade vendida, valor total).
  - **Grão**: Define o nível de detalhe das medições (ex.: item por transação).
  - **Fatos aditivos**: Podem ser somados em qualquer dimensão (ex.: vendas totais).
  - **Fatos não-aditivos**: Não podem ser somados (ex.: preço unitário).
- **Tabelas Dimensão**: Contêm atributos descritivos (ex.: produto, loja, tempo).
  - **Dimensões degeneradas**: Sem atributos descritivos, usadas para agrupamento (ex.: número da transação).
  - **Slowly Changing Dimensions (SCD)**: Técnicas para gerenciar mudanças em atributos dimensionais:
    - **Tipo 1**: Sobrescreve o valor antigo.
    - **Tipo 2**: Cria uma nova linha com o novo valor.
    - **Tipo 3**: Adiciona uma coluna para o valor antigo.

## 4. Processo de Modelagem Dimensional
1. **Selecionar o processo de negócio**: Identificar a atividade a ser modelada (ex.: vendas no POS).
2. **Definir o grão**: Especificar o nível de detalhe (ex.: item por transação).
3. **Escolher as dimensões**: Identificar como os dados serão descritos (ex.: produto, loja, tempo).
4. **Identificar os fatos**: Determinar o que será medido (ex.: quantidade vendida, valor total).

## 5. Técnicas Avançadas
- **Snowflaking**: Normalização de tabelas dimensão para reduzir redundância, porém pode impactar desempenho.
- **Tabelas Fato sem Fatos**: Usadas para registrar relacionamentos sem medições (ex.: produtos em promoção não vendidos).
- **Surrogate Keys**: Chaves artificiais para isolamento de mudanças operacionais e melhor desempenho.

## 6. Granularidade
- **Alta granularidade**: Menor detalhamento, ideal para sumarizações rápidas.
- **Baixa granularidade**: Maior detalhamento, oferece flexibilidade para análises profundas.

## 7. Volumetria de Dados
- **Cálculo de volumetria**: Estimativa do espaço necessário para armazenar dados no DW.
  - **Carga inicial**: Volume de dados inseridos no início do projeto.
  - **Carga periódica**: Volume de dados adicionados em intervalos regulares (ex.: mensal).

## 8. Tendências em Data Warehousing
- **Dados desestruturados**: Incorporação de documentos, imagens, áudio e vídeo.
- **SOA (Service-Oriented Architecture)**: Componentes do DW como serviços independentes.
- **DW em tempo real**: Atualizações contínuas para refletir transações operacionais imediatamente.
- **Data Science**: Uso de algoritmos como K-means e regressão para transformar dados em insights.

## 9. Comparativo entre Sistemas Transacionais e Dimensionais
| **Característica**       | **Sistemas Transacionais**       | **Sistemas Dimensionais**       |
|--------------------------|----------------------------------|----------------------------------|
| **Objetivo**             | Operações cotidianas             | Análise de negócios              |
| **Uso**                  | CRUD (Insert, Update, Delete)    | Consultas complexas              |
| **Volume de dados**      | MB – GB                          | GB – TB                          |
| **Histórico**            | 60-90 dias                       | Vários anos                      |
| **Atualização**          | Contínua                         | Periódica (snapshots)            |

## 10. Referências
- Kimball, R., & Ross, M. (2002). *The Data Warehouse Toolkit*. John Wiley & Sons.
- Machado, F. N. R. (2004). *Tecnologia e Projeto de Data Warehouse*. Editora Érica.

Este resumo abrange os conceitos fundamentais e técnicas avançadas abordadas nos materiais, proporcionando uma visão clara e estruturada de Enterprise Analytics and Data Warehousing.
