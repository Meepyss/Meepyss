<h1 align="center">Rodrigo Adriano Kreusch</h1>
<h3 align="center">Analytics Engineer · BI & Data Engineering</h3>

<p align="center">
  Pipelines ELT, modelagem dimensional e BI no Google Cloud.<br>
  Engenharia de dados com olhar de quem já trabalhou na contabilidade.
</p>

---

## 👋 Sobre mim

Sou Analytics Engineer na **Genial Dash**, empresa de *BI as a Service* para escritórios de contabilidade. Projeto e implemento arquiteturas de ingestão e modelagem dimensional, do dado bruto na API até o dashboard no Power BI.

Antes de entrar em dados, passei mais de 4 anos na rotina fiscal e contábil (apuração de ICMS, TTD, obrigações acessórias, fechamento de IRPJ/CSLL). Foi lá que comecei a automatizar processos com Python, e isso me dá um diferencial: entendo o negócio do cliente que está do outro lado do dashboard.

**Foco atual:** arquitetura medalhão, ELT no GCP, modelagem em esquema estrela e performance analítica.

---

## Stack

**Linguagens:**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-F2C811?style=flat&logo=powerbi&logoColor=black)

**Google Cloud:**
![BigQuery](https://img.shields.io/badge/BigQuery-669DF6?style=flat&logo=googlebigquery&logoColor=white)
![Cloud Run](https://img.shields.io/badge/Cloud_Run-4285F4?style=flat&logo=googlecloud&logoColor=white)
![Cloud Storage](https://img.shields.io/badge/Cloud_Storage-4285F4?style=flat&logo=googlecloud&logoColor=white)
![Workflows](https://img.shields.io/badge/Workflows-4285F4?style=flat&logo=googlecloud&logoColor=white)

**Dados e BI:**
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Microsoft Fabric](https://img.shields.io/badge/Microsoft_Fabric-0078D4?style=flat&logo=microsoft&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=flat&logo=dbt&logoColor=white)

**Automação, infra e design:**
![Power Automate](https://img.shields.io/badge/Power_Automate-0066FF?style=flat&logo=powerautomate&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=flat&logo=figma&logoColor=white)

---

## Arquitetura que eu construo

Padrão medalhão em ELT dentro do GCP:

```mermaid
flowchart LR
    A[APIs dos sistemas<br/>Gclick · Omie · Movidesk...] --> B[Python em<br/>Cloud Run]
    B --> C[(Cloud Storage<br/>Parquet · Bronze)]
    C --> D[(BigQuery<br/>Dedup e transformação<br/>Silver)]
    D --> E[(BigQuery<br/>Esquema estrela<br/>Gold)]
    E --> F[Power BI]
```

---

## Resultados em destaque

- **Lakehouse do zero** com extração completa via API do Gclick, viabilizando a comercialização de um novo produto estratégico na empresa.
- **-80% no tempo de extração** ao substituir o consumo direto de APIs no Power BI por pipelines containerizados no Cloud Run, eliminando também falhas de consistência.
- **Integrações com vários sistemas** (Gclick, Acessórias, Omie, Nibu, Movidesk) dentro de uma mesma arquitetura reaproveitável.
- **Novo produto de inteligência comercial** para varejo e indústria, incorporado como produto padrão do segmento.
- **Dashboards de alta performance** com DAX avançado, Star Schema e refresh incremental para grandes volumes (EVNE).
- **Prototipação rápida no Figma** para validar layout e funcionalidade com o cliente antes do desenvolvimento.

---

## Trajetória

| Período | Onde | Papel |
|---|---|---|
| 12/2025 → hoje | **Genial Dash** | Analytics Engineer · BI & Data Engineering |
| 06/2025 → 11/2025 | **EVNE Tecnologia** | Analista de BI |
| 2021 → 2024 | Escritórios de contabilidade | Auxiliar Fiscal/Contábil (automação em Python e Golang) |

Bacharel em Ciências Contábeis · Unidavi
Modelagem de Dados Essencial · Python Data Structures · EF SET English C1 Advanced (61/100)

---

## Projetos públicos

<!-- Fixe 3 a 6 repositórios no perfil e liste aqui. Sugestão: projetos pessoais com dados públicos que reproduzam sua arquitetura, já que o trabalho em empresa é confidencial. -->

- **[nome-do-projeto]**: pipeline Python → Parquet → BigQuery em arquitetura medalhão.
- **[nome-do-projeto]**: modelo dimensional e dashboard de exemplo.

---

## 📬 Contato

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rodrigo-adriano-kreusch-239ab8213/)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:adrianokreuschrodrigo@gmail.com)

<p align="center"><i>Transformando informação em valor.</i></p>
