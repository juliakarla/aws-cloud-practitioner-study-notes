Este laboratório faz parte do meu estudo para a certificação **AWS Certified Cloud Practitioner**. 

## 📚 Objetivos

- Explorar usuários e grupos do IAM pré-criados
- Inspecionar políticas do IAM atribuídas a grupos
- Adicionar usuários a grupos com permissões específicas
- Usar a URL de login do IAM
- Testar as permissões concedidas a cada usuário

## 🔧 Atividades realizadas

### 🔹 Tarefa 1: Exploração dos usuários e grupos IAM
- Inspecionei os usuários "user-1", "user-2" e "user-3"
- Verifiquei que inicialmente não tinham permissões ou associação a grupos
- Analisei os grupos "EC2-Support", "S3-Support" e "EC2-Admin"

### ➕ Tarefa 2: Adicionar Usuários a Grupos

| Usuário  | Grupo         | Permissões                        |
|----------|---------------|-----------------------------------|
| user-1   | S3-Support    | Somente leitura no Amazon S3      |
| user-2   | EC2-Support   | Somente leitura no Amazon EC2     |
| user-3   | EC2-Admin     | Iniciar, parar e descrever EC2    |

### 🔐 Tarefa 3: Testes de Permissões
- Login individual de cada usuário em modo anônimo.
- Verificação dos acessos permitidos e restritos:
  - "user-1": acesso apenas ao S3.
  - "user-2": visualização de EC2, sem modificar.
  - "user-3": controle total sobre instâncias EC2.

## 🧠 Aprendizados

- Diferença entre políticas gerenciadas e políticas em linha
- Como as permissões são herdadas por meio de grupos
- A prática de login com diferentes perfis reforça o entendimento das políticas aplicadas

## 🏁 Conclusão

Este laboratório ajudou a consolidar os conceitos de usuários, grupos, políticas e permissões dentro do IAM, fundamentais para segurança e governança na AWS.

## 🧑‍💻 

- Júlia Karla 
- https://www.linkedin.com/in/juliakarla/
- Certificação-alvo: AWS Certified Cloud Practitioner
