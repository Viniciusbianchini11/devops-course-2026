# Semana 07 – Práticas de DevOps

## Tema:

**Plataformas de Computação em Nuvem Aplicadas ao DevOps: Análise Comparativa entre AWS, Microsoft Azure e Google Cloud Platform**

## Integrantes

- **Daniel Castilho de Oliveira**
- **Rian Karlos Silva Weber**
- **Ricardo de Almeida Sarruf**

---

## 1. Práticas de DevOps Identificadas na Literatura

| Prática DevOps | Finalidade Principal | Relação com AWS, Azure e GCP |
|---|---|---|
| Integração Contínua (CI) | Integrar código frequentemente e validar alterações por meio de builds e testes automatizados. | AWS CodePipeline/CodeBuild, Azure DevOps, GitHub Actions, Google Cloud Build. |
| Entrega e Implantação Contínua (CD) | Automatizar a entrega de versões para ambientes de homologação ou produção. | AWS CodeDeploy, Azure Pipelines, Google Cloud Deploy, ArgoCD e Spinnaker. |
| Infraestrutura como Código (IaC) | Provisionar e gerenciar infraestrutura por meio de arquivos versionáveis e reutilizáveis. | AWS CloudFormation, Terraform, Azure ARM Templates, Bicep, Google Cloud Deployment Manager. |
| Automação de Testes | Validar aplicações antes da implantação, reduzindo erros e retrabalho. | Selenium, Postman/Newman, JMeter, testes integrados aos pipelines de CI/CD. |
| Monitoramento e Observabilidade | Acompanhar métricas, logs, desempenho, falhas e comportamento da aplicação. | Amazon CloudWatch, Azure Monitor, Log Analytics, Google Cloud Operations Suite, Prometheus e Grafana. |
| Containerização | Empacotar aplicações e dependências em containers portáveis e padronizados. | Docker, Amazon ECS/EKS, Azure Container Apps/AKS, Google Kubernetes Engine/Cloud Run. |
| Orquestração com Kubernetes | Automatizar implantação, escalabilidade, recuperação e gerenciamento de containers. | Amazon EKS, Azure AKS, Google GKE. |
| Gerenciamento de Configuração | Automatizar a configuração de servidores, ambientes e aplicações. | Ansible, Puppet, Chef, SaltStack, integráveis às três plataformas. |
| DevSecOps e Segurança Automatizada | Inserir segurança, controle de acesso, segredos e conformidade no pipeline. | AWS IAM/Secrets Manager, Azure Key Vault/RBAC, GCP Secret Manager, Snyk, Vault. |
| Self-Healing e Recuperação Automatizada | Detectar falhas e restaurar serviços automaticamente, reduzindo indisponibilidade. | Kubernetes, health checks, autoscaling, monitoramento e automações em ambientes multi-cloud. |
| MLOps | Automatizar o ciclo de vida de modelos de IA/ML, incluindo treinamento, implantação e monitoramento. | AWS SageMaker Pipelines, Azure Machine Learning, Google Vertex AI. |
| Governança e Policy-as-Code | Automatizar políticas, conformidade, auditoria e controle de infraestrutura. | Azure Policy, AWS Config, IAM Policies, Google Cloud IAM e políticas organizacionais. |

---

## 2. Análise das Principais Práticas

### 2.1 Integração Contínua (Continuous Integration – CI)

A **Integração Contínua** consiste na prática de integrar frequentemente alterações de código em um repositório compartilhado. Cada alteração passa por processos automatizados de compilação, verificação e testes, permitindo identificar erros de integração ainda nas fases iniciais do desenvolvimento.

Na literatura analisada, a CI aparece como uma das bases do DevOps moderno, pois reduz problemas decorrentes de integrações tardias, melhora a qualidade do código e acelera o feedback para os desenvolvedores. Em ambientes de nuvem, essa prática é fortalecida por serviços gerenciados, como **AWS CodeBuild**, **Azure DevOps Pipelines**, **GitHub Actions** e **Google Cloud Build**.

No contexto comparativo entre AWS, Azure e GCP, observa-se que todas as plataformas oferecem suporte robusto à integração contínua. A diferença está principalmente no grau de integração com seus ecossistemas: a Azure se destaca pela integração com Azure DevOps e GitHub; a AWS oferece um conjunto amplo e maduro de serviços nativos; e a GCP apresenta forte integração com Cloud Build, containers e fluxos cloud-native.

---

### 2.2 Entrega Contínua e Implantação Contínua (Continuous Delivery/Deployment – CD)

