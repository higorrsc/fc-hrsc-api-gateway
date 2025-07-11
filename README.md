# Repositório de Estudos sobre o Ambiente Kong API Gateway

Este repositório é dedicado à documentação e aos estudos sobre o Kong API Gateway, uma poderosa ferramenta de gerenciamento de APIs, de código aberto e nativa da nuvem. O objetivo é centralizar conhecimentos, configurações, exemplos práticos e tutoriais que possam auxiliar no entendimento e na utilização do Kong em diversos cenários.

## 🎯 Sobre o Kong API Gateway

O Kong API Gateway é um gateway de API leve, rápido e flexível, projetado para gerenciar, proteger e orquestrar APIs e microsserviços. Atuando como um proxy reverso, ele se posiciona em frente a qualquer API RESTful e pode ser estendido por meio de um rico ecossistema de plugins.

**Principais Funcionalidades:**

* **Roteamento Avançado e Balanceamento de Carga:** Direciona o tráfego para os serviços de backend apropriados e distribui as requisições para garantir alta disponibilidade e desempenho.
* **Segurança e Autenticação:** Oferece suporte a diversos mecanismos de autenticação, como JWT, OAuth 2.0, Basic Auth, Key Auth e ACLs, para proteger suas APIs.
* **Limitação de Taxa (Rate Limiting):** Controla o número de requisições que um consumidor pode fazer em um determinado período, prevenindo abusos e ataques de negação de serviço (DoS).
* **Transformação de Requisições e Respostas:** Modifica cabeçalhos, corpos e parâmetros de requisições e respostas em tempo de execução.
* **Logging e Monitoramento:** Integra-se com ferramentas de observabilidade como Prometheus e Grafana, permitindo um acompanhamento detalhado do tráfego da API.
* **Arquitetura Extensível com Plugins:** A funcionalidade do Kong pode ser facilmente estendida através de plugins, que podem ser configurados para atender a necessidades específicas de negócios e arquitetura.
* **Suporte a Diversas Arquiteturas:** Ideal para ambientes de microsserviços, implantações híbridas (hybrid-cloud) e multi-cloud, com suporte nativo para Kubernetes através do Kong Ingress Controller.

---

## 🚀 Começando

Para iniciar os estudos e testes práticos com o Kong, recomenda-se a utilização de Docker e Docker Compose para uma configuração rápida e isolada.

### Pré-requisitos

* [Docker](https://docs.docker.com/get-docker/)
* [Docker Compose](https://docs.docker.com/compose/install/)

### Instalação com Docker Compose

1. **Clone este repositório:**

    ```bash
    git clone https://github.com/higorrsc/fc-hrsc-api-gateway.git 
    cd fc-hrsc-api-gateway
    ```

2. **Inicie o ambiente:**

    O arquivo de configuração do Docker Compose está localizado em `compose/compose.yaml`. Para subir todos os serviços definidos nele, execute o seguinte comando a partir da raiz do repositório:

    ```bash
    docker-compose -f compose/compose.yaml up -d
    ```

3. **Verifique a instalação:**

    Após alguns instantes, você pode verificar se o Kong está em execução fazendo uma requisição para a Admin API:

    ```bash
    curl -i http://localhost:8001/
    ```

    Você deverá receber uma resposta `HTTP/1.1 200 OK` com informações sobre a versão do Kong.

---

## 📂 Estrutura do Repositório

Este repositório está organizado da seguinte forma para suportar um ambiente de estudos completo:

* `LICENSE`: O arquivo de licença do projeto (MIT License).
* `README.md`: Este arquivo de documentação.
* `compose/`: Diretório que contém toda a configuração do ambiente Docker Compose.
  * `compose.yaml`: O arquivo principal do Docker Compose que define e orquestra os serviços (Kong, Prometheus, Fluent Bit, etc.).
  * `fluent-bit/`: Contém os arquivos de configuração para o serviço de logging **Fluent Bit**.
  * `prom-conf/`: Contém o arquivo de configuração (`prometheus.yaml`) para o serviço de monitoramento **Prometheus**.
* `docker/`: Contém definições de imagens Docker customizadas.
  * `Dockerfile`: Arquivo utilizado para construir uma imagem Docker específica para algum serviço do ambiente.

---

## 📚 Tópicos Chave de Estudo

A seguir, uma lista dos principais conceitos e funcionalidades do Kong que podem ser explorados com este ambiente:

* **Core Concepts:**
  * Services
  * Routes
  * Consumers
  * Upstreams
  * Targets
* **Plugins Essenciais:**
  * **Autenticação:** Key Auth, Basic Auth, HMAC, JWT, OAuth 2.0
  * **Segurança:** ACL, CORS, IP Restriction, Bot Detection
  * **Controle de Tráfego:** Rate Limiting, Request Size Limiting, Canary Release
  * **Análise e Monitoramento:** Prometheus, Zipkin, Datadog
  * **Transformação:** Request Transformer, Response Transformer
  * **Logging:** TCP Log, UDP Log, HTTP Log, File Log
* **Tópicos Avançados:**
  * DB-less e Declarative Configuration
  * Kong Ingress Controller para Kubernetes
  * Desenvolvimento de Plugins Customizados em Lua
  * Estratégias de Alta Disponibilidade e Escalabilidade

---

## 🤝 Como Contribuir

Contribuições são sempre bem-vindas! Se você deseja adicionar novos exemplos, melhorar a documentação ou corrigir algum problema, sinta-se à vontade para:

1. Fazer um "fork" deste repositório.
2. Criar uma nova "branch" para a sua feature (`git checkout -b feature/nova-feature`).
3. Fazer o "commit" das suas alterações (`git commit -m 'Adiciona nova feature'`).
4. Fazer o "push" para a sua branch (`git push origin feature/nova-feature`).
5. Abrir um "Pull Request".

---

## 📄 Licença

Este projeto é distribuído sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
