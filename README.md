# Painel Soneda - Dashboard MongoDB

Dashboard web desenvolvido para substituir analises manuais em planilhas dinamicas de Excel por uma visao centralizada de vendas, estoque e performance comercial do cliente Soneda.

O painel consolida arquivos operacionais, aplica regras de tratamento e disponibiliza indicadores para leitura executiva, filtros dinamicos e acompanhamento por periodo, filial, categoria, familia e produto.

## Objetivo

Automatizar uma rotina que antes dependia de planilhas dinamicas, reduzindo retrabalho e dando acesso rapido aos principais numeros acompanhados pela diretoria comercial.

## Principais recursos

- Importacao de dados brutos de sell out em CSV/XLSX.
- Importacao de tabelas De/Para de lojas e categorias.
- Dashboard com KPIs de vendas, valor vendido, estoque e evolucao diaria.
- Filtros por periodo, filial, categoria, familia e produto.
- Agregacoes otimizadas no MongoDB para consultas mais rapidas.
- Cache controlado no backend para reduzir processamento repetido.
- Area administrativa para usuarios, admins, templates e logs de importacao.
- Redefinicao de senha por e-mail.
- Modo somente leitura para ambientes de demonstracao.

## Tecnologias

- Node.js
- Express
- MongoDB Atlas
- HTML, CSS e JavaScript puro
- Multer para upload de arquivos
- XLSX e csv-parser para leitura de planilhas
- Nodemailer para reset de senha
- Docker para deploy

## Estrutura

```text
backend/src/server.js      API, autenticacao, importacoes e consultas MongoDB
frontend/index.html        Interface principal do dashboard
frontend/reset-senha.html  Fluxo de redefinicao de senha
docs/                      Manuais de uso e manutencao
Dockerfile                 Build da aplicacao
```

## Variaveis de ambiente

Crie um arquivo `.env` local com as variaveis abaixo. O `.env` nao deve ser publicado.

```env
PORT=3000
DB_NAME=soneda_dashboard
MONGODB_URI=mongodb+srv://USUARIO:SENHA@HOST/?appName=Cluster0
ADMIN_USER=usuario-admin
ADMIN_PASSWORD=senha-admin
ADMIN_EMAIL=email@dominio.com
EMAIL_USER=
EMAIL_PASS=
READ_ONLY=false
```

## Como executar

```bash
npm install
npm start
```

A aplicacao sobe o backend Express e serve o frontend estatico.

## Demo estatica

Este repositorio tambem possui uma demo visual em `docs/index.html`, criada para GitHub Pages e portfolio. Ela usa dados ficticios embutidos no proprio HTML, sem depender de MongoDB, backend ou variaveis de ambiente.

## Cuidados de portfolio

Este repositorio foi preparado para portfolio. Bases reais, arquivos `.env`, uploads, CSVs e XLSX operacionais ficam fora do Git por seguranca e confidencialidade.

## Status

Projeto funcional e publicado originalmente em ambiente de producao, com rotinas de importacao, tratamento, consulta e administracao.
