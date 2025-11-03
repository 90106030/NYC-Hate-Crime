# NYC-Hate-Crime
import pandas as pd
url = "https://data.cityofnewyork.us/resource/bqiq-cu78.csv?$limit=1000000"
df = pd.read_csv(url)
