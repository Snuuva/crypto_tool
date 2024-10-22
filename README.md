
# Fernet Krypteringsverktyg

Detta projekt innehåller två Python-skript som använder **Fernet** från `cryptography`-biblioteket för att:
- Generera symmetriska nycklar för kryptering och dekryptering.
- Kryptera och dekryptera filer med de genererade nycklarna.

## Förutsättningar

- Python 3.x
- `cryptography`-biblioteket (installera med pip)

## Installation

1. Klona eller ladda ner detta repo.
2. Installera beroenden genom att köra:
   ```bash
   pip install -r requirements.txt
   ```

## Användning

### Kryptera en fil

För att kryptera en fil, använd `crypto_tool.py`:

```bash
python3 crypto_tool.py -e -f <filnamn>
```

Detta skapar två filer:
1. En krypterad fil med tillägget `.crypt`.
2. En nyckelfil med tillägget `.key`.

### Dekryptera en fil

För att dekryptera en krypterad fil:

```bash
python3 crypto_tool.py -d -f <filnamn>.crypt
```

Skriptet kommer att leta efter motsvarande `.key`-fil för att dekryptera filen.

### Generera en nyckel

Skriptet generate_key går även att köras separat för att generera en egen nyckel.

För att generera en ny nyckel och spara den i en `.key`-fil:

```bash
python3 generate_key.py
```

Du kommer att bli tillfrågad om att ange ett namn för nyckelfilen.

## Struktur

- **generate_key.py**: Genererar en nyckel och sparar den till en `.key`-fil.
- **crypto_tool.py**: Krypterar och dekrypterar filer med Fernet-kryptering.
- **requirements.txt**: Specifikation för Python-bibliotek som krävs för projektet.
- **.gitignore**: Ignorerar temporära filer, nyckelfiler och krypterade filer.

## Säkerhet

Var noga med att skydda dina `.key`-filer, eftersom de är nödvändiga för att dekryptera dina filer. Om någon får tillgång till din nyckelfil, kan de också dekryptera dina krypterade filer.
