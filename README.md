<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:1a0000,50:8b0000,100:cc0000&height=120&section=header&animation=fadeIn" alt="Faixa decorativa"/>

<h2>Alysson Caputti</h2>

<p>
  Data Engineer and Data Analyst · Curitiba, Brasil<br/>
  Construo pipelines, modelo dados e resolvo problemas de algoritmos nas horas vagas.
</p>

<p>
  <a href="https://www.linkedin.com/in/alyssoncaputti">
    <img src="https://img.shields.io/badge/LinkedIn-cc0000?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:alysson.farias@gpcorpbr.com">
    <img src="https://img.shields.io/badge/Email-a00000?style=flat&logo=gmail&logoColor=white" alt="Email"/>
  </a>
  <a href="https://leetcode.com/AlyssonCaputti">
    <img src="https://img.shields.io/badge/LeetCode-b30000?style=flat&logo=leetcode&logoColor=white" alt="LeetCode"/>
  </a>
</p>

<hr/>

<h3>Sobre mim</h3>

<p>
  Trabalho com engenharia e análise de dados — do dado cru até o dado pronto pra ser usado.<br/>
  Gosto de código limpo, sistemas observáveis e de entender <em>por que</em> algo quebra antes de sair corrigindo.<br/>
  Uso IA no meu fluxo de trabalho do dia a dia — não como muleta, mas como um pair programmer que nunca dorme.
</p>

<p><strong>Coisas que já coloquei em produção:</strong></p>
<ul>
  <li>Pipeline <strong>SAP B1 → MySQL DW → dbt Core → Power BI</strong> — zero exportação manual, dados em tempo real pra vendas, estoque e marketing.</li>
  <li>Agentes de IA com LLM APIs (Anthropic) pra modelagem SQL, automação de pipelines e validação de dados — IA como parte do fluxo, não enfeite.</li>
  <li>Debuguei um problema de parsing de datas no pandas que tava silenciosamente corrompendo dados em prod. Escrevi testes de regressão. Não voltou mais.</li>
  <li>dbt em produção: modelos modulares, testes de qualidade, linhagem rastreável.</li>
</ul>

<hr/>

<h3>Projetos</h3>

<table>
  <tr>
    <td><a href="https://github.com/AlyssonCaputti/sap-mysql-etl"><strong>sap-mysql-etl</strong></a></td>
    <td>
      ETL que sobrevive a uma origem que muda de formato sem avisar. Contrato de schema,
      4 estratégias de carga idempotentes e o post-mortem de um bug que descartava 33% da base
      com um aviso no log.<br/>
      <sub>Python · MySQL · pytest</sub>
    </td>
  </tr>
  <tr>
    <td><a href="https://github.com/AlyssonCaputti/frota-brasil-pipeline"><strong>frota-brasil-pipeline</strong></a></td>
    <td>
      Frota circulante do SENATRAN (22M linhas) cruzada com specs da FIPE. Camadas
      <code>staging → intermediate → marts</code>, testes de granularidade e CI que roda
      o pipeline inteiro na amostra.<br/>
      <sub>Python · PostgreSQL · dbt · Airflow · Docker</sub>
    </td>
  </tr>
  <tr>
    <td><a href="https://github.com/AlyssonCaputti/etl-cotacao-moedas"><strong>etl-cotacao-moedas</strong></a></td>
    <td>
      ETL enxuto de cotações via API pública. <code>ON CONFLICT</code> pra não duplicar em
      reexecução e <code>NUMERIC</code> pra valor monetário.<br/>
      <sub>Python · PostgreSQL · Docker</sub>
    </td>
  </tr>
  <tr>
    <td><a href="https://github.com/AlyssonCaputti/analise-ecommerce-sql"><strong>analise-ecommerce-sql</strong></a></td>
    <td>
      Análise de negócio em SQL sobre e-commerce: faturamento, produtos, clientes — com um
      arquivo de checagem de qualidade de dados à parte.<br/>
      <sub>SQL · SQLite · Python</sub>
    </td>
  </tr>
  <tr>
    <td><a href="https://github.com/AlyssonCaputti/sql-agent"><strong>sql-agent</strong></a></td>
    <td>
      Agente texto→SQL com a API da Anthropic: pergunta em português, query via tool use,
      execução somente leitura.<br/>
      <sub>Python · Anthropic API · SQLite</sub>
    </td>
  </tr>
</table>

<hr/>

<h3>Stack</h3>

<p><strong>Core</strong></p>
<p>
  <img src="https://img.shields.io/badge/Python-cc0000?style=flat&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/SQL-a00000?style=flat&logo=postgresql&logoColor=white" alt="SQL"/>
  <img src="https://img.shields.io/badge/dbt-b30000?style=flat&logo=dbt&logoColor=white" alt="dbt"/>
  <img src="https://img.shields.io/badge/ETL%20%2F%20ELT-cc0000?style=flat&logoColor=white" alt="ETL / ELT"/>
