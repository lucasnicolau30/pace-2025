# PACE-2025 — Sistema de Triagem de Saúde Escolar

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![Google Sheets API](https://img.shields.io/badge/Google_Sheets_API-34A853?style=flat&logo=google-sheets&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=flat&logo=render&logoColor=black)

Leia em: [Português](README.pt-br.md) | [English](README.md)

Aplicação web desenvolvida para a **Faculdade de Odontologia da UFAM** para digitalizar o cadastro de pacientes e a coleta de sinais vitais durante triagens de saúde escolar.

**Demo ao vivo:** https://pace-2025-rcn7.onrender.com/

## Contexto

Durante os eventos de triagem de saúde organizados pela Faculdade de Odontologia da UFAM, todos os dados dos pacientes eram registrados em papel — o que tornava os atendimentos mais lentos e trazia risco de perda de dados de pesquisa.

Este sistema digitaliza todo o processo: os estudantes de odontologia preenchem um formulário, o app calcula o IMC, classifica a pressão arterial e a temperatura automaticamente, e envia tudo para uma planilha compartilhada do Google Sheets via API.

**Resultados:** utilizado por **6 estudantes de odontologia** para cadastrar **18 pacientes**, eliminando o papel e disponibilizando os dados instantaneamente para análise acadêmica.

## Estrutura do Projeto

```
pace-2025/
├─ backend/
│  ├─ server.js              # Servidor Express + integração com Google Sheets API
│  └─ credentials.json       # Conta de serviço do Google (não versionado)
│
├─ public/
│  ├─ index.html             # Formulário de cadastro de pacientes
│  ├─ scripts.js             # Cálculos de IMC, pressão e temperatura
│  ├─ styles.css             # Estilização da interface
│  └─ img/                   # Logos e favicon
│
├─ .env                      # Variáveis de ambiente
├─ .gitignore
├─ package.json
└─ README.md
```

## Como Funciona

1. O estudante de odontologia preenche os dados do paciente (nome, idade, sexo, peso, altura, pressão arterial, temperatura)
2. **"Gerar tabela do paciente"** — executa os cálculos no lado do cliente e exibe um resumo colorido com a classificação do IMC, o estágio da pressão arterial e o estado da temperatura
3. **"Enviar para Google Sheets"** — o backend envia todos os dados (incluindo os campos calculados) para uma planilha compartilhada via Google Sheets API, autenticado com uma conta de serviço
4. Estudantes e professores de odontologia acessam a planilha diretamente para análise em pesquisas.

## Por Que Google Sheets Como Banco de Dados?

Escolha deliberada, não uma limitação. Os usuários finais (estudantes e professores de odontologia) precisavam acessar, filtrar e analisar os dados dos pacientes sem nenhuma ferramenta técnica. O Google Sheets ofereceu uma interface familiar, sem necessidade de treinamento.

## Autenticação

O sistema usa uma Conta de Serviço do Google para autenticar com segurança as requisições à API do Google Sheets. As credenciais são armazenadas localmente e acessadas por meio de variáveis de ambiente.

## Referências

- [express](https://expressjs.com/)
- [google API](https://developers.google.com/workspace/sheets/api/guides/concepts?hl=pt-br)

## Autor

**Lucas Nicolau** — Estudante de Engenharia de Software na @UFAM
