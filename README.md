# PACE-2025 — School Health Screening System

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![Google Sheets API](https://img.shields.io/badge/Google_Sheets_API-34A853?style=flat&logo=google-sheets&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=flat&logo=render&logoColor=black)

Web application developed for the **UFAM School of Dentistry** to digitize patient registration and vital signs collection during school health screenings.

🔗 **Live Demo:** https://pace-2025-rcn7.onrender.com/

## 💡 Context

During health screening events organized by UFAM's School of Dentistry, all patient data was recorded on paper — slowing down appointments and risking loss of research data.

This system digitizes the entire process: dentistry students fill out a form, the app calculates BMI, classifies blood pressure and temperature automatically, and sends everything to a shared Google Sheets spreadsheet via API.

**Results:** used by **6 dentistry students** to register **18 patients**, eliminating paper and making data instantly available for academic analysis.

## 📁 Project Structure

```
pace-2025/
├─ backend/
│  ├─ server.js              # Express server + Google Sheets API integration
│  └─ credentials.json       # Google Service Account (not committed)
│
├─ public/
│  ├─ index.html             # Patient registration form
│  ├─ scripts.js             # BMI, pressure & temperature calculations
│  ├─ styles.css             # UI styling
│  └─ img/                   # Logos and favicon
│
├─ .env                      # Environment variables
├─ .gitignore
├─ package.json
└─ README.md
```

## ⚙️ How It Works

1. Dentistry student fills in patient data (name, age, sex, weight, height, blood pressure, temperature)
2. **"Gerar tabela do paciente"** — runs client-side calculations and displays a color-coded summary with BMI classification, blood pressure stage, and temperature state
3. **"Enviar para Google Sheets"** — backend sends all data (including calculated fields) to a shared spreadsheet via Google Sheets API with Service Account auth
4. Dentistry students and professors access the spreadsheet directly for research analysis.

## 🔧 Why Google Sheets as the Database?

Deliberate choice, not a limitation. The end users (dentistry students and professors) needed to access, filter, and analyze patient data without any technical tools. Google Sheets gave them a familiar interface with zero training required.

## 🔐 Authentication

The system uses a Google Service Account to securely authenticate requests to the Google Sheets API. Credentials are stored locally and accessed through environment variables.

## 📖 References

- [express](https://expressjs.com/)
- [google API](https://developers.google.com/workspace/sheets/api/guides/concepts?hl=pt-br)

## 👨‍💻 Author

**Lucas Nicolau** — Software Engineering Student at [@UFAM](https://www.ufam.edu.br).
