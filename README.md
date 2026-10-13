# Tutorial 3 — Conectando Node.js e Express ao MySQL

Projeto de aula do Senac RJ. Implementa a conexão inicial com MySQL usando Express, `mysql2/promise`, pool de conexões e variáveis de ambiente.

## Requisitos
- Node.js compatível com `--env-file` (Node.js 20.6 ou superior recomendado)
- Docker Desktop

## 1. Configure o ambiente
Copie `.env.example` para `.env` e configure as credenciais do seu MySQL.

No PowerShell:
```powershell
Copy-Item .env.example .env
```

Para o `docker-compose.yml` deste projeto, configure no `.env`:
```env
PORT=3000
DB_HOST=localhost
DB_PORT=3306
DB_USER=api_user
DB_PASSWORD=api123
DB_NAME=api_rest
```

## 2. Inicie o MySQL
```powershell
docker compose up -d
docker ps
```

## 3. Instale e execute a API
```powershell
npm.cmd install
npm.cmd run dev
```

Saída esperada:
```text
Conexão com o MySQL estabelecida
Servidor rodando em http://localhost:3000
```

## 4. Teste
Abra http://localhost:3000. Resposta:
```json
{
  "mensagem": "API REST funcionando"
}
```

Se a conexão falhar, confirme que o container está em execução e que as credenciais no `.env` correspondem às usadas pelo MySQL. Não publique o arquivo `.env` no GitHub.

## Estrutura
```text
src/
├── database/
│   └── pool.js
├── app.js
└── server.js
```
