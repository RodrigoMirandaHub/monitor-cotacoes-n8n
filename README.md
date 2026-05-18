# 📈 Monitor de Cotações com Alertas — N8N

<img width="1668" height="879" alt="Screenshot_3" src="https://github.com/user-attachments/assets/34a9193a-14d2-423f-8002-6e4c3258899c" />

Automação completa que monitora cotações de USD e BTC em tempo real, registra histórico e envia alertas por e-mail quando os valores ultrapassam limites definidos.

## 🚀 O que faz

- Busca cotações de USD e BTC a cada 30 minutos via API
- Grava histórico automático no Google Sheets
- Envia alerta por e-mail personalizado quando o valor ultrapassa o limite configurado

## 🛠️ Tecnologias

- **N8N** — orquestração do fluxo de automação
- **AwesomeAPI** — dados de cotação em tempo real (sem autenticação)
- **Google Sheets** — armazenamento do histórico
- **Gmail** — envio de alertas

## 🔁 Arquitetura do Fluxo

Schedule Trigger (30min)
→ HTTP Request (AwesomeAPI)
→ Code (transforma e define limites por moeda)
→ IF (verifica se ultrapassou o limite)
→ [true] Google Sheets + Gmail Alert
→ [false] sem ação

## ⚙️ Configuração

<img width="611" height="568" alt="Screenshot_4" src="https://github.com/user-attachments/assets/53a40cfe-58aa-44c0-a2a1-e0c157ca01cd" />
1. Importe o workflow no N8N
2. Configure as credenciais do Google Sheets e Gmail
3. Ajuste os limites no nó **Code**:
   - `limite: 5.10` para USD
   - `limite: 410000` para BTC
4. Ative o workflow

## 📊 Exemplo de Alerta

**Assunto:** 🚀 Bitcoin rompeu R$ 411.500  
**Corpo:** Valor atual, máxima do dia e data/hora

## 👤 Autor

Rodrigo Miranda — [LinkedIn](www.linkedin.com/in/rodrigo-h-miranda) | [GitHub](https://github.com/RodrigoMirandaHub)

