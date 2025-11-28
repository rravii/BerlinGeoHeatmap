# -------------------------------
# Installation:
# install Python 3.10+ on your system, restart system
# Example here: Windows 11


#--------------------------------
Download these files from the link below and add it into datasets
# Ladesäuleninfrastruktur je PLZ (Charging station infrastructure by postcode)
https://www.bundesnetzagentur.de/DE/Fachthemen/ElektrizitaetundGas/E-Mobilitaet/start.html
# Liste der Ladesäulen (xlsx / 8 MB) : List of charging stations
# Liste der Ladesäulen (CSV) (csv / 11 MB) : List of charging stations

# -------------------------------
# Installation:
c:
cd C:\(...)\src
python -m venv .venv
.venv\Scripts\activate.bat
pip install -r requirements.txt
pip install spyder

cd C:\(...)\src

# -------------------------------
# Launch:
c:
cd C:\(...)\src
.venv\Scripts\activate.bat
spyder

# jupyter-notebook


# -------------------------------
# Start Streamlit App:
streamlit run main.py
