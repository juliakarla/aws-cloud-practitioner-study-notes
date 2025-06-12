## Este laboratório faz parte do meu estudo para a certificação **AWS Certified Cloud Practitioner**.

# 💻 Laboratório 2: Criar a VPC e Executar um Servidor Web

## 🎯 Objetivos

- Criar uma VPC personalizada
- Criar sub-redes públicas e privadas em múltiplas Zonas de Disponibilidade
- Configurar um grupo de segurança para acesso HTTP
- Iniciar uma instância EC2 e configurar um servidor web com Apache e PHP

## 🛠️ Recursos Criados

### VPC
- Nome: "lab-vpc"
- CIDR: "10.0.0.0/16"

### Sub-redes
| Nome                         | Tipo      | Zona de Disponibilidade | CIDR         |
|------------------------------|-----------|--------------------------|--------------|
| lab-subnet-public1-us-east-1a  | Pública   | us-east-1a               | 10.0.0.0/24  |
| lab-subnet-private1-us-east-1a | Privada   | us-east-1a               | 10.0.1.0/24  |
| lab-subnet-public2             | Pública   | us-east-1b               | 10.0.2.0/24  |
| lab-subnet-private2            | Privada   | us-east-1b               | 10.0.3.0/24  |

### Tabelas de Rotas
- "lab-rtb-public": direciona tráfego 0.0.0.0/0 para o gateway de internet
- "lab-rtb-private1-us-east-1a": direciona tráfego 0.0.0.0/0 para o gateway NAT

### Gateways
- Internet Gateway: "lab-igw"
- NAT Gateway: "lab-nat-public1-us-east-1a"

## 🔐 Grupo de Segurança

- **Nome:** Web Security Group  
- **Regra de entrada:**  
  - Tipo: HTTP  
  - Porta: 80  
  - Origem: Anywhere (0.0.0.0/0)  
  - Descrição: Permit web requests

## 🚀 Instância EC2

- **Nome:** Web Server 1
- **AMI:** Amazon Linux 2023
- **Tipo:** t2.micro
- **Par de Chaves:** "vockey"
- **Sub-rede:** "lab-subnet-public2"
- **IP Público:** Atribuído automaticamente
- **Grupo de Segurança:** Web Security Group

### Script de inicialização (Dados do usuário) - bash

#!/bin/bash
# Install Apache Web Server and PHP
dnf install -y httpd wget php mariadb105-server
# Download Lab files
wget https://aws-tc-largeobjects.s3.us-west-2.amazonaws.com/CUR-TF-100-ACCLFO-2/2-lab2-vpc/s3/lab-app.zip
unzip lab-app.zip -d /var/www/html/
# Turn on web server
chkconfig httpd on
service httpd start

## 🌐 Testando o Servidor Web
Após a instância EC2 iniciar, copie o DNS Público IPv4 da instância e cole no navegador.

- Você deverá ver uma página com: Logotipo da AWS e Informações de metadados da instância EC2

## 🧠 Aprendizados
- Compreensão prática de como redes virtuais funcionam na AWS
- Conceito de sub-redes públicas e privadas
- Função dos gateways e tabelas de rotas
- Compreensão sobre NAT
- Configuração de instâncias EC2 com servidor web via script de inicialização

## ✅ Status
Laboratório concluído com sucesso e validado visualmente via navegador.

## 🧑‍💻 

- Júlia Karla 
- https://www.linkedin.com/in/juliakarla/
- Certificação-alvo: AWS Certified Cloud Practitioner