A **Entrega Contínua** e a **Implantação Contínua** são práticas voltadas à automação do processo de disponibilização de novas versões de software. Na entrega contínua, o sistema é mantido sempre em estado implantável, ainda que a liberação final possa depender de aprovação manual. Na implantação contínua, as alterações aprovadas nos testes automatizados podem ser levadas diretamente para produção.

Os estudos analisados demonstram que pipelines de CI/CD são fundamentais para reduzir o tempo de entrega, aumentar a frequência de releases e melhorar a confiabilidade dos processos de implantação. Essa prática é especialmente relevante em ambientes cloud-native, nos quais a infraestrutura é elástica, os ambientes podem ser criados sob demanda e os serviços são integrados por APIs.

Nas plataformas comparadas, a AWS oferece recursos como **CodePipeline**, **CodeDeploy** e **CodeBuild**; a Azure conta com **Azure Pipelines** e integração nativa com repositórios e serviços corporativos; e a GCP utiliza **Cloud Build** e serviços integrados a containers e Kubernetes. Em ambientes Kubernetes, ferramentas como **ArgoCD**, **Flux** e **Spinnaker** também aparecem como alternativas importantes para entrega contínua.

---

### 2.3 Infraestrutura como Código (Infrastructure as Code – IaC)

A **Infraestrutura como Código (IaC)** é uma das práticas mais recorrentes na literatura. Ela consiste em descrever a infraestrutura por meio de arquivos de configuração ou código, permitindo que servidores, redes, bancos de dados, clusters, permissões e demais recursos sejam criados de forma automatizada, padronizada e versionada.

Essa prática reduz a dependência de configurações manuais, aumenta a rastreabilidade das mudanças e facilita a replicação de ambientes. Com IaC, é possível criar ambientes de desenvolvimento, teste, homologação e produção com maior consistência, reduzindo divergências entre configurações.

Entre as principais ferramentas identificadas estão:

- **Terraform**, com suporte multi-cloud;
- **AWS CloudFormation**, voltado ao ecossistema AWS;
- **Azure Resource Manager (ARM Templates)** e **Bicep**, voltados ao Azure;
- **Google Cloud Deployment Manager**, voltado ao GCP;
- **Pulumi**, que permite IaC com linguagens de programação;
- **Ansible**, utilizado tanto para provisionamento quanto para configuração.

No tema do grupo, IaC é uma prática essencial porque permite comparar como AWS, Azure e GCP oferecem mecanismos de automação e padronização da infraestrutura. Além disso, favorece estratégias multi-cloud, pois ferramentas como Terraform permitem trabalhar com mais de um provedor em uma mesma abordagem de automação.

---

### 2.4 Automação de Testes

A **automação de testes** é uma prática fundamental para garantir que as alterações de código sejam validadas antes da implantação. Ela aparece na literatura como elemento complementar aos pipelines de CI/CD, permitindo detectar falhas funcionais, problemas de integração, inconsistências de API e gargalos de desempenho antes que a aplicação chegue ao ambiente de produção.

Entre as ferramentas mencionadas estão:

- **Selenium**, para testes de interface;
- **Postman/Newman**, para testes de APIs;
- **JMeter**, para testes de carga e desempenho;
- testes unitários, testes de integração e testes automatizados incorporados aos pipelines.

A automação de testes contribui diretamente para a confiabilidade do DevOps, pois reduz a probabilidade de erros manuais e aumenta a segurança das implantações contínuas. Em AWS, Azure e GCP, esses testes podem ser executados em esteiras automatizadas e integrados a serviços de build, deploy e monitoramento.

---

### 2.5 Monitoramento e Observabilidade

O **monitoramento** e a **observabilidade** são práticas indispensáveis para acompanhar o comportamento das aplicações e da infraestrutura após a implantação. Enquanto o monitoramento tradicional se concentra em métricas e alertas, a observabilidade amplia essa visão por meio de logs, traces, métricas, eventos e análise de desempenho.

A literatura analisada destaca que o monitoramento contínuo é essencial para identificar falhas, gargalos, indisponibilidades e degradação de performance. Em ambientes DevOps, essa prática gera feedback contínuo para as equipes, permitindo respostas rápidas e melhoria constante do sistema.

As principais ferramentas e serviços identificados foram:

- **Amazon CloudWatch**, para monitoramento na AWS;
- **Azure Monitor** e **Log Analytics**, no Azure;
- **Google Cloud Operations Suite**, no GCP;
- **Prometheus** e **Grafana**, em ambientes multi-cloud e Kubernetes;
- **Datadog** e **New Relic**, como soluções de observabilidade multi-cloud.

No contexto do artigo do grupo, essa prática é importante porque a escolha da plataforma em nuvem não deve considerar apenas implantação e custo, mas também a capacidade de acompanhar desempenho, uso de recursos, falhas e experiência do usuário.

