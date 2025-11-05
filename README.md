import pandas as pd
import matplotlib.pyplot as plt

# Load NYPD Hate Crime dataset
url = "https://data.cityofnewyork.us/resource/bqiq-cu78.csv?$limit=1000000"
df = pd.read_csv(url)

# Basic preview
print("Data shape:", df.shape)
print(df.head())

# Drop missing values
df = df.dropna(subset=["Borough", "Bias Motivation", "Occurrence Year"])

# Top 10 bias motivations
bias_counts = df["Bias Motivation"].value_counts().head(10)
bias_counts.plot(kind="bar", figsize=(10,6), color="steelblue")
plt.title("Top 10 Bias Motivations in NYC Hate Crimes")
plt.ylabel("Number of Incidents")
plt.tight_layout()
plt.savefig("top_bias_motivations.png")
plt.show()
