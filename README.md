import requests

def fetch_openfda_data(drug):
    url = f"https://api.fda.gov/drug/event.json?search=patient.drug.medicinalproduct:{drug}&limit=5"
    try:
        res = requests.get(url)
        return res.json()
    except:
        return {}

def fetch_europe_pmc(query):
    url = f"https://www.ebi.ac.uk/europepmc/webservices/rest/search?query={query}&format=json&pageSize=5"
    try:
        res = requests.get(url)
        return res.json()
    except:
        return {}
