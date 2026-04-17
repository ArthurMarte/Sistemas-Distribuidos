# CarnaTroca

> Sistema distribuído de escambo de fantasias de carnaval · CCF 355 – UFV Florestal · 2022

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405E?style=flat-square&logo=sqlite&logoColor=white)
![Sockets](https://img.shields.io/badge/Sockets-333?style=flat-square)
![gRPC](https://img.shields.io/badge/gRPC-4285F4?style=flat-square)
![REST](https://img.shields.io/badge/REST-FF6F00?style=flat-square)

---

## Sobre o Projeto

O **CarnaTroca** é um sistema distribuído cliente-servidor que permite o escambo de fantasias de carnaval entre usuários. O projeto foi desenvolvido em 5 etapas progressivas ao longo da disciplina de Sistemas Distribuídos e Paralelos, cada uma implementando o mesmo conjunto de funcionalidades com uma tecnologia de comunicação diferente — evoluindo de Sockets puros até REST com Flask.

---

## Funcionalidades

- Cadastro e autenticação de usuários
- Anunciar fantasias para troca (nome, descrição, tamanho)
- Listar todas as fantasias disponíveis de outros usuários
- Propor trocas entre fantasias por ID
- Visualizar, aceitar ou recusar propostas de troca recebidas
- Persistência em SQLite (tabelas: `user`, `fantasias`, `trocas_pendentes`, `controle_trocas`)
- Servidor multithreaded — suporta múltiplos clientes simultâneos

---

## Etapas do Projeto

| Etapa | Tecnologia | Descrição |
|---|---|---|
| TP1 | — | Especificação: requisitos funcionais, casos de uso e diagrama UML |
| TP2 | — | Arquitetura: modelo Cliente-Servidor, camadas físicas/lógicas, modelos de falha e segurança |
| TP3 | TCP Sockets + Threads | Comunicação via sockets, mensagens em JSON, servidor multithreaded |
| TP4 | gRPC | Reimplementação usando gRPC como middleware de comunicação |
| TP5 | REST + Flask | Reimplementação com Web Service REST usando Flask e biblioteca requests |

---

## Arquitetura

Modelo **Cliente-Servidor** com comunicação por **Invocação Remota**. O servidor recebe requisições do cliente, executa as operações no banco de dados e retorna o resultado. Arquitetura em 3 camadas lógicas: interface (cliente), lógica de negócio (servidor) e persistência (SQLite).

---

## Como executar (TP3 e TP5)

```bash
# instalar dependências (necessário apenas para TP5)
pip install flask flask-restful requests

# terminal 1 — iniciar o servidor
python3 servidor.py

# terminal 2 — iniciar o cliente
python3 cliente.py
```

---

*Autores: Arthur Marciano Pires · Vinícius Júlio Martins Barbosa*  
*Disciplina: Sistemas Distribuídos e Paralelos (CCF 355) · UFV Florestal · 2022*

