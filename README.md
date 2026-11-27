# Baozi Store - API REST

API REST para controle de clientes, produtos e pedidos da Baozi Store (pãozinho chinês).

**Tecnologias:** Java 17, Spring Boot, Spring Data JPA, H2 (banco em memória), Maven.

## Como rodar

```
mvn spring-boot:run
```

A API sobe em `http://localhost:8080`. O console do banco fica em `http://localhost:8080/h2-console`
(JDBC URL: `jdbc:h2:mem:baozidb`, usuário `sa`, senha vazia).

## Endpoints

| Método | Rota | Descrição |
|---|---|---|
| POST | `/clientes` | Criar cliente |
| GET | `/clientes` | Listar clientes |
| GET | `/clientes/{id}` | Consultar cliente por ID |
| DELETE | `/clientes/{id}` | Apagar cliente |
| POST | `/produtos` | Criar produto |
| GET | `/produtos` | Listar produtos |
| GET | `/produtos/{id}` | Consultar produto por ID |
| DELETE | `/produtos/{id}` | Apagar produto |
| POST | `/pedidos` | Criar pedido |
| GET | `/pedidos` | Listar pedidos |
| GET | `/pedidos/{id}` | Consultar pedido por ID |
| DELETE | `/pedidos/{id}` | Apagar pedido |

## Exemplos de JSON

Cliente:
```json
{ "nome": "Felipe5173937", "clienteDesde": "2026-11-27" }
```

Produto:
```json
{ "nome": "Baozi de carne", "preco": 8.50, "estoque": true }
```

Pedido (use os IDs retornados nos POSTs anteriores):
```json
{ "clienteId": 1, "produtoId": 1, "quantidade": 3 }
```
