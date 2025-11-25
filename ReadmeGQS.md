# 💰 Calculadora de Renda Fixa 
 
![Nuxt](https://img.shields.io/badge/Nuxt-4.2-00DC82?logo=nuxt.js&style=flat-square) 
![Vue](https://img.shields.io/badge/Vue.js-3.5-4FC08D?logo=vue.js&style=flat-square) 
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-4.0-38B2AC?logo=tailwind-css&style=flat-square) 
![Vitest](https://img.shields.io/badge/Vitest-Passed-729B1B?logo=vitest&style=flat-square) 
 
Uma aplicação web moderna para simulação e comparação de investimentos em Renda Fixa, utilizando dados reais do Banco Central do Brasil. Desenvolvida como parte da Avaliação A3 da disciplina de **Gestão e Qualidade de Software**. 
 
🔗 **Acesse o projeto online:** [https://rendafixa.github.io](https://rendafixa.github.io) 
 
--- 
 
## 🎯 Objetivo do Projeto 
 
Facilitar a vida do investidor brasileiro, oferecendo uma ferramenta transparente que calcula a rentabilidade real de investimentos (descontando IR e IOF automaticamente), comparando: 
* **Poupança** (com regras de aniversário antiga/nova). 
* **CDB / RDB / LC** (Títulos tributáveis). 
* **LCI / LCA** (Títulos isentos). 
 
## 🚀 Tecnologias Utilizadas 
 
O projeto foi construído sobre uma stack moderna, garantindo performance e manutenibilidade: 
 
* **[Nuxt 4](https://nuxt.com/)** (Compatibility Version): Framework Vue híbrido para renderização e otimização. 
* **[Vue.js 3](https://vuejs.org/)**: Componentização e reatividade. 
* **[Tailwind CSS 4](https://tailwindcss.com/)**: Estilização utilitária e design responsivo. 
* **[Pinia](https://pinia.vuejs.org/)**: Gerenciamento de estado global. 
* **[Vitest](https://vitest.dev/)**: Framework de testes unitários. 
* **[Axios](https://axios-http.com/)**: Cliente HTTP para consumo de APIs. 
 
--- 
 
## ✅ Garantia de Qualidade (QA) 
 
A confiabilidade dos cálculos é o pilar deste projeto. Implementamos uma estratégia de testes automatizados cobrindo: 
 
### 1. Testes Unitários (Lógica de Negócio) 
Validam a matemática financeira crítica, garantindo que o dinheiro do usuário seja calculado corretamente. 
* **Cálculo de Juros Compostos:** Validação da fórmula exponencial. 
* **Tabela Regressiva de IR:** Testes de valor limite (ex: 180 dias vs 181 dias). 
* **Tabela de IOF:** Validação da incidência regressiva nos primeiros 30 dias. 
 
### 2. Testes de Componentes (Interface) 
Validam a entrada de dados e o feedback visual ao usuário. 
* **Inputs:** Garantia de que valores negativos ou inválidos são bloqueados. 
* **Acessibilidade:** Verificação de labels e mensagens de erro claras. 
 
### Para rodar os testes: 
```bash 
pnpm test 
 
 
⚙️ Automação de Dados (Data Fetching) 
O projeto conta com um script dedicado (update-indexes.js) que busca os indicadores financeiros mais recentes diretamente das APIs governamentais: 
API do Banco Central (SGS): Para obter a taxa da Poupança e o histórico do CDI. 
API do Site BCB: Para obter a Meta Selic atual. 
Isso garante que a calculadora esteja sempre utilizando as taxas de mercado vigentes. 
 
🛠️ Instalação e Execução Local 
Certifique-se de ter o Node.js instalado. 
Clone o repositório: 
Bash 
git clone [https://github.com/SEU_USUARIO/a3-calculadora-rendafixa.git](https://github.com/SEU_USUARIO/a3-calculadora-rendafixa.git) 
cd a3-calculadora-rendafixa 
 
Instale as dependências: 
Bash 
pnpm install 
# ou npm install 
 
Atualize os índices financeiros (Opcional): 
Bash 
pnpm update-indexes 
 
Rode o servidor de desenvolvimento: 
Bash 
pnpm dev 
 
Acesse http://localhost:3000 no seu navegador. 
 
👥 Autores 
Projeto desenvolvido pelos alunos de Ciência da Computação / Engenharia de Software: 
Argel dos Santos 
Bernardo Gomes 
Cauã Durante 
Renato Nagahama 
