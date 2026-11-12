# Alimentos São Bento S.A. | Data & Business Intelligence

> **Projeto acadêmico de Engenharia de Dados e Business Intelligence**  
> Transformando dados operacionais em inteligência para a tomada de decisão.

<p align="center">
  <img src="https://img.shields.io/badge/Status-Em%20desenvolvimento-orange" />
  <img src="https://img.shields.io/badge/Azure-SQL%20%7C%20ADLS%20%7C%20Databricks-0078D4" />
  <img src="https://img.shields.io/badge/Analytics-Power%20BI-F2C811" />
</p>

## Sobre o projeto

A **Alimentos São Bento S.A.** é uma empresa fictícia do setor de laticínios, criada para o desenvolvimento de uma solução de Engenharia de Dados e Business Intelligence.

O projeto parte de um cenário hipotético: uma indústria alimentícia tradicional, com décadas de mercado, enfrenta uma crise financeira e operacional. Apesar de possuir uma estrutura significativa de produção e distribuição, a empresa apresenta dificuldades para controlar seus estoques, administrar seus custos, otimizar a produção e garantir a eficiência logística.

A diretoria reconhece que a operação está apresentando resultados insatisfatórios, mas não possui informações integradas suficientes para compreender a dimensão dos problemas e identificar suas possíveis causas.

Nesse contexto, nossa equipe assume o papel de uma consultoria de dados, contratada para investigar a situação da empresa e desenvolver uma solução que transforme seus registros operacionais em informações relevantes para a tomada de decisão.

**O desafio é ir além da construção de dashboards: queremos descobrir onde a empresa está perdendo dinheiro, quais processos precisam de atenção e quais decisões podem contribuir para sua recuperação.**

## Inspiração: o caso Shefa

A ideia surgiu a partir de notícias sobre a trajetória da **Agropecuária Tuiuti S.A., responsável pela marca de laticínios Shefa**.

Em julho de 2023, a Justiça de São Paulo decretou a falência da empresa, que estava em recuperação judicial desde 2017 e havia informado dívidas de aproximadamente R$ 222,5 milhões.

O caso chamou nossa atenção e despertou uma reflexão:

*O que pode acontecer dentro de uma indústria de laticínios para que sua operação e sua situação financeira cheguem a um cenário tão crítico? Quais indicadores poderiam ajudar a gestão a identificar problemas e tomar decisões antes que a situação se agrave?*

A partir dessa reflexão, desenvolvemos a proposta da Alimentos São Bento S.A. e formulamos hipóteses sobre problemas que podem comprometer uma indústria desse segmento, como desperdícios, vencimento de produtos, custos elevados, ineficiência produtiva, problemas logísticos e dificuldades de gestão.

É importante esclarecer que **não estamos afirmando que esses problemas foram as causas da situação da Shefa**. O caso real é a inspiração para o contexto do projeto e para as perguntas que pretendemos investigar. A empresa, os dados, os problemas operacionais e os cenários apresentados neste trabalho são inteiramente fictícios.

Também é importante contextualizar que o decreto de falência de julho de 2023 foi posteriormente suspenso por decisão do STJ, em outubro de 2023, permitindo a retomada dos efeitos da recuperação judicial.

### Referências sobre o caso