---

### 2.6 Containerização

A **containerização** consiste no empacotamento da aplicação com suas dependências em uma unidade padronizada e portátil, geralmente utilizando **Docker**. Essa prática aparece fortemente associada a ambientes cloud-native, pois facilita a implantação consistente de aplicações em diferentes provedores de nuvem.

Os artigos analisados apontam que containers contribuem para maior portabilidade, escalabilidade e padronização dos ambientes. Em vez de depender de configurações específicas de servidores, a aplicação passa a ser executada em containers, reduzindo conflitos de ambiente e facilitando a movimentação entre AWS, Azure e GCP.

Exemplos de serviços relacionados:

- **AWS ECS**, **AWS EKS** e **AWS App Runner**;
- **Azure Kubernetes Service (AKS)** e **Azure Container Apps**;
- **Google Kubernetes Engine (GKE)** e **Google Cloud Run**.

Essa prática é especialmente relevante para o tema do grupo, pois aplicações containerizadas podem ser avaliadas comparativamente entre diferentes plataformas de nuvem, considerando desempenho, facilidade de implantação, escalabilidade e custo.

---

### 2.7 Orquestração com Kubernetes

O **Kubernetes** é uma das tecnologias mais citadas nos estudos relacionados a DevOps cloud-native. Ele atua como plataforma de orquestração de containers, automatizando implantação, escalabilidade, balanceamento, recuperação e gerenciamento de aplicações distribuídas.

Na literatura, Kubernetes aparece associado a práticas como:

- escalabilidade automática;
- recuperação de falhas;
- distribuição de workloads;
- padronização de ambientes;
- suporte a arquiteturas multi-cloud;
- integração com pipelines de CI/CD;
- implantação declarativa.

Nas plataformas analisadas, o Kubernetes é oferecido por meio de serviços gerenciados:

- **Amazon Elastic Kubernetes Service (EKS)**;
- **Azure Kubernetes Service (AKS)**;
- **Google Kubernetes Engine (GKE)**.

A prática é relevante porque permite comparar a maturidade dos provedores no suporte a aplicações modernas, especialmente aquelas baseadas em microservices, containers e alta disponibilidade.

---

### 2.8 Gerenciamento de Configuração

O **gerenciamento de configuração** envolve automatizar a instalação, parametrização e manutenção de sistemas, aplicações e servidores. Essa prática reduz inconsistências entre ambientes e permite que configurações sejam aplicadas de forma repetível e auditável.

As ferramentas mais associadas a essa prática são:

- **Ansible**;
- **Puppet**;
- **Chef**;
- **SaltStack**.

No DevOps, essa prática complementa a Infraestrutura como Código, pois enquanto a IaC provisiona recursos, o gerenciamento de configuração garante que esses recursos estejam corretamente configurados. Em ambientes de nuvem, isso é essencial para manter consistência entre diferentes regiões, contas, ambientes e provedores.

---

### 2.9 DevSecOps e Segurança Automatizada

A literatura também evidencia a importância da integração da segurança ao ciclo DevOps, prática conhecida como **DevSecOps**. Essa abordagem busca inserir controles de segurança desde as fases iniciais do desenvolvimento, evitando que a segurança seja tratada apenas no final do ciclo de entrega.

As práticas identificadas incluem:

- controle de identidade e acesso;
- gerenciamento de segredos;
- criptografia;
- auditoria;
- análise de vulnerabilidades;
- segurança de containers;
- validação de políticas no pipeline.

Ferramentas e serviços relacionados:

- **AWS IAM** e **AWS Secrets Manager**;
- **Azure Key Vault**, **RBAC** e **Azure Policy**;
- **Google Secret Manager** e **Cloud IAM**;
- **HashiCorp Vault**;
- **Snyk** e **Aqua Security**.

No contexto de AWS, Azure e GCP, DevSecOps é essencial porque ambientes de nuvem operam sob modelo de responsabilidade compartilhada, no qual o provedor protege parte da infraestrutura, mas o cliente continua responsável por permissões, configurações, dados, aplicações e políticas de acesso.

---

### 2.10 Self-Healing e Recuperação Automatizada

A prática de **self-healing** está relacionada à capacidade de um sistema detectar falhas e executar ações automáticas de recuperação, sem depender imediatamente de intervenção humana. Essa prática aparece associada principalmente a Kubernetes, monitoramento em tempo real, health checks e automação de resposta a incidentes.

Em ambientes multi-cloud, mecanismos de self-healing são relevantes porque aumentam a resiliência e reduzem o tempo de indisponibilidade. Entre os exemplos identificados estão:

