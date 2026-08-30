# Electricity Production and Consumption Balance in Finland (Data & ETL)

This thesis analyzes the balance between electricity production and consumption in Finland using Fingrid's open data. The analysis focuses on the net load, which represents the difference between consumption and domestic production, directly indicating the need for electricity imports or exports.

Long-term trends are examined using moving averages, while distribution and variance are analyzed with boxplots based on hourly averages. The goal of this project is to provide a clear, data-driven overview of the Finnish electricity system's balance and to establish a strong foundation for further analysis, such as clustering.

## Technical Implementation (Data Engineering & Analysis)

This project goes beyond standard data analysis by implementing a complete data extraction and preprocessing pipeline (ETL).

1. **Automated Data Retrieval (Extract):** Data is fetched programmatically from Fingrid's open REST API using the `requests` library. The script successfully handles bulk downloads of paginated data (e.g., 700,000+ rows) and automatically manages API rate limits (such as HTTP 429 Too Many Requests errors).
2. **Data Cleaning and Transformation (Transform):**
   - Localizing timestamps from UTC to the Finnish timezone (Europe/Helsinki) using the Pandas library.
   - Merging (Concatenating) separate datasets based on their timestamps.
   - Identifying missing values (NaN) and filling them using time-based linear interpolation.
3. **Feature Engineering & Visualization:** A 30-day moving average and a new variable (Net Load) are calculated to support Matplotlib visualizations.

## Technologies

- **Language & Environment:** Python, Jupyter Notebook
- **Data Processing:** Pandas
- **APIs:** Requests, dotenv (secure API key management)
- **Visualization:** Matplotlib

## Installation (Local Testing)

1. **Clone the repository:**
   ```bash
   git clone [YOUR-GITHUB-LINK-HERE]
---

# Sähkön tuotannon ja kulutuksen tasapaino Suomessa (Data & ETL)

Tämä opinnäytetyö analysoi Suomen sähkön tuotannon ja kulutuksen tasapainoa Fingridin avoimen datan avulla. Analyysin keskiössä on nettokuorma, joka kuvaa kulutuksen ja kotimaisen tuotannon välistä erotusta ja siten sähkön tuonti- tai vientitarvetta.

Pitkän aikavälin kehitystä tarkastellaan liukuvien keskiarvojen avulla, kun taas jakaumaa ja vaihtelua analysoidaan tuntikeskiarvoihin perustuvilla boxplot-kuvaajilla. Projektin tavoitteena on tuottaa selkeä ja datalähtöinen kuva Suomen sähköjärjestelmän tasapainosta sekä luoda pohja jatkoanalyysille, kuten klusteroinnille.

## Tekninen toteutus (Data Engineering & Analysis)

Projekti ei ole vain data-analyysi, vaan se sisältää kokonaisen datanhaku- ja esikäsittelyputken (ETL).

1. **Automatisoitu datanhaku (Extract):** Data ladataan ohjelmallisesti Fingridin avoimesta REST API -rajapinnasta `requests`-kirjastolla. Koodi osaa käsitellä sivutetun datan massalataukset (esim. 700 000+ riviä) ja hallitsee automaattisesti rajapinnan rajoitukset (kuten HTTP 429 Too Many Requests -virheet).
2. **Datan siivoaminen ja muokkaus (Transform):**
   - Aikaleimojen lokalisointi UTC-ajasta Suomen aikavyöhykkeelle (Europe/Helsinki) Pandas-kirjastolla.
   - Erillisten datasettien yhdistäminen (Concatenation) aikaleimojen perusteella.
   - Puuttuvien arvojen (NaN) tunnistaminen ja täyttäminen aikapohjaisella lineaarisella interpoloinnilla.
3. **Feature Engineering & Visualisointi:** Datalle lasketaan 30 päivän liukuvat keskiarvot sekä uusi muuttuja (Nettokuorma) matplotlib-visualisointeja varten.

## Teknologiat

- **Kieli ja ympäristö:** Python, Jupyter Notebook
- **Datan käsittely:** Pandas
- **Rajapinnat:** Requests, dotenv (API-avainten turvallinen hallinta)
- **Visualisointi:** Matplotlib

## Asennus (Paikallinen testaus)

1. **Kloonaa repositorio:**
   ```bash
   git clone [SINUN-GITHUB-LINKKISI-TÄHÄN]

   ```
