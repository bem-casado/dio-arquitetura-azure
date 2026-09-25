# Construindo Arquiteturas no Azure

Este repositório foi criado como parte de um desafio da **DIO (Digital Innovation One)** para documentar os principais conceitos estudados sobre **arquitetura de soluções na Microsoft Azure**.

O objetivo é registrar uma visão prática de como os recursos da Azure podem ser organizados para criar ambientes mais seguros, disponíveis, escaláveis e fáceis de administrar.

## Objetivo do desafio

Durante o laboratório, o foco é compreender como diferentes serviços da Azure podem ser combinados na construção de uma arquitetura em nuvem.

Entre os principais pontos estudados estão:

- organização de recursos;
- regiões e zonas de disponibilidade;
- redes virtuais;
- máquinas virtuais e outros recursos de computação;
- armazenamento;
- bancos de dados;
- segurança e controle de acesso;
- monitoramento;
- escalabilidade;
- custos.

## Conceitos importantes

### Regiões

Uma **região da Azure** é uma área geográfica que contém um ou mais datacenters.

A escolha da região pode impactar fatores como:

- latência;
- disponibilidade dos serviços;
- requisitos de residência de dados;
- custo;
- recuperação de desastres.

### Zonas de disponibilidade

As **Availability Zones** são datacenters fisicamente separados dentro de uma mesma região.

Elas podem ser utilizadas para aumentar a disponibilidade de uma aplicação, reduzindo o impacto de falhas em um único datacenter.

### Grupos de recursos

Um **Resource Group** é um agrupamento lógico utilizado para organizar recursos relacionados.

Por exemplo:

```text
Resource Group
├── Virtual Network
├── Virtual Machine
├── Banco de Dados
├── Storage Account
└── Monitoramento
```

Isso facilita tarefas como organização, controle de acesso, monitoramento e exclusão dos recursos de um ambiente.

## Exemplo de arquitetura

Uma arquitetura simples de aplicação na Azure pode ser representada da seguinte forma:

```text
Usuário
   ↓
Internet
   ↓
Aplicação / Serviço Web
   ↓
Rede Virtual (VNet)
   ├── Camada de Aplicação
   └── Banco de Dados
            ↓
        Armazenamento

Monitoramento e Segurança atuam sobre todo o ambiente.
```

Em uma implementação real, outros recursos podem ser adicionados conforme a necessidade de disponibilidade, desempenho, segurança e escala.

## Rede

A **Azure Virtual Network (VNet)** permite criar uma rede privada dentro da Azure.

Dentro de uma VNet podem existir diferentes sub-redes para separar os componentes da solução.

Exemplo:

```text
VNet
├── Subnet Front-end
├── Subnet Back-end
└── Subnet Banco de Dados
```

Essa separação ajuda na organização e permite aplicar regras de segurança específicas para cada camada.

## Computação

A Azure oferece diferentes formas de executar aplicações.

Alguns exemplos são:

- **Azure Virtual Machines:** máquinas virtuais com maior controle sobre o sistema operacional;
- **Azure App Service:** serviço gerenciado para aplicações web;
- **Azure Functions:** execução de código baseada em eventos;
- **Azure Kubernetes Service (AKS):** gerenciamento de aplicações em containers.

A escolha depende dos requisitos do sistema e do nível de gerenciamento desejado.

## Armazenamento

A Azure possui diferentes serviços de armazenamento para diferentes tipos de dados.

O **Azure Storage Account**, por exemplo, pode oferecer:

- Blob Storage;
- File Shares;
- Queues;
- Tables.

É importante escolher o tipo de armazenamento adequado conforme o formato dos dados, desempenho esperado e necessidade de redundância.

## Banco de dados

A camada de dados pode utilizar diferentes serviços gerenciados da Azure, como:

- Azure SQL Database;
- Azure SQL Managed Instance;
- Azure Database for PostgreSQL;
- Azure Cosmos DB.

Serviços gerenciados reduzem a necessidade de administrar diretamente aspectos como infraestrutura, atualização e disponibilidade.

## Segurança

Uma arquitetura em nuvem deve considerar segurança desde o início.

Algumas práticas importantes são:

- utilizar o princípio do menor privilégio;
- controlar acessos com Azure RBAC;
- proteger credenciais e segredos;
- restringir tráfego de rede;
- evitar exposição pública desnecessária;
- habilitar logs e monitoramento;
- utilizar identidades gerenciadas quando possível.

## Escalabilidade e disponibilidade

Uma solução bem planejada deve considerar como responder ao aumento de carga e como se comportar diante de falhas.

Algumas estratégias incluem:

- escalabilidade vertical;
- escalabilidade horizontal;
- balanceamento de carga;
- múltiplas instâncias;
- zonas de disponibilidade;
- backups;
- replicação;
- planos de recuperação de desastre.

## Monitoramento

O monitoramento ajuda a identificar problemas de desempenho, falhas e comportamentos inesperados.

Na Azure, serviços como **Azure Monitor** e **Log Analytics** podem ser utilizados para acompanhar:

- métricas;
- logs;
- utilização de recursos;
- alertas;
- disponibilidade.

## Custos

Arquitetura também envolve controle financeiro.

Antes de provisionar recursos é importante avaliar:

- tamanho das máquinas;
- quantidade de armazenamento;
- tráfego de rede;
- região;
- banco de dados utilizado;
- tempo de execução dos recursos.

Em ambientes de estudo, recursos que não serão mais utilizados devem ser removidos para evitar cobranças desnecessárias.

## Boas práticas

Durante o estudo de arquitetura na Azure, algumas boas práticas importantes são:

1. organizar os recursos utilizando Resource Groups;
2. separar componentes utilizando redes e sub-redes;
3. liberar somente os acessos necessários;
4. preferir serviços gerenciados quando eles atendem ao requisito;
5. projetar pensando em disponibilidade e recuperação;
6. habilitar monitoramento e alertas;
7. acompanhar custos;
8. documentar a arquitetura e as decisões tomadas.

## Resumo

A construção de uma arquitetura na Azure não consiste apenas em criar recursos isolados.

É necessário pensar na relação entre:

```text
Computação
    +
Rede
    +
Dados
    +
Armazenamento
    +
Segurança
    +
Monitoramento
    +
Custos
```

Uma boa arquitetura procura equilibrar **disponibilidade, segurança, desempenho, escalabilidade, simplicidade e custo**.

## Referências

- [Documentação do Microsoft Azure](https://learn.microsoft.com/pt-br/azure/)
- [Fundamentos de arquitetura do Azure](https://learn.microsoft.com/pt-br/azure/architecture/)
- [Azure Well-Architected Framework](https://learn.microsoft.com/pt-br/azure/well-architected/)
- [Documentação do GitHub](https://docs.github.com/)
- [Markdown no GitHub](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

---

**Desafio de Projeto — DIO**