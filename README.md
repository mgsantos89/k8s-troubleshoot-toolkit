# k8s-troubleshoot-toolkit

**k8s-troubleshoot-toolkit** é uma coleção de exemplos de deploys, scripts e ferramentas para facilitar testes e troubleshooting em ambientes Kubernetes. O objetivo deste repositório é servir como uma caixa de ferramentas para desenvolvedores e operadores que precisam validar funcionalidades, solucionar problemas e realizar experimentos de conectividade, desempenho e configuração no Kubernetes.

## Índice

- [Recursos Disponíveis](#recursos-disponíveis)
- [Pré-requisitos](#pré-requisitos)
- [Como Usar](#como-usar)
- [Estrutura do Repositório](#estrutura-do-repositório)
- [Contribuições](#contribuições)
- [Autoria](#autoria)

## Recursos Disponíveis

Este repositório oferece exemplos de deploys e testes prontos para serem usados em diferentes cenários comuns de troubleshooting e validação, incluindo:

1. **Conexão com Banco de Dados**:
   - Deploy de um Pod simples para testar a conectividade com bancos de dados, como MySQL e PostgreSQL.
   
2. **Aplicação Web**:
   - Deploy de um Pod para testar configurações de aplicações web, incluindo exemplos básicos de uma aplicação `Hello World` em diferentes stacks (Nginx, Node.js, etc.).

3. **Validação de Configuração do Nginx**:
   - Deploy de um Pod com Nginx configurado para servir conteúdo estático ou para funcionar como proxy reverso, útil para verificar as configurações e a conectividade do Nginx.

4. **Testes de Conectividade Interna**:
   - Ferramentas para validar conectividade entre Pods e serviços, incluindo testes de rede entre namespaces e verificações de políticas de rede.

5. **Ferramentas de Debug**:
   - Pods com ferramentas como `curl`, `ping`, e `nslookup` para ajudar no diagnóstico de problemas de rede e de DNS.

## Pré-requisitos

- Cluster Kubernetes funcional (minikube, EKS, GKE, AKS, etc.)
- `kubectl` configurado para acessar o cluster

## Como Usar

1. Clone o repositório:

   ```bash
   git clone https://github.com/seu-usuario/k8s-troubleshoot-toolkit.git
   cd k8s-troubleshoot-toolkit
   ```

2. Navegue até o diretório do tipo de teste que deseja realizar e aplique o manifesto YAML correspondente. Por exemplo, para testar uma aplicação web:

   ```bash
   kubectl apply -f web-app-test/deployment.yaml
   ```

3. Monitore os recursos e logs para verificar a execução e coletar informações de debug:

   ```bash
   kubectl get pods
   kubectl logs <nome-do-pod>
   ```

4. Remova o teste após a conclusão, se necessário:

   ```bash
   kubectl delete -f caminho/para/o/deployment.yaml
   ```

## Estrutura do Repositório

A estrutura básica do repositório é organizada conforme os diferentes cenários de teste:

```plaintext
k8s-troubleshoot-toolkit/
│
├── db-connection-test/        # Testes de conectividade com bancos de dados
│   ├── mysql-deployment.yaml
│   └── postgres-deployment.yaml
│
├── web-app-test/              # Testes de aplicação web (ex: Nginx, Node.js)
│   ├── nginx-deployment.yaml
│   └── nodejs-deployment.yaml
│
├── nginx-validation/          # Configurações e testes do Nginx
│   ├── default-conf.yaml
│   └── nginx-deployment.yaml
│
└── network-tools/             # Ferramentas de rede para troubleshooting
    ├── debug-pod.yaml
    └── connectivity-test.yaml
```

Cada diretório inclui uma descrição do teste e instruções sobre como aplicá-lo e monitorá-lo.

## Contribuições

Contribuições são bem-vindas! Se você deseja adicionar novos cenários de teste ou melhorar os exemplos atuais, sinta-se à vontade para abrir uma *Pull Request* ou criar uma *Issue* com sugestões.

## Autoria

Este repositório foi criado e é mantido por **Marco Gomes**. Sinta-se à vontade para entrar em contato para sugestões ou colaborações!
