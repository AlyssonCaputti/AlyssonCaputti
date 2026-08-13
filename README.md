<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=26&duration=3200&pause=900&color=E05A2B&center=true&vCenter=true&width=700&height=45&lines=Alysson+Caputti;Data+Engineer+%2F+Data+Analyst;do+dado+cru+ao+dado+confi%C3%A1vel" alt="Alysson Caputti, Data Engineer / Data Analyst"/>

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
    'cargo':      'Data Engineer / Data Analyst',
    'stack':      ['Python', 'SQL', 'dbt', 'Airflow', 'Docker'],
    'em_prod':    'SAP B1 -> MySQL DW -> dbt -> Power BI',
    'obsessao':   'pipeline que falha alto, nunca em silêncio',
    'estudando':  ['DDIA (Kleppmann)', 'Spark internals', 'DP-700'],
}
>>> perfil.regra_numero_um()
'um pipeline que roda não é um pipeline que funciona'
```

## Oi, tudo bem?

Trabalho com engenharia e análise de dados, do dado cru até o dado pronto pra ser usado.
Gosto de código limpo, sistema observável e de entender *por que* algo quebra antes de sair corrigindo.

Uso IA no fluxo do dia a dia. Não como muleta: como um pair programmer que nunca dorme.

> [!NOTE]
> **O que eu já coloquei em produção**
>
> - Pipeline **SAP B1 → MySQL DW → dbt Core → Power BI**: zero exportação manual, dado fresco pra vendas, estoque e marketing.
> - Agentes de IA com LLM APIs (Anthropic) pra modelagem SQL, automação de pipeline e validação de dados.
> - Achei um parsing de datas no pandas que corrompia dado em silêncio. Corrigi, escrevi teste de regressão, não voltou mais.
> - dbt em produção: modelo modular, teste de qualidade, linhagem rastreável.

## Projetos

Cada um resolve um problema diferente. Abra o que te interessar:

<details open>
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
<img src="https://skillicons.dev/icons?i=python,postgres,mysql,sqlite,docker,linux,git,github,vscode&theme=dark" alt="Python, PostgreSQL, MySQL, SQLite, Docker, Linux, Git, GitHub, VS Code"/>
<br/>
<img src="https://img.shields.io/badge/dbt-E05A2B?style=flat-square&logo=dbt&logoColor=white" alt="dbt"/>
<img src="https://img.shields.io/badge/Airflow-C24020?style=flat-square&logo=apacheairflow&logoColor=white" alt="Airflow"/>
<img src="https://img.shields.io/badge/pandas-9E3318?style=flat-square&logo=pandas&logoColor=white" alt="pandas"/>
<img src="https://img.shields.io/badge/Power%20BI-E05A2B?style=flat-square&logo=powerbi&logoColor=white" alt="Power BI"/>
<img src="https://img.shields.io/badge/FastAPI-C24020?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
<img src="https://img.shields.io/badge/Anthropic%20API-9E3318?style=flat-square&logo=anthropic&logoColor=white" alt="Anthropic API"/>
</div>

## No que estou trabalhando

<details>
<summary><b>Observabilidade de ETL</b>: “o pipeline parou? quando? por quê?”</summary>

<br/>

Tabela de controle de execução (início, fim, linhas afetadas, status) e um painel que
responde essas três perguntas sem ninguém precisar abrir log. A pergunta que quero
nunca mais responder com “alguém reclamou que o dado tá velho”.

</details>

<details>
<summary><b>Reescrita do ETL de produção</b>: de script para pipeline</summary>

<br/>

Saindo do monolito para camadas testáveis com orquestração declarada. A régua é poder
provar que o dado chegou certo, não só que o processo terminou com exit 0.

</details>

<details>
<summary><b>Estudo contínuo</b></summary>

<br/>

*Designing Data-Intensive Applications* (Kleppmann) · Spark internals · System design de dados ·
Certificação **DP-700** (Fabric Data Engineer) · GCP / BigQuery · LeetCode todo dia

</details>

## Certificações

<img src="https://img.shields.io/badge/Google%20Cloud%20Computing%20Foundations-2B2B2B?style=flat-square&logo=googlecloud&logoColor=white" alt="Google Cloud Computing Foundations"/>
<img src="https://img.shields.io/badge/Data,%20ML%20%26%20AI%20no%20Google%20Cloud-2B2B2B?style=flat-square&logo=googlecloud&logoColor=white" alt="Data, ML & AI no Google Cloud"/>
<img src="https://img.shields.io/badge/Cloud%20Computing%20Fundamentals-2B2B2B?style=flat-square&logo=googlecloud&logoColor=white" alt="Cloud Computing Fundamentals"/>

---

<div align="center">

**Bora trocar ideia sobre dados?** Chama que eu respondo.

<a href="https://www.linkedin.com/in/alyssoncaputti"><img src="https://img.shields.io/badge/LinkedIn-E05A2B?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
<a href="mailto:alysson.farias@gpcorpbr.com"><img src="https://img.shields.io/badge/Email-C24020?style=for-the-badge&logo=maildotru&logoColor=white" alt="Email"/></a>
<a href="https://github.com/AlyssonCaputti?tab=repositories"><img src="https://img.shields.io/badge/Repos-2B2B2B?style=for-the-badge&logo=github&logoColor=white" alt="Repositórios"/></a>

<br/><br/>
<sub><code>$ exit 0</code>, mas só quando o dado realmente chegou</sub>

</div>
