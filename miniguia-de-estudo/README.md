# Miniguia de Estudo - Cloud Computing com AWS

> Entrega final do caderno temático: conteúdo consolidado para revisões rápidas. Este guia reúne os **resumos estruturados**, o **glossário** e um **conjunto de prompts reutilizáveis** para futuras sessões de estudo com o NotebookLM.

## 1. Resumos estruturados

### 1.1 O que é computação em nuvem

Computação em nuvem é o **fornecimento sob demanda de recursos de TI pela internet**, com **cobrança conforme o uso (pay-as-you-go)**. Em vez de comprar e manter servidores e datacenters próprios, o usuário acessa serviços como poder de processamento, armazenamento e banco de dados conforme a necessidade, de um provedor de nuvem.

**Características essenciais** (definição do NIST SP 800-145):

| Característica | Descrição |
| --- | --- |
| **Self-service sob demanda** | O usuário provisiona recursos sem interação humana com o provedor |
| **Amplo acesso pela rede** | Recursos acessíveis pela rede por dispositivos heterogêneos |
| **Pooling de recursos** | Recursos compartilhados entre múltiplos usuários (multi-tenant) |
| **Elasticidade rápida** | Escalar para cima/baixo rapidamente, às vezes automaticamente |
| **Serviço medido** | O uso é medido/monitorado e cobrado conforme o consumo |

**Benefícios** (visão AWS): agilidade (implantar em minutos), elasticidade (escalar conforme a demanda), redução de custos (capex -> opex), alcance global e confiabilidade (datacenters distribuídos).

### 1.2 Modelos de serviço

| Modelo | O usuário gerencia | O provedor gerencia | Exemplo na AWS |
| --- | --- | --- | --- |
| **IaaS** (Infraestrutura como Serviço) | SO, aplicações, runtime, dados | Servidores, rede, virtualização, datacenter | Amazon EC2 |
| **PaaS** (Plataforma como Serviço) | Aplicações e dados | Plataforma completa (SO, runtime, infra) | AWS Elastic Beanstalk, AWS Lambda |
| **SaaS** (Software como Serviço) | Dados e usuários | Tudo (software e infraestrutura) | Aplicações SaaS da AWS e parceiros |

**Regra geral**: quanto mais alto o modelo, menos controle e mais responsabilidade transferida ao provedor; quanto mais baixo, mais controle e mais gerenciamento pelo usuário.

### 1.3 Modelos de implantação

- **Nuvem pública**: infraestrutura do provedor, compartilhada e acessível pela internet (ex.: AWS, Azure, GCP).
- **Nuvem privada**: infraestrutura exclusiva de uma organização (on-premises ou hospedada).
- **Nuvem híbrida**: combinação de pública e privada (ex.: AWS Outposts conectando on-premises à nuvem).
- **Comunitária**: compartilhada por organizações com interesses comuns.

### 1.4 Infraestrutura global da AWS

- **Região (Region)**: localização geográfica com múltiplas AZs (ex.: us-east-1, sa-east-1 em São Paulo).
- **Zona de disponibilidade (AZ)**: datacenters isolados dentro de uma região, conectados por rede de baixa latência. Múltiplas AZs garantem **alta disponibilidade** e **tolerância a falhas**.
- **Edge locations / CloudFront**: distribuição de conteúdo com baixa latência.

### 1.5 Modelo de Responsabilidade Compartilhada

- **AWS = Segurança DA nuvem**: hardware, software, rede, datacenters e infraestrutura global.
- **Cliente = Segurança NA nuvem**: dados, plataformas, aplicações, gerenciamento de identidade e acesso (IAM), configuração de serviços, sistema operacional (em IaaS) e permissões.
- **Depende do modelo**: em SaaS o provedor assume mais; em IaaS o cliente assume mais.

### 1.6 AWS Well-Architected Framework

O framework ajuda a avaliar arquiteturas contra boas práticas e medir pontos de melhoria. Pilares:

| Pilar | Foco |
| --- | --- |
| **Excelência Operacional** | Operar e monitorar sistemas, aprender e melhorar continuamente |
| **Segurança** | Proteger dados, sistemas e ativos; identificar e gerenciar acessos |
| **Confiabilidade** | Recuperar-se de falhas, escalar e atender às expectativas de disponibilidade |
| **Eficiência de Performance** | Usar recursos de TI de forma eficiente para cumprir requisitos |
| **Otimização de Custos** | Evitar gastos desnecessários e usar os recursos da forma mais econômica |
| **Sustentabilidade** | Minimizar os impactos ambientais dos workloads |

### 1.7 Serviços AWS por categoria (visão geral)

| Categoria | Serviços principais |
| --- | --- |
| Compute | Amazon EC2, AWS Lambda, Elastic Beanstalk, Auto Scaling |
| Armazenamento | Amazon S3 (objetos), Amazon EBS (blocos), Amazon EFS (arquivos) |
| Banco de dados | Amazon RDS, Amazon DynamoDB (NoSQL), Amazon Aurora |
| Rede e CDN | Amazon VPC, CloudFront, Elastic Load Balancing, Route 53 |
| Segurança e identidade | IAM, AWS WAF, AWS Shield, AWS KMS |
| Integração | Amazon SQS, SNS, EventBridge |
| Gerenciamento | CloudWatch (monitoramento), CloudTrail (auditoria), AWS Config |

