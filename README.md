<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=26&duration=3200&pause=900&color=E05A2B&center=true&vCenter=true&width=700&height=45&lines=Alysson+Caputti;Data+Engineer;do+dado+cru+ao+dado+confi%C3%A1vel" alt="Alysson Caputti, Data Engineer"/>

<p>
  <a href="https://www.linkedin.com/in/alyssoncaputti"><img src="https://img.shields.io/badge/LinkedIn-E05A2B?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:alyssoncaputti@gmail.com"><img src="https://img.shields.io/badge/Email-C24020?style=flat-square&logo=maildotru&logoColor=white" alt="Email"/></a>
  <a href="https://leetcode.com/AlyssonCaputti"><img src="https://img.shields.io/badge/LeetCode-9E3318?style=flat-square&logo=leetcode&logoColor=white" alt="LeetCode"/></a>
  <img src="https://img.shields.io/badge/Curitiba,%20BR-2B2B2B?style=flat-square&logo=googlemaps&logoColor=white" alt="Curitiba, Brasil"/>
</p>

</div>

```python
>>> from alysson import perfil
>>> perfil.resumo()
{
    'cargo':     'Data Engineer @ GP Corp BR',
    'stack':     ['Python', 'SQL', 'PySpark', 'Airflow', 'dbt', 'GCP'],
    'todo_dia':  'um pouco de LeetCode, um pouco de dado tratado',
    'porque':    'porque eu gosto mesmo é disso',
}
```

## Oi, tudo bem?

Sou o Alysson. Engenheiro de dados que estuda todo dia porque programar é a parte boa do meu dia, não uma obrigação.

Hoje construo pipelines na GP Corp BR, do SAP até o dado pronto pra alguém usar. Fora do trabalho, treino algoritmo no LeetCode e Codeforces, e monto meu próprio roadmap de estudo pra virar um engenheiro cada vez melhor.

Dá uma olhada no que eu venho construindo:

## Projetos

Cada um resolve um problema diferente. Abra o que te interessar:

<details>
<summary><b>🔧 sap-mysql-etl</b>: ETL que sobrevive a uma origem instável</summary>

<br/>

Todo dia ele lê exportação de ERP, trata e carrega num MySQL que alimenta dashboard e forecast.
O problema interessante não é volume, é que **a origem muda de formato sem avisar**: encoding, separador, nome de coluna, formato numérico.

O que tem dentro:

| | |
|---|---|
| **Contrato de schema** | declara o que espera da origem e aborta com mensagem útil quando quebra |
| **4 estratégias de carga** | `replace` · `truncate` · `date_range` · `upsert` (todas seguras pra rodar duas vezes) |
| **Falha alta, nunca silenciosa** | 3 correções de bug que passavam batido no log e no exit code |
| **Testável sem infra** | a suíte roda em ~1s, sem banco e sem rede |

A história favorita do repo: o detector de separador fazia `split(",")` cru, então
todo CSV **bem-formado** com vírgula dentro de aspas parecia quebrado, e o
reconstrutor heurístico **descartava 33% da base** com um aviso no log.
Achei investigando lentidão, não erro.

`Python` `MySQL` `pandas` `pytest`

</details>

<details>
<summary><b>🚗 frota-brasil-pipeline</b>: 22M linhas de frota nacional cruzadas com FIPE</summary>

<br/>

Frota circulante do SENATRAN × specs técnicas da FIPE, respondendo por marca/modelo/ano
quantos carros existem na rua e qual motor/combustível/potência eles têm.

```
SENATRAN (CKAN) ──┐
                  ├─> raw ─┬─> stg_frota ─┐
FIPE API ─────────┘        └─> stg_fipe ──┼─> marts
```

- Camadas `staging → intermediate → marts` no dbt, com de-para de marca como seed
- Teste de **granularidade** (não só `not_null`): a combinação marca+modelo+ano tem que ser única
- CI que sobe Postgres, roda o pipeline na amostra e valida com `dbt test`
- 93,1% de cobertura contra o total oficial de veículos leves, e o gap está documentado

`Python` `PostgreSQL` `dbt` `Airflow` `Docker`

</details>

<details>
<summary><b>💱 etl-cotacao-moedas</b>: ETL enxuto, feito certo</summary>

<br/>

Cotação de moeda de API pública → tratamento → Postgres em Docker. Pequeno de propósito,
mas com as decisões que importam: `ON CONFLICT` pra não duplicar em reexecução e
`NUMERIC` pra valor monetário (nunca `FLOAT`: erro de arredondamento em dinheiro não perdoa).

`Python` `PostgreSQL` `Docker`

</details>

<details>
<summary><b>📊 analise-ecommerce-sql</b>: análise de negócio em SQL puro</summary>

