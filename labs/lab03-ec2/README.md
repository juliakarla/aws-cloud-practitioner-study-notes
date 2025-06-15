---

## 🎯 Objetivos

* Lançar e configurar uma instância Amazon EC2.
* Automatizar a instalação de um servidor web usando **User Data**.
* Configurar e gerenciar **Security Groups** como um firewall virtual.
* Redimensionar uma instância EC2 e seus volumes do EBS.
* Compreender e testar as proteções contra encerramento e interrupção.
* Explorar os **Service Quotas** do EC2.

---

## 🛠️ Recursos Criados na AWS

* **Instância EC2:** "Web Server": inicialmente "t2.micro", redimensionada para "t2.small".
* **Volume EBS:** Volume raiz de 8 GiB redimensionado para 10 GiB.
* **Security Group:** "Web Server security group": regra para tráfego HTTP na porta 80.
* **Par de Chaves:** "vockey" (utilizado para a criação da instância).

---

## 🧠 Aprendizados Chave

* A **automação** de tarefas de configuração inicial em instâncias EC2 através de scripts de **User Data**.
* O papel fundamental dos **Security Groups** como **firewalls stateful**, controlando o tráfego de rede para e de instâncias EC2.
* A importância das **proteções contra encerramento e interrupção** para prevenir desligamentos ou exclusões acidentais de instâncias.
* O processo flexível de **redimensionamento de instâncias** e volumes EBS, permitindo ajustar os recursos conforme as demandas da aplicação.
* A utilização de ferramentas de **monitoramento** do EC2 (Status Checks, CloudWatch Metrics, System Log e Instance Screenshots) para diagnóstico e solução de problemas.
* A existência e relevância dos **Service Quotas** da AWS para o gerenciamento de limites de recursos por região.

---

## 🔧 Atividades Realizadas

1.  **Lançamento da Instância EC2:**
    * Criação da instância "Web Server" na região "us-east-1" (Norte da Virgínia).
    * Configuração com AMI Amazon Linux 2023, tipo "t2.micro" e ativação da proteção contra encerramento.
    * Injeção de um script bash via **User Data** para instalar e iniciar o servidor web Apache e criar uma página HTML simples.
    * Criação de um Security Group inicial sem regras de entrada.
2.  **Monitoramento da Instância:**
    * Verificação do estado e status da instância.
    * Análise de métricas do CloudWatch e do log do sistema.
    * Geração de uma captura de tela da instância.
3.  **Atualização do Security Group e Acesso ao Servidor Web:**
    * Tentativa inicial de acesso ao servidor web (falhou devido ao Security Group).
    * Modificação do "Web Server security group" para permitir tráfego HTTP (porta 80) de qualquer IP ("Anywhere-IPv4").
    * Acesso bem-sucedido à página web "Hello From Your Web Server!".
4.  **Redimensionamento da Instância:**
    * Interrupção da instância "Web Server".
    * Alteração do tipo de instância de "t2.micro" para "t2.small".
    * Ativação da proteção contra interrupção (diferente da proteção contra encerramento).
    * Modificação do tamanho do volume EBS de 8 GiB para 10 GiB.
    * Início da instância redimensionada.
5.  **Exploração de Service Quotas:**
    * Navegação no console de Service Quotas para entender os limites de instâncias EC2 por região.
6.  **Teste da Proteção contra Interrupção:**
    * Tentativa de interromper a instância com a proteção ativa (ação bloqueada).
    * Desativação da proteção contra interrupção.
    * Interrupção bem-sucedida da instância.

---

## 🏁 Conclusão

Este laboratório reforçou minha compreensão sobre EC2 e suas funcionalidades essenciais.

---

🧑‍💻
Júlia Karla
https://www.linkedin.com/in/juliakarla/
Certificação-alvo: AWS Certified Cloud Practitioner
