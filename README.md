# 🚀 Infraestrutura Automatizada com AWS CloudFormation

Este repositório documenta o desafio de construir e versionar uma infraestrutura completa na AWS utilizando **CloudFormation**. O objetivo é demonstrar como automatizar a criação de componentes como redes, servidores, banco de dados e serviços auxiliares por meio de templates declarativos.

---

## 🎯 Objetivos

- Consolidar o conhecimento em infraestrutura como código na AWS.
- Criar um ambiente completo (rede, aplicação, banco, monitoramento) via CloudFormation.
- Registrar e versionar os artefatos do projeto no GitHub.

---

## 🏗️ Visão Geral da Arquitetura

A infraestrutura modelada inclui:

- **VPC com sub-redes públicas e privadas**: isolamento e roteamento controlado.
- **Application Load Balancer** em subnet pública: expõe a aplicação de forma escalável.
- **Auto Scaling Group com instâncias EC2** em subnet privada: executa a aplicação de forma flexível.
- **Amazon RDS**: banco de dados relacional gerenciado.
- **Buckets S3**: para armazenamento de arquivos estáticos e para guardar o template do CloudFormation.
- **IAM Roles/Policies**: permissões mínimas necessárias para cada serviço.
- **CloudWatch**: coleta logs e métricas para observabilidade.

🖼️ **Diagrama de arquitetura**:

 :agentCitation{citationIndex='0' label='Arquitetura CloudFormation'}


---

## 🧩 Componentes do CloudFormation

O template CloudFormation define recursos como:

- `AWS::VPC::VPC` com CIDR e tabelas de roteamento.
- `AWS::EC2::Subnet` públicas e privadas.
- `AWS::ElasticLoadBalancingV2::LoadBalancer` e `TargetGroup`.
- `AWS::AutoScaling::AutoScalingGroup` associado a `LaunchTemplate`.
- `AWS::RDS::DBInstance` configurado para subnets privadas.
- `AWS::S3::Bucket` para armazenamento de artefatos.
- `AWS::IAM::Role` e `AWS::IAM::Policy` para permissões dos serviços.
- `AWS::CloudWatch::LogGroup` para logs da aplicação.

---
![FreddyKrugerJasonGIF (2)](https://github.com/user-attachments/assets/731acb86-8cd5-4f7e-8dc7-10319b7c25c2)




## 📁 Estrutura do Repositório

