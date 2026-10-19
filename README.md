<h1 align="center">Rodrigo Kreusch</h1>
<h3 align="center">Analytics Engineer</h3>

<p align="center">
  ELT · dbt · Modelagem dimensional · Data Warehouse · Google Cloud · Power BI
</p>

---

## Sobre

Analytics Engineer na Genial Dash (BI as a Service). Projeto a camada entre a fonte e o dashboard: ingestão via API, armazenamento em Parquet, transformação e deduplicação em SQL e dbt no BigQuery, e modelos em esquema estrela prontos para consumo no Power BI.

**Foco técnico:** arquitetura medalhão · ELT · modelagem dimensional · performance analítica · pipelines containerizados.

---

## Arquitetura de referência

```mermaid
flowchart LR
    A[APIs REST<br/>Gclick · Omie · Acessórias<br/>Nibu · Movidesk] --> B[Python<br/>Cloud Run]
    B --> C[(GCS<br/>Parquet<br/>Bronze)]
    C --> D[(BigQuery + dbt<br/>Dedup e transformação<br/>Silver)]
    D --> E[(BigQuery + dbt<br/>Star schema<br/>Gold)]
    E --> F[Power BI]
    W[Cloud Workflows] -. orquestra .-> B
    W -. orquestra .-> D
```

| Camada | Tecnologia | Responsabilidade |
|---|---|---|
| **Ingestão** | Python, Docker, Cloud Run | Extração completa via API, escrita em Parquet |
| **Bronze** | Cloud Storage (Parquet) | Dado cru, formato colunar e barato |
| **Silver** | BigQuery, SQL, dbt | Deduplicação, tipagem e limpeza |
| **Gold** | BigQuery, dbt | Fatos e dimensões em esquema estrela |
| **Consumo** | Power BI (DAX) | Medidas e visualização sobre modelo já pronto |
| **Orquestração** | Cloud Workflows | Encadeamento e agendamento dos jobs |

---

## Decisões de engenharia

Escolhas que fiz e os trade-offs por trás delas:

- **Pipeline em Cloud Run em vez de consumir a API direto no Power BI.** Mais código para manter, mas o tempo de extração caiu 80% e as falhas de consistência acabaram. A regra de negócio sai do relatório e vai para uma camada versionada.
- **Parquet no GCS antes do BigQuery.** Um passo a mais na arquitetura, em troca de custo baixo de armazenamento, histórico reprocessável e desacoplamento entre extração e transformação.
- **ELT com transformação no BigQuery.** Usa o poder do warehouse e mantém a lógica em SQL, ao custo de pagar processamento a cada execução, o que pede atenção a particionamento e consultas incrementais.
- **dbt para a camada de transformação.** Traz versionamento, testes e documentação dos modelos, mas adiciona uma ferramenta para operar e exige disciplina de convenções no projeto.
- **Esquema estrela no consumo.** Modelo mais previsível e rápido no Power BI, com custo extra de modelagem antecipada.
- **Refresh incremental** para grandes volumes, em vez de recarga total.

---

## Stack

**Linguagens**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-F2C811?style=flat&logo=powerbi&logoColor=black)

**Google Cloud**
![BigQuery](https://img.shields.io/badge/BigQuery-669DF6?style=flat&logo=googlebigquery&logoColor=white)
![Cloud Run](https://img.shields.io/badge/Cloud_Run-4285F4?style=flat&logo=googlecloud&logoColor=white)
![Cloud Storage](https://img.shields.io/badge/Cloud_Storage-4285F4?style=flat&logo=googlecloud&logoColor=white)
![Workflows](https://img.shields.io/badge/Workflows-4285F4?style=flat&logo=googlecloud&logoColor=white)

**Transformação e modelagem**
![dbt](https://img.shields.io/badge/dbt-FF694B?style=flat&logo=dbt&logoColor=white)
![Parquet](https://img.shields.io/badge/Parquet-50ABF1?style=flat&logo=apache&logoColor=white)

**Bancos e BI**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Microsoft Fabric](https://img.shields.io/badge/Microsoft_Fabric-0078D4?style=flat&logo=microsoft&logoColor=white)

**Infra e automação**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Power Automate](https://img.shields.io/badge/Power_Automate-0066FF?style=flat&logo=powerautomate&logoColor=white)

---

## Entregas

- **Lakehouse completo** com extração total via API do Gclick, base técnica para o lançamento de um novo produto.
- **Redesenho de pipeline:** de consumo direto de API no Power BI para ELT containerizado, com redução de 80% no tempo de extração.
- **Integração de 5 sistemas** (Gclick, Acessórias, Omie, Nibu, Movidesk) na mesma arquitetura medalhão.
- **Produto de inteligência comercial** para varejo e indústria, hoje padrão do segmento.
- **Power BI de alta performance** com DAX avançado, Star Schema, views/CTEs e refresh incremental.
- **Governança no Power BI Service e Fabric:** Dataflows, Gateways e monitoramento de falhas.

---

## Projetos públicos

<!-- Fixe 3 a 6 repositórios. Sugestão: reproduza a arquitetura acima com uma API pública (API, Parquet, BigQuery, modelo estrela com dbt). -->

- **[nome-do-projeto]**: pipeline Python → GCS → BigQuery em arquitetura medalhão.
- **[nome-do-projeto]**: modelagem dimensional com dbt sobre dados públicos.

---

## Contato

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rodrigo-adriano-kreusch-239ab8213/)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:adrianokreuschrodrigo@gmail.com)
