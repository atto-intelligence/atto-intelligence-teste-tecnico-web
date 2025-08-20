# Teste Técnico Front-end Júnior

## Objetivo
O objetivo deste teste é avaliar as habilidades de um desenvolvedor front-end júnior em:

- Consumo de API pública
- Manipulação de dados JSON
- Uso de **React** com **TypeScript**
- Criação de componentes reutilizáveis
- Aplicação de design moderno e responsivo

O candidato deverá criar uma tela que exiba a previsão do tempo para **Rondonópolis** nos próximos 7 dias.

---

## Requisitos da API

**Endpoint:**
  - [Documentação](https://open-meteo.com/en/docs))  
  - Endpoint sugerido (clima atual):  
    ```http
    GET (https://api.open-meteo.com/v1/forecast?latitude=-16.4708&longitude=-54.6356&daily=temperature_2m_max,temperature_2m_min,weathercode&timezone=America/Cuiaba)
    ```
**O parametro enviado**
```
  - `latitude=-16.4708`
  - `longitude=-54.6356`
  - `daily=temperature_2m_max,temperature_2m_min,weathercode`
  - `timezone=America/Cuiaba`
```
**o retorno da API é assim:**
  ```
  {
  "latitude": -16.5,
  "longitude": -54.625,
  "generationtime_ms": 0.375032424926758,
  "utc_offset_seconds": -14400,
  "timezone": "America/Cuiaba",
  "timezone_abbreviation": "GMT-4",
  "elevation": 229,
  "daily_units": {
    "time": "iso8601",
    "temperature_2m_max": "°C",
    "temperature_2m_min": "°C",
    "weathercode": "wmo code"
  },
  "daily": {
    "time": [
      "2025-08-20",
      "2025-08-21",
      "2025-08-22",
      "2025-08-23",
      "2025-08-24",
      "2025-08-25",
      "2025-08-26"
    ],
    "temperature_2m_max": [37, 37.8, 37.8, 38.3, 26.1, 25.8, 28.1],
    "temperature_2m_min": [19.9, 19.8, 19.9, 17.9, 18.4, 13.9, 12.8],
    "weathercode": [3, 3, 2, 2, 2, 2, 2]
  }
}
  ```

## Desafio

1. Criar uma aplicação em **React + TypeScript**.
2. Consumir a API do Open-Meteo para Rondonópolis:
3. Exibir a previsão de **temperatura máxima e mínima** para os próximos **7 dias**.
4. Cada dia deve ser representado em um **card**, totalizando **7 cards**.
5. Cada card deve mostrar:
   - Data do dia
   - Temperatura máxima
   - Temperatura mínima
6. A tela deve mostrar **14 informações totais** (7 máximas + 7 mínimas) de forma clara e organizada.
7. O design deve ser moderno, limpo e responsivo. Pode usar **CSS**, **Tailwind**, **Material UI** ou outra biblioteca de UI.

---

## Estrutura sugerida

src/
├─ components/
│ ├─ WeatherCard.tsx # Componente que recebe date, tempMax e tempMin e renderiza o card
├─ pages/
│ ├─ Forecast.tsx # Tela principal que consome a API e renderiza os 7 cards
├─ services/
│ ├─ api.ts # Serviço para encapsular a chamada à API
├─ App.tsx
├─ index.tsx