- reinicialização automática de pods;
- substituição de instâncias com falha;
- alertas automáticos;
- redistribuição de workloads;
- recuperação baseada em políticas;
- integração com ferramentas como Datadog, Prometheus e Grafana.

Essa prática reforça a maturidade operacional do DevOps, pois o objetivo não é apenas implantar rapidamente, mas manter o sistema disponível, resiliente e capaz de se recuperar diante de falhas.

---

### 2.11 MLOps

Embora o foco principal do trabalho seja DevOps em plataformas de nuvem, a literatura sobre workloads de IA/ML também aponta a presença de práticas de **MLOps**, que representam a aplicação dos princípios DevOps ao ciclo de vida de modelos de machine learning.

As práticas de MLOps incluem:

- versionamento de modelos;
- pipelines de treinamento;
- implantação automatizada de modelos;
- monitoramento de desempenho;
- detecção de drift;
- governança de dados e modelos;
- integração com CI/CD.

Nas plataformas analisadas, destacam-se:

- **AWS SageMaker Pipelines**;
- **Azure Machine Learning**;
- **Google Vertex AI**.

Essa prática demonstra que o DevOps se expande para além do desenvolvimento tradicional de software, alcançando também aplicações inteligentes, pipelines de dados e modelos de aprendizado de máquina.

---

### 2.12 Governança, Compliance e Policy-as-Code

A governança em ambientes DevOps envolve o controle sobre padrões, políticas, conformidade, permissões, auditoria e segurança. Em ambientes de nuvem, essa prática é especialmente importante porque a facilidade de provisionamento pode gerar riscos de configuração inadequada, uso excessivo de recursos, exposição de dados e inconsistência entre ambientes.

A literatura aponta que práticas de governança podem ser automatizadas por meio de:

- políticas de acesso;
- validação de conformidade;
- trilhas de auditoria;
- templates padronizados;
- controle de custos;
- backup e recuperação;
- políticas como código.

Exemplos de serviços:

- **Azure Policy** e **RBAC**;
- **AWS Config**, **IAM** e políticas organizacionais;
- **Google Cloud IAM** e políticas de organização;
- **Azure Blueprints**;
- ferramentas de auditoria e compliance integradas ao pipeline.

Essa prática é relevante para empresas que utilizam nuvem em escala, pois permite equilibrar agilidade e controle, evitando que a automação gere ambientes inseguros ou fora dos padrões corporativos.

---

## 3. Relação das Práticas com AWS, Azure e GCP

| Categoria | AWS | Microsoft Azure | Google Cloud Platform |
|---|---|---|---|
| CI/CD | CodePipeline, CodeBuild, CodeDeploy | Azure DevOps, Azure Pipelines, GitHub Actions | Cloud Build, Cloud Deploy |
| IaC | CloudFormation, Terraform, CDK | ARM Templates, Bicep, Terraform | Deployment Manager, Terraform |
| Containers | ECS, EKS, App Runner | AKS, Azure Container Apps | GKE, Cloud Run |
| Monitoramento | CloudWatch, X-Ray | Azure Monitor, Log Analytics | Cloud Operations Suite |
| Segurança | IAM, Secrets Manager, KMS | Azure Key Vault, RBAC, Azure Policy | Secret Manager, Cloud IAM |
| MLOps | SageMaker Pipelines | Azure Machine Learning | Vertex AI Pipelines |
| Orquestração | Amazon EKS | Azure AKS | Google Kubernetes Engine |
| Governança | AWS Config, Organizations | Azure Policy, Blueprints | Organization Policy, Cloud IAM |

---

## 4. Síntese Comparativa

A análise das práticas DevOps mostra que as três plataformas oferecem recursos robustos para automação, integração contínua, implantação contínua, infraestrutura como código, monitoramento e segurança. Entretanto, cada provedor apresenta características próprias.

A **AWS** se destaca pela amplitude de serviços, maturidade do ecossistema e grande variedade de ferramentas nativas para CI/CD, infraestrutura, segurança, containers e observabilidade. É uma plataforma adequada para cenários complexos, escaláveis e com alto grau de customização.

A **Microsoft Azure** apresenta forte integração com ambientes corporativos, especialmente organizações que já utilizam ferramentas Microsoft, Azure Active Directory, GitHub e Azure DevOps. Sua principal vantagem está na integração com fluxos empresariais, governança, RBAC, Azure Policy e pipelines bem integrados.

A **Google Cloud Platform** se destaca pela abordagem cloud-native, pelo forte suporte a containers, Kubernetes, Cloud Run, Vertex AI e ferramentas orientadas a dados e inteligência artificial. A GCP tende a ser atrativa para cenários que exigem experimentação rápida, aplicações containerizadas e integração com serviços gerenciados modernos.