## 2. Glossário - principais conceitos

| Termo | Definição |
| --- | --- |
| **Cloud computing** | Fornecimento sob demanda de recursos de TI pela internet com cobrança conforme o uso |
| **IaaS** | Infraestrutura como serviço: servidores virtuais, armazenamento e rede sob demanda |
| **PaaS** | Plataforma como serviço: ambiente gerenciado para desenvolver e implantar aplicações |
| **SaaS** | Software como serviço: aplicação completa entregue pela internet |
| **On-demand / self-service** | Provisionar recursos sem intervenção manual do provedor |
| **Elasticidade** | Capacidade de aumentar ou reduzir recursos automaticamente conforme a demanda |
| **Pay-as-you-go** | Modelo de cobrança em que se paga somente pelo que é consumido |
| **Capex** | Despesa de capital (investimento fixo, ex.: compra de servidores) |
| **Opex** | Despesa operacional (custo recorrente, ex.: fatura mensal do provedor) |
| **Região (Region)** | Área geográfica da AWS composta por múltiplas AZs |
| **Zona de disponibilidade (AZ)** | Um ou mais datacenters isolados dentro de uma região |
| **Tolerância a falhas** | Capacidade do sistema de continuar operando diante de falhas de componentes |
| **Alta disponibilidade** | Capacidade de manter o sistema acessível e operacional por longos períodos |
| **Responsabilidade compartilhada** | Divisão de responsabilidades de segurança entre provedor (segurança da nuvem) e cliente (segurança na nuvem) |
| **IAM (Identity and Access Management)** | Serviço AWS para gerenciar usuários, grupos, papéis e permissões |
| **VPC** | Rede virtual isolada dentro da nuvem AWS onde se provisionam recursos |
| **Amazon S3** | Serviço de armazenamento de objetos escalável e durável |
| **Amazon EC2** | Serviço de servidores virtuais (instâncias) sob demanda |
| **AWS Lambda** | Compute serverless: executa código sem gerenciar servidores |
| **Serverless** | Modelo em que o provedor gerencia a infraestrutura e o usuário paga pela execução |
| **Auto Scaling** | Ajuste automático da capacidade de recursos conforme a demanda |
| **CloudWatch** | Serviço de monitoramento de métricas, logs e alarmes |
| **CloudTrail** | Serviço de auditoria que registra chamadas à API da conta |
| **Well-Architected Framework** | Conjunto de boas práticas da AWS organizadas em pilares para projetar arquiteturas |

## 3. Conjunto de prompts reutilizáveis

Prontos para usar em futuras revisões no NotebookLM (substitua as fontes conforme seu notebook).

### Revisão de fundamentos

```
Com base no NIST SP 800-145, explique o que é computação em nuvem e liste as 5 características essenciais. Para cada característica, escreva um exemplo prático e cite a fonte.
```

```
Crie um quiz de 5 perguntas de múltipla escolha sobre as características essenciais da nuvem. Ao final, dê o gabarito e explique cada resposta citando as fontes.
```

### Revisão de modelos de serviço

```
Faça uma tabela comparando IaaS, PaaS e SaaS com: definição, o que o usuário gerencia, o que o provedor gerencia, e 2 exemplos na AWS para cada. Cite as fontes.
```

```
Dê 3 exemplos de aplicações que fariam sentido rodar em cada modelo (IaaS, PaaS, SaaS) e explique o motivo da escolha.
```

### Revisão de arquitetura (Well-Architected)

```
Explique os 5 pilares do AWS Well-Architected Framework. Para cada pilar, inclua: objetivo, pergunta-chave e uma prática recomendada. Cite as fontes.
```

```
Considere uma aplicação web que precisa de alta disponibilidade e custo controlado. Proponha uma arquitetura simples na AWS aplicando os pilares de confiabilidade e otimização de custos. Explique cada decisão e cite as fontes.
```

### Revisão de segurança

```
Explique o modelo de responsabilidade compartilhada da AWS: liste as responsabilidades do cliente e as da AWS e dê 3 exemplos de cada. Cite as fontes.
```

```
Crie uma tabela que mostra, para IaaS, PaaS e SaaS, quem é responsável por: infraestrutura física, sistema operacional, aplicação e dados. Cite as fontes.
```

### Técnica de autoavaliação

```
Gere 10 perguntas de revisão sobre cloud computing e AWS baseadas apenas nas fontes do notebook, do nível fácil ao difícil. Depois que eu responder, corrija minhas respostas e aponte o que preciso revisar.
```

```
Resuma os conceitos mais importantes das minhas fontes em 15 flashcards no formato "pergunta -> resposta", com citações, para eu revisar rapidamente.
```

---

*Guia elaborado a partir da curadoria de fontes e das respostas do NotebookLM. Para atualizações, refaça as perguntas estratégicas do arquivo de engenharia de prompts e consolide aqui os novos aprendizados.*
