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
