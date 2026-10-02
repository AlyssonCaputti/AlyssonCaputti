# Oi, eu sou o Alysson 👋

Engenheiro de Dados, em Curitiba

Hoje eu cuido da engenharia de dados ponta a ponta na empresa onde trabalho:
arquitetei o hub de dados do zero, levo o **SAP Business One** até as bases
analíticas que o comercial e o marketing usam, e sou a referência técnica da
squad, definindo a arquitetura, respondendo pelo merge e priorizando as demandas
com o negócio.

O que me interessa de verdade é dado que chega na hora certa e com o número
certo. É basicamente atrás disso que eu corro todo dia.

Algumas coisas que saíram disso:

- pipeline de faturamento **46% mais rápido** (140s para 76s)
- leitura das fontes SAP **3,9x mais rápida** e **47x menos memória**, com
  processamento incremental, Parquet particionado e PyArrow
- warehouse modelado em dbt (`staging → intermediate → marts`, marts em star
  schema, `dbt test` em todas as tabelas) e migrado para o **BigQuery**, hoje em
  produção com particionamento mensal e clustering dimensionados pelo custo por
  consulta
- **R$ 84 mil/ano** a menos, ao internalizar a entrega de uma consultoria
- **SLA de dado atualizado às 8h**, sustentado por pipelines idempotentes,
  monitoramento e alerta na falha

---

## Stack

| | |
|---|---|
| **Linguagens** | Python, SQL, PySpark |
| **Orquestração e transformação** | Apache Airflow, dbt Core |
| **Bancos e formatos** | BigQuery, PostgreSQL, MySQL, Parquet, PyArrow |
| **Cloud e infra** | GCP, Docker, GitHub Actions, Linux |
| **Também uso** | FastAPI, Power BI |

**Estudando agora:** PySpark, Terraform e arquiteturas distribuídas.

---

## Projetos

Três que valem a visita. A descrição de verdade está em cada repositório.

### [frota-brasil-pipeline](https://github.com/AlyssonCaputti/frota-brasil-pipeline)

Cruzei a frota circulante do SENATRAN com as specs da FIPE: 22M de linhas por
mês, 730M no histórico desde 2019, tudo de fonte aberta. A arquitetura é essa:

```mermaid
flowchart LR
  subgraph SRC["🌐 Source"]
    direction TB
    S1(["SENATRAN · dump CKAN"])
    S2(["FIPE · API pública"])
  end

  subgraph ING["⬇ Ingestion"]
    L["Python<br/>download + COPY em lote"]
  end

  subgraph STO["🗄 Storage"]
    RAW[("PostgreSQL<br/>schema raw")]
  end

  subgraph PRC["⚙ Processing · dbt"]
    direction TB
    STG["staging"]
    INT["intermediate"]
    MRT["marts"]
    STG --> INT --> MRT
  end

  subgraph CON["📊 Consumption"]
    Q["SQL · Power BI"]
  end

  S1 --> L
  S2 --> L
  L --> RAW --> STG
  MRT --> Q

  AF{{"Airflow · DAG mensal"}}
  AF -. orquestra .-> L
  AF -. orquestra .-> STG

  classDef src   fill:#FFF1EA,stroke:#E05A2B,stroke-width:1.5px,color:#2B2B2B
  classDef ing   fill:#FCDCCB,stroke:#C24020,stroke-width:1.5px,color:#2B2B2B
  classDef store fill:#2B2B2B,stroke:#9E3318,stroke-width:2px,color:#FFFFFF
  classDef proc  fill:#FDE8DE,stroke:#C24020,stroke-width:1.5px,color:#2B2B2B
  classDef out   fill:#EDEDED,stroke:#6B6B6B,stroke-width:1.5px,color:#2B2B2B
  classDef orch  fill:#FFFFFF,stroke:#9E3318,stroke-width:1.5px,stroke-dasharray:5 3,color:#9E3318

  class S1,S2 src
  class L ing
  class RAW store
  class STG,INT,MRT proc
  class Q out
  class AF orch

  style SRC fill:none,stroke:#D5D5D5,stroke-dasharray:3 3,color:#8A8A8A
  style ING fill:none,stroke:#D5D5D5,stroke-dasharray:3 3,color:#8A8A8A
  style STO fill:none,stroke:#D5D5D5,stroke-dasharray:3 3,color:#8A8A8A
  style PRC fill:none,stroke:#D5D5D5,stroke-dasharray:3 3,color:#8A8A8A
  style CON fill:none,stroke:#D5D5D5,stroke-dasharray:3 3,color:#8A8A8A
```

No repositório eu cobri `DAG mensal no Airflow` · `testes de granularidade e de
cobertura` · `backfill mês a mês sem estourar disco` · `CI que sobe Postgres e
roda o pipeline` · `limitações documentadas`.

### [sap-mysql-etl](https://github.com/AlyssonCaputti/sap-mysql-etl)

ETL que roda todo dia sobre uma origem que muda de formato sem avisar. Cobri
`contrato de schema` · `4 estratégias de carga idempotentes` · `reconciliação
transacional` · `falha alta, nunca silenciosa` · `suíte que roda em ~1s, sem
banco e sem rede`.

Tem uma história boa de bug lá dentro, que custou 33% da base e eu achei
investigando lentidão, não erro.

### [sql-agent](https://github.com/AlyssonCaputti/sql-agent)

Pergunta em português vira SQL via tool use da API da Anthropic, executa em modo
somente leitura e responde com base no resultado. Cobri `tool use` ·
`execução read-only` · `resposta ancorada no dado`.

Os outros ficam em
[todos os repositórios](https://github.com/AlyssonCaputti?tab=repositories),
incluindo o [cs-data-roadmap](https://github.com/AlyssonCaputti/cs-data-roadmap),
onde eu registro meu estudo.

---

**Bora conversar?**
[LinkedIn](https://www.linkedin.com/in/alyssoncaputti) ·
[alyssoncaputti@gmail.com](mailto:alyssoncaputti@gmail.com) ·
[LeetCode](https://leetcode.com/AlyssonCaputti)