<br/>

Faturamento, produto, cliente e cohort sobre um banco de e-commerce, com um arquivo
de checagem de qualidade de dados separado, porque conferir a base antes de tirar
conclusão dela deveria ser padrão.

`SQL` `SQLite` `Python`

</details>

<details>
<summary><b>🤖 sql-agent</b>: pergunta em português, resposta em dado</summary>

<br/>

Agente texto→SQL com a API da Anthropic: a pergunta vira query via tool use, executa
em modo somente leitura e responde com base no resultado. Sem alucinar número.

`Python` `Anthropic API` `SQLite`

</details>

<details>
<summary><b>🧩 Competitive-programming</b>: algoritmo todo dia</summary>

<br/>

Soluções comentadas com abordagem, complexidade e o raciocínio atrás de cada uma.
Pensar em O(n log n) vs O(n²) muda como você escreve qualquer código, não só o de competição.

<a href="https://leetcode.com/AlyssonCaputti"><img src="https://img.shields.io/badge/LeetCode-9E3318?style=flat-square&logo=leetcode&logoColor=white" alt="LeetCode"/></a>
<a href="https://codeforces.com/profile/AlyssonCaputti"><img src="https://img.shields.io/badge/Codeforces-2B2B2B?style=flat-square&logo=codeforces&logoColor=white" alt="Codeforces"/></a>

</details>

## Ferramentas do dia a dia

<div align="center">
<img src="https://skillicons.dev/icons?i=python,postgres,mysql,sqlite,docker,linux,git,github,vscode,gcp&theme=dark" alt="Python, PostgreSQL, MySQL, SQLite, Docker, Linux, Git, GitHub, VS Code, GCP"/>
<br/>
<img src="https://img.shields.io/badge/dbt-E05A2B?style=flat-square&logo=dbt&logoColor=white" alt="dbt"/>
<img src="https://img.shields.io/badge/Airflow-C24020?style=flat-square&logo=apacheairflow&logoColor=white" alt="Airflow"/>
<img src="https://img.shields.io/badge/PySpark-9E3318?style=flat-square&logo=apachespark&logoColor=white" alt="PySpark"/>
<img src="https://img.shields.io/badge/pandas-9E3318?style=flat-square&logo=pandas&logoColor=white" alt="pandas"/>
<img src="https://img.shields.io/badge/Power%20BI-E05A2B?style=flat-square&logo=powerbi&logoColor=white" alt="Power BI"/>
<img src="https://img.shields.io/badge/FastAPI-C24020?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
<img src="https://img.shields.io/badge/Anthropic%20API-9E3318?style=flat-square&logo=anthropic&logoColor=white" alt="Anthropic API"/>
</div>

## Sempre estudando

Curioso por natureza. A lista de hoje: **GCP / BigQuery**, internals do **Spark**, arquitetura
distribuída, *Designing Data-Intensive Applications* (Kleppmann) e um problema novo por dia
no LeetCode. O `cs-data-roadmap` aqui do GitHub é onde eu registro tudo isso.

## Certificações

<img src="https://img.shields.io/badge/Google%20Cloud%20Computing%20Foundations-2B2B2B?style=flat-square&logo=googlecloud&logoColor=white" alt="Google Cloud Computing Foundations"/>
<img src="https://img.shields.io/badge/Data,%20ML%20%26%20AI%20no%20Google%20Cloud-2B2B2B?style=flat-square&logo=googlecloud&logoColor=white" alt="Data, ML & AI no Google Cloud"/>
<img src="https://img.shields.io/badge/Cloud%20Computing%20Fundamentals-2B2B2B?style=flat-square&logo=googlecloud&logoColor=white" alt="Cloud Computing Fundamentals"/>
<img src="https://img.shields.io/badge/Microsoft%20Certified-DP--700%20Fabric%20Data%20Engineer-2B2B2B?style=flat-square&logo=microsoftazure&logoColor=white" alt="Microsoft Certified: Fabric Data Engineer Associate (DP-700)"/>

---

<div align="center">

**Bora trocar ideia sobre dados?** Chama que eu respondo.

<a href="https://www.linkedin.com/in/alyssoncaputti"><img src="https://img.shields.io/badge/LinkedIn-E05A2B?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
<a href="mailto:alysson.farias@gpcorpbr.com"><img src="https://img.shields.io/badge/Email-C24020?style=for-the-badge&logo=maildotru&logoColor=white" alt="Email"/></a>
<a href="https://github.com/AlyssonCaputti?tab=repositories"><img src="https://img.shields.io/badge/Repos-2B2B2B?style=for-the-badge&logo=github&logoColor=white" alt="Repositórios"/></a>

</div>
