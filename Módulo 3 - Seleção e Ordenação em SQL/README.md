![logo_ebac](https://github.com/user-attachments/assets/1f3b26d6-9a21-4646-ac17-48c506b4de43)

---

# **Módulo 3** | SQL: Seleção e ordenação em SQL

Professora Mariane Neiva <br>
Aluna Cristiane <br>

Data: 01 de Julho de 2025.

---

## Atividades

### **2. Selecionando dados**

```sql
CREATE EXTERNAL TABLE transacoes (
	id_cliente BIGINT,
	id_transacao BIGINT,
	valor FLOAT,
	id_loja STRING
)
ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.OpenCSVSerde'
WITH SERDEPROPERTIES (
	'separatorChar' = ',',
	'quoteChar' = '"',
	'escapeChar' = '\\'
)
STORED AS TEXTFILE
LOCATION 's3://bucket-cristianesantos-transacoes/'
```

#### [**2.1. Query 1**](https://raw.githubusercontent.com/crikactba/SQL/main/Módulo%203%20-%20Seleção%20e%20Ordenação%20em%20SQL/query1.csv)
```sql
SELECT *
FROM transacoes
```

#### [**2.2. Query 2**](https://raw.githubusercontent.com/crikactba/SQL/main/Módulo%203%20-%20Seleção%20e%20Ordenação%20em%20SQL/query2.csv)
```sql
SELECT id_cliente,
	valor,
	id_loja AS nome_loja
FROM transacoes;
```

#### [**2.3. Query 3**](https://raw.githubusercontent.com/crikactba/SQL/main/Módulo%203%20-%20Seleção%20e%20Ordenação%20em%20SQL/query3.csv)
```sql
SELECT DISTINCT id_loja AS nome_loja
FROM transacoes;
```

### **3. Ordenando e limitando dados**

#### [**3.1. Query 4**](https://raw.githubusercontent.com/crikactba/SQL/main/Módulo%203%20-%20Seleção%20e%20Ordenação%20em%20SQL/query4.csv)
```sql
SELECT id_cliente,
	valor
FROM transacoes
ORDER BY valor DESC
LIMIT 2;
```