</p>

<p><strong>Dados & Infra</strong></p>
<p>
  <img src="https://img.shields.io/badge/PostgreSQL-cc0000?style=flat&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/MySQL-a00000?style=flat&logo=mysql&logoColor=white" alt="MySQL"/>
  <img src="https://img.shields.io/badge/Airflow-b30000?style=flat&logo=apacheairflow&logoColor=white" alt="Airflow"/>
  <img src="https://img.shields.io/badge/Docker-cc0000?style=flat&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/Power%20BI-a00000?style=flat&logo=powerbi&logoColor=white" alt="Power BI"/>
  <img src="https://img.shields.io/badge/Linux-b30000?style=flat&logo=linux&logoColor=white" alt="Linux"/>
  <img src="https://img.shields.io/badge/Git-cc0000?style=flat&logo=git&logoColor=white" alt="Git"/>
</p>

<p><strong>Engenharia com IA</strong></p>
<p>
  <img src="https://img.shields.io/badge/LLM%20APIs-cc0000?style=flat&logo=anthropic&logoColor=white" alt="LLM APIs"/>
  <img src="https://img.shields.io/badge/Anthropic-a00000?style=flat&logoColor=white" alt="Anthropic"/>
  <img src="https://img.shields.io/badge/Agentes%20de%20IA-b30000?style=flat&logoColor=white" alt="Agentes de IA"/>
  <img src="https://img.shields.io/badge/FastAPI-cc0000?style=flat&logo=fastapi&logoColor=white" alt="FastAPI"/>
</p>

<hr/>

<h3>Certificações</h3>

<p>
  <img src="https://img.shields.io/badge/Google%20Cloud%20Computing%20Foundations-cc0000?style=flat&logo=googlecloud&logoColor=white" alt="Google Cloud Computing Foundations"/>
  <img src="https://img.shields.io/badge/Data%2C%20ML%20%26%20AI%20no%20Google%20Cloud-a00000?style=flat&logo=googlecloud&logoColor=white" alt="Data, ML & AI no Google Cloud"/>
  <img src="https://img.shields.io/badge/Cloud%20Computing%20Fundamentals-b30000?style=flat&logo=googlecloud&logoColor=white" alt="Cloud Computing Fundamentals"/>
</p>

<hr/>

<h3>Programação Competitiva</h3>

<p>
  Resolvo problemas de algoritmos todo dia — LeetCode, Codeforces, campeonatos.<br/>
  Não é só hobby: pensar em O(n log n) vs O(n²) muda como você escreve qualquer código, não só o de competição.<br/>
  Tenho um repositório com as soluções comentadas — abordagem, complexidade e o raciocínio por trás de cada uma.
</p>

<p>
  <a href="https://leetcode.com/AlyssonCaputti" target="_blank">
    <img src="https://img.shields.io/badge/LeetCode-cc0000?style=flat&logo=leetcode&logoColor=white" alt="LeetCode"/>
  </a>
  <a href="https://codeforces.com/profile/AlyssonCaputti" target="_blank">
    <img src="https://img.shields.io/badge/Codeforces-a00000?style=flat&logo=codeforces&logoColor=white" alt="Codeforces"/>
  </a>
  <a href="https://github.com/AlyssonCaputti/Competitive-programming" target="_blank">
    <img src="https://img.shields.io/badge/Repositório%20de%20soluções-b30000?style=flat&logo=github&logoColor=white" alt="Repositório de soluções"/>
  </a>
</p>

<hr/>

<h3>Estudando agora</h3>

<p>
  <em>Designing Data-Intensive Applications</em> (Kleppmann) · Spark internals · System Design de dados ·
  GCP / BigQuery · LeetCode todo dia sem falta
</p>

<hr/>

<h3>No que estou trabalhando</h3>

<ul>
  <li><strong>Observabilidade de ETL</strong> — tabela de controle de execução e um painel que responde "o pipeline parou? quando? por quê?" sem abrir log.</li>
  <li><strong>Reescrita do ETL de produção</strong> — do script monolítico para camadas testáveis, com orquestração declarada.</li>
  <li><strong>Certificação DP-700</strong> (Fabric Data Engineer) e fundamentos de GCP / BigQuery.</li>
</ul>

<hr/>

<p align="center">
  <a href="https://www.linkedin.com/in/alyssoncaputti">
    <img src="https://img.shields.io/badge/LinkedIn-cc0000?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  &nbsp;
  <a href="mailto:alysson.farias@gpcorpbr.com">
    <img src="https://img.shields.io/badge/Email-a00000?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
  &nbsp;
  <a href="https://github.com/AlyssonCaputti?tab=repositories">
    <img src="https://img.shields.io/badge/Repositórios-b30000?style=for-the-badge&logo=github&logoColor=white" alt="Repositórios"/>
  </a>
</p>
