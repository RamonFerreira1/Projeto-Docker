# 🚀 Microsserviços com Docker: Projeto Toshiro Shibakita

Este projeto consiste na implementação de uma arquitetura de microsserviços escalável e de alta disponibilidade, inspirada no estudo de caso "Toshiro Shibakita". A aplicação demonstra como separar responsabilidades entre banco de dados, lógica de aplicação e balanceamento de carga utilizando contêineres Docker.

## 🛠️ Tecnologias Utilizadas

* **Docker & Docker Compose**: Orquestração de contêineres e definição de infraestrutura como código.
* **Nginx**: Atuando como Proxy Reverso e Balanceador de Carga (Load Balancer).
* **PHP 7.4**: Camada de aplicação para processamento de lógica e conexão com banco de dados.
* **MySQL 5.7**: Persistência de dados em rede isolada.
* **WSL 2**: Subsistema Linux para execução eficiente do motor Docker no Windows.

## 🏗️ Arquitetura do Sistema

A solução foi desenhada para garantir que cada componente funcione de forma independente, seguindo os princípios de microsserviços:

1. **Nginx (Porta 4500)**: Recebe todas as requisições externas e as distribui para o cluster de instâncias PHP.
2. **PHP App**: Processa a requisição, gera dados aleatórios e registra o nome do host (container ID) que realizou a operação.
3. **MySQL**: Armazena os registros em um volume persistente, garantindo que os dados não sejam perdidos ao reiniciar os contêineres.

## 📈 Conceitos de DevOps Aplicados

* **Alta Disponibilidade**: Se um container de aplicação falhar, o Load Balancer redireciona o tráfego para os demais nós ativos.
* **Escalabilidade Horizontal**: O serviço PHP pode ser escalado instantaneamente com o comando `docker compose up -d --scale php-app=3`.
* **Isolamento de Rede**: Utilização de uma rede bridge customizada (`toshiro-net`) para segurança entre os serviços.

---

**Desenvolvido por Ramon Ferreira** *Estudante de Ciência da Computação | Especialista em Suporte de TI & DevOps*

---