Portanto, a escolha da plataforma ideal para práticas DevOps depende do contexto organizacional, do nível de maturidade da equipe, da arquitetura da aplicação, dos requisitos de governança, dos custos e do grau de dependência desejado em relação ao provedor.

---

## 5. Referências

ABRAHAM, Anoop. **Analyzing the System Features, Usability, and Performance of a Containerized Application on Cloud Computing Systems**. 2023. 52 p. Graduate Thesis (Master of Science in Computer Science) — Texas A&M University-San Antonio, San Antonio, 2023. Disponível em: <https://digitalcommons.tamusa.edu/masters_theses/9>. Acesso em: 11 maio 2026.

BALADARI, Venkata. **The Role of Software Developers in Transitioning On-Premises Applications to Cloud Platforms: Strategies and Challenges**. *Journal of Scientific and Engineering Research*, v. 8, n. 1, p. 270-278, 2021. DOI: <https://doi.org/10.5281/zenodo.15044869>.

BANERJEE, Rahul; CHATTERJEE, Tathagata. **Comparative Evaluation of Cloud-Native and VM-Based CI/CD Pipelines for Automated DevOps Deployments**. *Asian Journal of Research in Computer Science*, v. 18, n. 11, p. 153-171, 2025. DOI: <https://doi.org/10.9734/ajrcos/2025/v18i11785>.

DESHPANDE, Vaishnavi Udayrao. **Management of Self-Healing Systems for Multi-Cloud Deployments on Kubernetes**. 2024. 18 p. MSc Research Project (Master of Science in Cloud Computing) — School of Computing, National College of Ireland, 2024.

GADEKAR, Amruta; VARMA, Nayan; MORE, Prerana; SALUNKHE, Ashish. **Comparing Major Cloud Providers for AI/ML Workloads: AWS vs Azure vs GCP**. *International Journal of Advanced Research in Education and Technology (IJARETY)*, v. 11, n. 3, p. 1271-1276, maio/jun. 2024. DOI: <https://doi.org/10.15680/IJARETY.2024.1103061>.

GUJJALA, Praveen Kumar Reddy. **Cloud Enabled Intelligent Enterprise Healthcare Framework with Machine Learning Based on Artificial Intelligence and Blockchain Governance**. *International Journal of Research Publications in Engineering, Technology and Management (IJRPETM)*, v. 8, n. 5, p. 12873-12882, set./out. 2025. DOI: <https://doi.org/10.15662/IJRPETM.2025.0805025>.

JOYCE, Sheetal. **Accelerating Enterprise SAP Workload Performance and Automation Using Microsoft Azure Center for SAP Solutions Through Cloud Native Architecture Intelligent Orchestration and Infrastructure as Code**. *IACSE - International Journal of Information Technology (IACSE-IJIT)*, v. 4, n. 1, p. 8-30, 2023. DOI: <https://doi.org/10.5281/zenodo.17786229>.

KISHAN, Raj. **The Role of DevOps and Automation in Cloud Transition**. *International Journal of Computer Technology and Electronics Communication (IJCTEC)*, v. 5, n. 2, p. 4805-4808, mar./abr. 2022. DOI: <https://doi.org/10.15680/IJCTECE.2022.0502001>.

MURPHY, Olga. **Adoption of Infrastructure as Code (IaC) in Real World: Lessons and Practices from Industry**. 2022. 61 p. Master’s Thesis (Information Technology — Full-Stack Degree Programme) — JAMK University of Applied Sciences, Jyväskylä, 2022.

PASHIKANTI, Santosh. **Data Governance and Compliance in Cloud-Based Data Engineering Pipelines**. *International Journal of Leading Research Publication (IJLRP)*, v. 5, n. 8, p. 1-7, ago. 2024. Article ID: IJLRP24081150.

RAVI, Vamsee Krishna; JAMPANI, Sridhar; GUDAVALLI, Sunil; GOEL, Punit; CHHAPOLA, Akshun; SHRIVASTAV, Aman. **Cloud-native DevOps Practices for SAP Deployment**. *International Journal of Research in Modern Engineering and Emerging Technology (IJRMEET)*, v. 10, n. 6, p. 26-50, jun. 2022.

VELDI, Santhosh Rao. **Infrastructure-as-Code with Scripting: A Technical Review**. *Journal of Computer Science and Technology Studies*, v. 7, n. 6, p. 345-352, 2025. DOI: <https://doi.org/10.32996/jcsts.2025.7.6.41>.
