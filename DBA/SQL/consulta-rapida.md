# SQL - Consulta Rápida

## Comandos Essenciais

### Consulta de Dados
| Comando | Descrição | Exemplo |
|---------|-----------|---------|
| **SELECT** | Seleciona dados do banco | `SELECT * FROM tabela` |
| **AS** | Renomeia coluna/tabela | `SELECT nome AS cliente` |
| **FROM** | Especifica a tabela origem | `FROM produtos` |
| **WHERE** | Filtra resultados | `WHERE preço > 100` |
| **LIMIT** | Limita resultados | `LIMIT 10` |

### Modificação de Dados
| Comando | Descrição | Exemplo |
|---------|-----------|---------|
| **INSERT** | Adiciona dados | `INSERT INTO tabela VALUES (...)` |
| **UPDATE** | Atualiza dados | `UPDATE tabela SET coluna=valor` |
| **DELETE** | Remove dados | `DELETE FROM tabela WHERE id=1` |

### Estrutura do Banco
| Comando | Descrição | Exemplo |
|---------|-----------|---------|
| **CREATE** | Cria objetos | `CREATE TABLE clientes (...)` |
| **ALTER** | Modifica tabelas | `ALTER TABLE ADD coluna` |
| **DROP** | Remove objetos | `DROP TABLE temporaria` |

## Cláusulas JOIN (Junções)

| Tipo | Descrição | Sintaxe |
|------|-----------|---------|
| **INNER JOIN** | Apenas registros correspondentes | `FROM A INNER JOIN B ON A.id=B.id` |
| **LEFT JOIN** | Todos da esquerda + correspondentes | `FROM A LEFT JOIN B ON...` |
| **RIGHT JOIN** | Todos da direita + correspondentes | `FROM A RIGHT JOIN B ON...` |
| **FULL JOIN** | Todos registros de ambas tabelas | `FROM A FULL JOIN B ON...` |

## Funções de Agregação

| Função | Descrição | Exemplo |
|--------|-----------|---------|
| **COUNT()** | Conta registros | `SELECT COUNT(*)` |
| **SUM()** | Soma valores | `SELECT SUM(valor)` |
| **AVG()** | Calcula média | `SELECT AVG(nota)` |
| **MIN()/MAX()** | Valor mínimo/máximo | `SELECT MAX(data)` |

## Operadores Condicionais

| Operador | Descrição | Exemplo |
|----------|-----------|---------|
| **AND** | Todas condições verdadeiras | `WHERE idade > 18 AND saldo > 0` |
| **OR** | Pelo menos uma condição | `WHERE status='ativo' OR vip=1` |
| **IN** | Lista de valores possíveis | `WHERE id IN (1,5,7)` |
| **LIKE** | Busca por padrão | `WHERE nome LIKE 'Jo%'` |
| **IS NULL** | Verifica valores nulos | `WHERE email IS NULL` |

## Operadores de Comparação

**Operador**	| **Descrição**
> ``=``	➔ Igual
``<> ou !=``	➔ Diferente
``>`` ➔ Maior que
`< ` ➔ Menor que
``=``	➔ Maior ou igual
``<=``	➔ Menor ou igual

## Exemplos Práticos

```sql
-- Criar banco de dados
CREATE DATABASE ecommerce;

-- Consulta básica com filtro
SELECT nome, preço FROM produtos
WHERE categoria = 'eletrônicos'
ORDER BY preço DESC
LIMIT 5;

-- Atualização condicional
UPDATE usuarios
SET premium = 1
WHERE cadastro_data < '2023-01-01';

-- Junção de tabelas
SELECT p.nome, c.quantidade
FROM produtos p
INNER JOIN compras c ON p.id = c.produto_id;

