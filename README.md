# African & Public Health Free Public APIs

> A curated, community-oriented collection of **100% free, CORS-enabled, and zero-auth public APIs** for African developers, health informaticians, and data builders.  
> Authored and maintained by **Kabo Merapelo Onamile** ([@sunji-droid](https://github.com/sunji-droid)), Founder of [CadeCodemy](https://sunji-droid.github.io/cadecodemy/).

---

## 💡 Why This Repository Exists

Most public API lists contain thousands of entries, but many are:
1. Blocked by browser **CORS policies** (breaking frontend applications).
2. Locked behind paid credit-card verification paywalls.
3. Focused exclusively on North American and European datasets.

This directory focuses on **zero-friction, browser-accessible APIs** covering **Public Health, Demographics, African Indicators, Currency, and Environmental Telemetry** that students, researchers, and developers can fetch directly from their code with zero configuration.

---

## 📑 Table of Contents

- [Public Health & Disease Surveillance](#public-health--disease-surveillance)
- [Africa, Demographics & Open Governance](#africa-demographics--open-governance)
- [Currency, Trade & Financial Telemetry](#currency-trade--financial-telemetry)
- [Environment, Weather & Cold-Chain Telemetry](#environment-weather--cold-chain-telemetry)
- [How to Fetch Data (Code Examples)](#how-to-fetch-data-code-examples)
  - [JavaScript (Browser Fetch)](#javascript-browser-fetch)
  - [Python (urllib / requests)](#python-urllib--requests)
- [Contributing](#contributing)
- [License](#license)

---

## Public Health & Disease Surveillance

| API | Description | Auth | CORS | Link |
| :--- | :--- | :---: | :---: | :--- |
| **Disease.sh** | Real-time epidemiological metrics on COVID-19, Influenza, and global disease surveillance with WHO/JHU data. | `No` | `Yes` | [Website](https://disease.sh/) |
| **WHO Global Health Observatory** | World Health Organization indicator database covering mortality, health systems, and infectious diseases across African member states. | `No` | `Yes` | [Website](https://www.who.int/data/gho/info/gho-odata-api) |
| **OpenFDA Drug & Adverse Events** | Public database on medication clinical trials, adverse drug events, and pharmacological recalls. | `No` | `Yes` | [Website](https://open.fda.gov/apis/) |
| **ClinicalTrials.gov API** | National Library of Medicine database of privately and publicly funded clinical studies worldwide. | `No` | `Yes` | [Website](https://clinicaltrials.gov/data-api/api) |

---

## Africa, Demographics & Open Governance

| API | Description | Auth | CORS | Link |
| :--- | :--- | :---: | :---: | :--- |
| **REST Countries** | Comprehensive geographical, currency, language, border, and regional demographic data covering all 54 African nations. | `No` | `Yes` | [Website](https://restcountries.com/) |
| **World Bank Indicators API** | Macroeconomic, poverty, literacy, child mortality, and electrification metrics with specific country codes (`BWA`, `ZAF`, `NAM`, `ZWE`). | `No` | `Yes` | [Website](https://datahelpdesk.worldbank.org/knowledgebase/topics/125510-developer-information) |
| **HDX (Humanitarian Data Exchange)** | UN OCHA platform providing crisis, malnutrition, and displacement indicators across Sub-Saharan Africa. | `No` | `Yes` | [Website](https://data.humdata.org/) |
| **UNESCO UIS Data** | Education statistics, primary school completion rates, and literacy datasets across African educational systems. | `No` | `Yes` | [Website](https://apiportal.uis.unesco.org/) |

---

## Currency, Trade & Financial Telemetry

| API | Description | Auth | CORS | Link |
| :--- | :--- | :---: | :---: | :--- |
| **ExchangeRate-API** | Real-time and historical foreign exchange rates supporting Botswana Pula (`BWP`), South African Rand (`ZAR`), and African central bank currencies. | `No` | `Yes` | [Website](https://open.er-api.com/v6/latest/BWP) |
| **Frankfurter** | Track currency exchange rates and historical trends published by the European Central Bank without API keys. | `No` | `Yes` | [Website](https://www.frankfurter.app/) |
| **CoinGecko Free API** | Global cryptocurrency market capitalization, exchange volume, and decentralized asset quotes. | `No` | `Yes` | [Website](https://www.coingecko.com/api) |

---

## Environment, Weather & Cold-Chain Telemetry

| API | Description | Auth | CORS | Link |
| :--- | :--- | :---: | :---: | :--- |
| **Open-Meteo** | High-resolution global weather forecast, solar radiation, historical temperatures, and atmospheric pressure without API keys. Ideal for cold-chain modeling. | `No` | `Yes` | [Website](https://open-meteo.com/) |
| **USGS Earthquake Hazards** | Real-time seismic activity, tremor magnitude, and tectonic fault event feeds from the US Geological Survey. | `No` | `Yes` | [Website](https://earthquake.usgs.gov/fdsnws/event/1/) |
| **OpenAQ Air Quality** | Aggregated particulate matter (PM2.5, PM10) and atmospheric emissions monitoring across global air quality sensors. | `apiKey` | `Yes` | [Website](https://openaq.org/) |

---

## 💻 How to Fetch Data (Code Examples)

### JavaScript (Browser Fetch)
Fetch Botswana's national demographics and currency info:

```javascript
async function getBotswanaData() {
  try {
    const response = await fetch('https://restcountries.com/v3.1/name/botswana');
    const [botswana] = await response.json();
    
    console.log(`Country: ${botswana.name.common}`);
    console.log(`Capital: ${botswana.capital[0]}`);
    console.log(`Population: ${botswana.population.toLocaleString()}`);
    console.log(`Currency: ${Object.keys(botswana.currencies)[0]}`);
  } catch (error) {
    console.error('Error fetching country data:', error);
  }
}

getBotswanaData();
```

---

### Python (urllib / requests)
Fetch real-time Botswana Pula (BWP) exchange rates:

```python
import urllib.request
import json

url = "https://open.er-api.com/v6/latest/BWP"

req = urllib.request.Request(url, headers={"User-Agent": "CadeCodemy-Data-Lab"})
with urllib.request.urlopen(req) as resp:
    data = json.loads(resp.read().decode("utf-8"))
    usd_rate = data["rates"]["USD"]
    zar_rate = data["rates"]["ZAR"]
    print(f"1 BWP = ${usd_rate:.4f} USD")
    print(f"1 BWP = R{zar_rate:.4f} ZAR")
```

---

## 🤝 Contributing

Contributions are welcome! If you know of a free, reliable, and CORS-friendly API relevant to African builders or health informatics:
1. Fork the repo.
2. Add your entry in alphabetical order to the relevant table.
3. Submit a Pull Request.

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for details.  
Built for the African developer and health informatics community by **Kabo Merapelo Onamile**.