- [UOL — Justiça de São Paulo decreta a falência da Shefa (14/07/2023)](https://economia.uol.com.br/noticias/redacao/2023/07/14/justica-sp-decreta-falencia-shefa.htm)
- [Exame — Dona da marca de laticínios Shefa tem falência decretada (17/07/2023)](https://exame.com/negocios/dona-da-marca-de-laticinios-chefa-tem-falencia-decretada-empresa-continua-funcionando/)
- [TMA Brasil — Empresa responsável pela marca Shefa reverte falência e retoma recuperação judicial (08/11/2023)](https://www.tmabrasil.org/blog-tma-brasil/noticias-em-geral/empresa-responsavel-pela-marca-de-laticinios-shefa-reverte)

---

## A empresa: Alimentos São Bento S.A.

A Alimentos São Bento é uma indústria brasileira fictícia, fundada em 1989, com sede em Minas Gerais.

Sua atividade principal é a fabricação e distribuição de produtos derivados do leite, atendendo supermercados, distribuidores e estabelecimentos varejistas.

### Perfil da empresa

| Característica | Cenário simulado |
|---|---|
| Segmento | Indústria alimentícia / Laticínios |
| Fundação | 1989 |
| Sede | Minas Gerais, Brasil |
| Unidades fabris | 3 |
| Centros de distribuição | 2 |
| Linhas de produção | 12 |
| Funcionários | Aproximadamente 180 |
| Produtos acabados | Aproximadamente 35 |
| Clientes | Supermercados, distribuidores e varejistas |
| Histórico analisado | Novembro/2023 a Outubro/2026 |

### Portfólio de produtos

A empresa trabalha com diferentes categorias de produtos:

- **Leites:** integral, desnatado e semidesnatado.
- **Queijos:** muçarela, prato e minas.
- **Iogurtes:** naturais e saborizados.
- **Derivados:** manteiga e requeijão.
- **Bebidas:** bebidas lácteas.

A operação também depende da aquisição e utilização de matérias-primas e insumos, como leite cru, fermentos, coalho e embalagens.

### O cenário de crise

Apesar de sua estrutura e experiência no mercado, a empresa atravessa um momento delicado.

Os principais problemas identificados como hipóteses para investigação são:

| Área | Problemas simulados |
|---|---|
| Estoque | Produtos vencidos, excesso de mercadorias e desperdícios. |
| Produção | Consumo excessivo de matérias-primas e baixa eficiência. |
| Logística | Atrasos nas entregas, problemas com rotas e custos elevados. |
| Recursos Humanos | Distribuição desigual de atividades, ociosidade e excesso de horas extras. |
| Comercial | Produtos com margens reduzidas, cancelamentos e concentração de vendas. |
| Financeiro | Despesas elevadas, inadimplência e dificuldades de controle da rentabilidade. |

Esses problemas não serão tratados como conclusões antecipadas. Nossa intenção é construir uma base de dados capaz de investigá-los e identificar quais situações realmente representam riscos para a empresa dentro do cenário simulado.

---

## Objetivos do projeto

### Objetivo geral

Desenvolver uma solução de Engenharia de Dados e Business Intelligence capaz de transformar dados transacionais de uma indústria de laticínios em informações analíticas, proporcionando uma visão integrada da operação e apoiando a tomada de decisão.

### Objetivos específicos

1. Construir uma base de dados transacional que represente os processos de uma indústria alimentícia.
2. Desenvolver uma arquitetura de dados baseada no conceito de Lakehouse.
3. Implementar processos de ingestão, limpeza, padronização e transformação de dados.
4. Organizar os dados nas camadas Bronze, Silver e Gold.
5. Construir um modelo dimensional utilizando a abordagem Star Schema.
6. Desenvolver indicadores e medidas analíticas utilizando DAX.
7. Criar dashboards interativos para acompanhamento dos principais processos empresariais.
8. Identificar gargalos, desperdícios, tendências e oportunidades de melhoria.
9. Apresentar insights e recomendações fundamentados nos dados.

## Perguntas que queremos responder

O trabalho será orientado por perguntas de negócio, conectando os dados às necessidades da diretoria.

| Área | Pergunta estratégica |
|---|---|
| Financeiro | Onde a empresa está perdendo dinheiro? |
| Estoque | Quanto dinheiro é perdido com produtos vencidos e descartados? |
| Produção | A empresa está produzindo de maneira eficiente? |
| Logística | Quais fatores estão relacionados aos atrasos nas entregas? |
| Recursos Humanos | A força de trabalho está bem distribuída entre os setores? |
| Comercial | Quais produtos e clientes realmente contribuem para a rentabilidade? |
| Gestão integrada | Quais problemas devem ser priorizados para melhorar os resultados? |

Um dos principais objetivos será cruzar informações de diferentes áreas.

Por exemplo, investigar se o excesso de estoque está relacionado a falhas no planejamento de produção, se atrasos de fornecedores comprometem a fabricação ou se determinados custos logísticos reduzem significativamente a margem de determinados produtos.

---

## Arquitetura tecnológica

A solução será desenvolvida utilizando uma arquitetura **Lakehouse**, combinando armazenamento em Data Lake, processamento distribuído e modelagem analítica.

### Visão geral

```text
                 ORIGEM TRANSACIONAL
                   Azure SQL Database
                           |
                           v
              AZURE DATA LAKE STORAGE
                     (ADLS Gen2)
                           |
             +-------------+-------------+
             |             |             |
             v             v             v
          BRONZE         SILVER         GOLD
        Dados brutos  Dados tratados  Dados analíticos
             |             |             |
             +-------------+-------------+
                           |
                  AZURE DATABRICKS
                  SQL / PySpark
                   Delta Lake
                           |
                           v
                       POWER BI
                  Modelo semântico
                     Medidas DAX
                           |
                           v
                      DASHBOARDS
                Indicadores e insights
```

### Tecnologias utilizadas

| Tecnologia | Aplicação |
|---|---|
| Azure SQL Database | Banco de dados transacional e origem dos registros operacionais. |
| Azure Data Lake Storage Gen2 | Armazenamento dos dados no Lakehouse. |
| Azure Databricks | Ingestão, processamento e transformação dos dados. |
| Delta Lake | Armazenamento das tabelas nas camadas do Lakehouse. |
| SQL | Consultas, estruturação e transformações de dados. |
| Python / PySpark | Geração de dados sintéticos e processamento de dados. |
| Power Query (M) | Preparação e transformação de dados para o Power BI, quando aplicável. |
| Power BI | Modelagem analítica, indicadores, visualizações e dashboards. |
| DAX | Construção de medidas e cálculos analíticos. |

### Arquitetura Medallion

Os dados serão organizados em três camadas:

**Bronze — Dados brutos**

Recebe os dados provenientes da origem transacional, preservando os registros e permitindo rastreabilidade e reprocessamento.

**Silver — Dados tratados**

Contém dados limpos, padronizados, validados e integrados, com aplicação das regras de negócio necessárias.

**Gold — Dados analíticos**

Disponibiliza conjuntos de dados preparados para análise, incluindo o modelo dimensional Star Schema e as estruturas utilizadas pelo Power BI.

---

## Modelagem de dados

A origem será construída no Azure SQL Database, representando os processos operacionais da Alimentos São Bento.

A modelagem transacional será organizada em domínios:

| Domínio | Principais entidades |
|---|---|
| Cadastro | Unidades, setores, funcionários, cargos, clientes, fornecedores e produtos. |
| Comercial | Pedidos de venda, itens de pedidos e histórico de status. |
| Suprimentos | Pedidos de compra, recebimentos e fornecedores. |
| Produção | Receitas, ordens de produção, consumo de insumos e perdas. |
| Estoque | Depósitos, lotes e movimentações. |
| Qualidade | Inspeções e registros de temperatura. |
| Logística | Rotas, entregas, transportadoras e ocorrências. |
| Recursos Humanos | Jornadas, atividades e apontamentos de horas. |
| Financeiro | Lançamentos, contas a pagar e contas a receber. |

Posteriormente, os dados serão transformados em um modelo dimensional.

A camada Gold deverá conter múltiplas tabelas fato, respeitando a granularidade de cada processo, e dimensões compartilhadas, como:

- Dimensão Data;
- Dimensão Produto;
- Dimensão Cliente;
- Dimensão Fornecedor;
- Dimensão Funcionário;
- Dimensão Unidade;
- Dimensão Setor;
- Dimensão Transportadora;
- Dimensão Rota.

A estrutura definitiva será estabelecida durante a etapa de modelagem dimensional.

---

## Geração de dados sintéticos

Como não utilizaremos dados internos de uma organização real, será construída uma base de dados fictícia.

A geração será realizada de maneira controlada, respeitando as regras de negócio, os relacionamentos entre entidades e a evolução temporal dos registros.

O objetivo é criar uma operação empresarial coerente, na qual seja possível investigar problemas e identificar relações entre diferentes processos.

### Cenários que serão simulados

- Lotes de produtos com diferentes datas de fabricação e validade.
- Produtos vencidos e descartados.
- Compras recebidas com atrasos e divergências.
- Consumo de matérias-primas acima do previsto.
- Diferenças entre produção planejada e realizada.
- Pedidos cancelados ou entregues parcialmente.
- Entregas atrasadas por diferentes motivos.
- Ocorrências de transporte e desvios de temperatura.
- Funcionários com diferentes distribuições de horas e atividades.
- Despesas operacionais, recebimentos em atraso e margens distintas.

Os dados serão gerados com dependências entre eventos, evitando registros aleatórios e desconectados.

### Volume estimado

A simulação terá três anos de histórico operacional, entre novembro de 2023 e outubro de 2026.

| Entidade | Volume estimado |
|---|---:|
| Funcionários | 180 |
| Produtos e insumos | 100 |
| Clientes | 300 |
| Fornecedores | 50 |
| Pedidos de venda | 35.000 |
| Itens de pedidos | 100.000 |
| Ordens de produção | 8.000 |
| Lotes | 12.000 |
| Movimentações de estoque | 80.000 |
| Entregas | 30.000 |
| Apontamentos de atividades | 100.000 |
| Lançamentos financeiros | 50.000 |

*Os volumes são estimativas iniciais e poderão ser ajustados durante o desenvolvimento.*

---

## Dashboards planejados

A solução analítica será dividida em painéis temáticos, permitindo que a diretoria investigue diferentes aspectos da operação.

### 1. Visão Executiva

Indicadores gerais da empresa, evolução da receita, custos, margem, perdas e desempenho operacional.

### 2. Comercial e Rentabilidade

Faturamento, volume vendido, ticket médio, margem por produto, clientes e desempenho comercial.

### 3. Estoque e Perdas

Giro de estoque, cobertura, vencimentos, descartes, perdas financeiras e rastreabilidade de lotes.

### 4. Produção e Eficiência

Volume produzido, capacidade produtiva, consumo de matérias-primas, desperdícios e eficiência das unidades.

### 5. Logística e Entregas

Pontualidade, atrasos, ocorrências, custos de transporte, rotas e desempenho das transportadoras.

### 6. Recursos Humanos e Produtividade

Horas trabalhadas, horas extras, distribuição de atividades e utilização da capacidade das equipes.

### 7. Financeiro

Receitas, despesas, custos, contas a pagar, contas a receber e evolução dos resultados financeiros.

Os painéis poderão ser ajustados conforme os requisitos identificados e os resultados obtidos durante a análise.

---

## Etapas de desenvolvimento

O projeto será conduzido em etapas:

| Etapa | Atividade |
|---|---|
| 01 | Levantamento de requisitos e definição das perguntas de negócio. |
| 02 | Modelagem do banco transacional e elaboração do diagrama ER. |
| 03 | Implementação do banco no Azure SQL Database. |
| 04 | Desenvolvimento dos scripts de geração de dados sintéticos. |
| 05 | Ingestão dos dados na camada Bronze. |
| 06 | Limpeza, padronização e integração na camada Silver. |
| 07 | Construção do Star Schema na camada Gold. |
| 08 | Desenvolvimento do modelo semântico e das medidas DAX. |
| 09 | Construção dos dashboards no Power BI. |
| 10 | Análise dos resultados, identificação de insights e apresentação das recomendações. |

---

## Estrutura do repositório

A organização inicial do projeto seguirá uma estrutura modular:

```text
alimentos-sao-bento-bi/
│
├── README.md
│
├── docs/
│   ├── requisitos/
│   ├── modelagem/
│   │   └── diagrama-er/
│   ├── arquitetura/
│   └── apresentacao/
│
├── sql/
│   ├── 01_database/
│   ├── 02_schemas/
│   ├── 03_tables/
│   ├── 04_constraints/
│   ├── 05_indexes/
│   └── 06_views/
│
├── data-generation/
│   ├── scripts/
│   └── config/
│
├── databricks/
│   ├── bronze/
│   ├── silver/
│   └── gold/
│
├── power-bi/
│   ├── dashboards/
│   ├── dax/
│   └── documentation/
│
└── .gitignore
```

Essa estrutura poderá evoluir conforme os componentes forem implementados.

---

## Resultados esperados

Ao final do projeto, esperamos entregar:

- Banco de dados transacional no Azure SQL Database.
- Base sintética representando três anos de operações.
- Arquitetura Lakehouse implementada no ADLS Gen2.
- Processos de ingestão e transformação no Azure Databricks.
- Camadas Bronze, Silver e Gold.
- Modelo dimensional Star Schema.
- Indicadores e medidas DAX.
- Dashboards interativos no Power BI.
- Diagnóstico dos principais problemas da empresa fictícia.
- Insights e recomendações fundamentados nos dados.

O objetivo não é apenas apresentar indicadores, mas demonstrar como diferentes fontes de informação podem ser integradas para revelar problemas que não seriam facilmente identificados por meio de análises isoladas.

---

## Considerações finais

A Alimentos São Bento S.A. é uma empresa inteiramente fictícia, criada para fins acadêmicos e de demonstração técnica.

A inspiração no caso Shefa surgiu da reflexão sobre os desafios enfrentados por empresas do setor de laticínios e sobre como uma gestão orientada por dados pode contribuir para identificar riscos, compreender a operação e apoiar decisões estratégicas.

**Nosso propósito é demonstrar como Engenharia de Dados e Business Intelligence podem transformar dados operacionais em conhecimento, contribuindo para uma gestão mais eficiente, sustentável e orientada por evidências.**

---

## Status do projeto

**Em desenvolvimento — Levantamento de requisitos e modelagem inicial.**

As tecnologias, os processos, os volumes e a arquitetura descritos neste documento representam o planejamento inicial e poderão ser refinados ao longo do desenvolvimento.

---

<p align="center">
  <strong>Alimentos São Bento S.A.</strong><br>
  Data Engineering & Business Intelligence
</p>