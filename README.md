# Alimentos São Bento S.A. — Engenharia de Dados e Business Intelligence

## 1. Sobre o projeto

O projeto **Alimentos São Bento S.A.** simula um cenário de consultoria de dados contratada pela diretoria de uma empresa familiar brasileira do setor de laticínios.

A empresa fictícia foi fundada em 1989, possui sede em Minas Gerais e opera com uma única fábrica e um fornecedor principal.

Nos últimos anos, a organização passou a enfrentar dificuldades financeiras e operacionais, como desperdício de matéria-prima, produtos vencidos, atrasos nas entregas, custos elevados, problemas de abastecimento e redução da rentabilidade.

Diante desse cenário, uma equipe de consultoria foi contratada para investigar os dados da operação, identificar padrões, levantar possíveis causas dos problemas e apresentar recomendações que apoiem a tomada de decisão.

O projeto utiliza dados sintéticos para representar três anos de operação, de novembro de 2023 a outubro de 2026.

> A empresa e os acontecimentos apresentados são fictícios. O cenário foi inspirado em desafios observados no setor de laticínios, sem representar ou atribuir esses problemas a uma empresa real.

## 2. Objetivos

O objetivo principal é construir uma solução de Engenharia de Dados e Business Intelligence capaz de transformar dados operacionais em informações relevantes para a gestão.

Entre as perguntas que a consultoria pretende responder estão:

- Quais produtos apresentam maior volume de vendas e quais possuem margens negativas?
- O crescimento do faturamento está acompanhado de crescimento da lucratividade?
- Quais insumos apresentam maior consumo e possíveis problemas de abastecimento?
- Existem diferenças relevantes entre a produção planejada e a realizada?
- Quais produtos e lotes apresentam maior risco de vencimento ou desperdício?
- Quais fatores estão associados aos atrasos nas entregas?
- Existem padrões de cancelamento, atendimento parcial ou atraso nos pedidos?
- Quais processos apresentam oportunidades de redução de custos?

As análises buscarão identificar relações e causas prováveis, distinguindo evidências observadas de hipóteses que precisam de investigação adicional.

## 3. Arquitetura tecnológica

A solução utiliza serviços do ecossistema Microsoft Azure e uma arquitetura de dados organizada em camadas.

| Tecnologia | Responsabilidade |
|---|---|
| Azure SQL Database | Banco de dados relacional e origem dos dados operacionais |
| Azure Data Lake Storage Gen2 | Armazenamento dos dados no Lakehouse |
| Azure Databricks | Ingestão, processamento e transformação dos dados |
| Delta Lake | Armazenamento transacional nas camadas do Lakehouse |
| Power BI | Modelagem analítica, indicadores, dashboards e relatórios |

### Arquitetura Medallion

A organização dos dados seguirá três camadas:

**Bronze — Dados brutos**

Armazena os dados extraídos da origem, preservando sua estrutura original e permitindo rastreabilidade.

**Silver — Dados tratados**

Contém dados padronizados, limpos, integrados e submetidos a regras de qualidade e validação.

**Gold — Dados analíticos**

Contém estruturas preparadas para análise, incluindo modelos dimensionais e tabelas organizadas para consumo pelo Power BI.

O modelo analítico seguirá o conceito de **Star Schema**, com tabelas fato e dimensão adequadas às necessidades dos indicadores.

## 4. Banco de dados operacional

O banco de dados `bd-sao-bento-laticineos` foi criado no Azure SQL Database.

A modelagem relacional inicial possui sete tabelas no schema `dbo`, contemplando cadastros, pedidos, produção, estoque e entregas.

### Estrutura das tabelas

| Tabela | Descrição |
|---|---|
| `Produto` | Cadastro de produtos acabados e insumos, com categorias, unidades de medida e informações de validade e armazenamento. |
| `Parceiro` | Cadastro unificado de clientes, fornecedor e transportadoras, diferenciados pelo tipo de parceiro. |
| `Pedido` | Registro de pedidos de compra e venda, incluindo datas, status e parceiro relacionado. |
| `ItemPedido` | Detalhamento dos produtos, quantidades solicitadas e atendidas, valores e custos de referência. |
| `OrdemProducao` | Registro das ordens de produção, com quantidades planejadas e realizadas, datas e custos. |
| `MovimentacaoEstoque` | Histórico de entradas, saídas, consumo, perdas e ajustes de estoque, incluindo informações de lote e validade. |
| `Entrega` | Registro das entregas vinculadas aos itens dos pedidos de venda, com transportadora, motorista, veículo, datas e frete. |

### Decisões de modelagem

- Utilização de um cadastro unificado de parceiros.
- Pedidos de compra e venda representados na mesma tabela.
- Controle de estoque por movimentações, sem armazenar saldo diretamente.
- Identificação simplificada de lotes nas movimentações.
- Relacionamento entre entregas e itens dos pedidos.
- Utilização de chaves primárias, estrangeiras, restrições e validações de integridade.

## 5. Dados sintéticos

A base foi construída para representar uma operação empresarial durante o período de 01/11/2023 a 31/10/2026.

Os dados possuem variações temporais, diferentes situações operacionais e inconsistências intencionais que poderão ser investigadas nas etapas analíticas.

### Cadastros

| Entidade | Registros |
|---|---:|
| Produtos | 15 |
| Parceiros | 23 |
| Clientes | 20 |
| Fornecedor | 1 |
| Transportadoras | 2 |

Os produtos estão divididos entre produtos acabados e insumos utilizados no processo produtivo.

### Pedidos e itens

| Entidade | Registros |
|---|---:|
| Pedidos de venda | 720 |
| Pedidos de compra | 36 |
| Total de pedidos | 756 |
| Itens de pedidos | 2.268 |

Os pedidos possuem diferentes status, valores, quantidades solicitadas e quantidades atendidas.

Alguns produtos apresentam custos de referência superiores aos seus preços de venda, permitindo investigar situações de margem negativa.

### Ordens de produção

Foram geradas 360 ordens de produção, distribuídas ao longo dos 36 meses simulados.

Os registros contemplam:

- Quantidades planejadas e produzidas.
- Datas previstas e realizadas.
- Diferentes status de produção.
- Custos totais reais.
- Variações entre produção planejada e realizada.

### Movimentações de estoque

Até o momento, foram geradas 1.741 movimentações:

| Tipo de movimentação | Registros |
|---|---:|
| `EntradaCompra` | 99 |
| `ConsumoProducao` | 1.305 |
| `EntradaProducao` | 337 |
| **Total** | **1.741** |

As movimentações representam o recebimento de insumos, o consumo de matérias-primas na produção e a entrada de produtos acabados no estoque.

A consulta inicial de saldos identificou quantidades negativas em alguns insumos. Essas inconsistências foram preservadas como pontos de investigação, podendo indicar problemas de abastecimento, planejamento ou dimensionamento dos dados.

## 6. Investigações e cenários analíticos

A base foi estruturada para permitir diferentes linhas de investigação.

### Comercial e financeiro
- Evolução do faturamento e da rentabilidade.
- Margem por produto.
- Produtos com margem negativa.
- Pedidos cancelados e parcialmente atendidos.
- Relação entre volume vendido e resultado financeiro.

### Produção
- Diferença entre quantidade planejada e produzida.
- Eficiência das ordens de produção.
- Custos de produção por produto.
- Consumo de insumos por unidade produzida.

### Estoque e abastecimento
- Saldo de estoque por produto.
- Consumo e recebimento de matérias-primas.
- Produtos próximos do vencimento.
- Perdas e desperdícios.
- Possíveis rupturas de estoque.

### Logística
- Cumprimento dos prazos de entrega.
- Atrasos por transportadora, motorista e região.
- Custos de frete.
- Quantidades entregues e pendências de atendimento.

Os indicadores e conclusões serão construídos conforme os dados disponíveis e as regras de negócio estabelecidas, evitando atribuir causalidade sem evidências suficientes.

## 7. Etapas de desenvolvimento

| Etapa | Atividade | Situação |
|---|---|---|
| 1 | Definição do cenário empresarial e requisitos | Concluída |
| 2 | Modelagem do banco de dados relacional | Concluída |
| 3 | Criação do Azure SQL Database | Concluída |
| 4 | Criação das sete tabelas e restrições | Concluída |
| 5 | Geração dos cadastros sintéticos | Concluída |
| 6 | Geração de pedidos e itens | Concluída |
| 7 | Geração das ordens de produção | Concluída |
| 8 | Geração das movimentações de estoque | Concluída |
| 9 | Geração e validação das entregas | Pendente |
| 10 | Integração com Azure Data Lake | Pendente |
| 11 | Implementação das camadas Bronze, Silver e Gold | Pendente |
| 12 | Modelagem dimensional | Pendente |
| 13 | Desenvolvimento dos dashboards no Power BI | Pendente |
| 14 | Análise dos resultados e recomendações | Pendente |

## 8. Resultados esperados

Ao final do projeto, espera-se entregar:

- Banco de dados operacional estruturado no Azure SQL.
- Pipeline de ingestão e transformação de dados.
- Lakehouse organizado pela arquitetura Medallion.
- Modelo dimensional preparado para análises.
- Dashboards interativos no Power BI.
- Indicadores de desempenho operacional e financeiro.
- Diagnóstico dos principais problemas simulados.
- Recomendações orientadas por dados para apoiar decisões gerenciais.

**Projeto:** Alimentos São Bento S.A. — Engenharia de Dados e Business Intelligence  
**Período dos dados:** Novembro de 2023 a Outubro de 2026  
**Banco de dados:** Azure SQL Database  
**Arquitetura analítica:** Lakehouse + Medallion Architecture  
**Ferramentas principais:** Azure, Azure Databricks, Delta Lake e Power BI