# AI Consumer Feedback Analyser

An interactive **sentiment analysis dashboard** that processes consumer feedback from CSV files and visualizes the results in real time.  
Built with **Streamlit**, **NLTK VADER**, and **Plotly**, and designed to run entirely in **Google Colab** with a public Cloudflare tunnel.

---

## Features
- **CSV Upload & Preview**: Upload any CSV with customer reviews and preview the data.
- **Automatic Sentiment Detection**: Combines VADER sentiment scores with optional star ratings.
- **Interactive Visualizations**: Pie chart, histogram of sentiment scores, top keywords bar chart, and sentiment-specific word clouds.
- **Downloadable Results**: Export processed data with sentiment labels as a CSV.
- **No Local Setup Required**: Everything runs directly in Google Colab.

---

## Tech Stack
- **Python 3** (Google Colab)
- **Streamlit** for the web interface
- **NLTK (VADER)** for sentiment analysis
- **Pandas / Matplotlib / Plotly** for data manipulation & charts
- **WordCloud** for visual keyword clouds
- **Cloudflared** to expose the Streamlit app to the web

---

## Project Structure
- sentiment_analysis.py # Full code
- images/ # Screenshots of sample results
- README.md # Project documentation

---

## Getting Started

You can run the app **directly in Google Colab** — no local installation needed.

### 1️⃣ Open Colab
Open a new Colab notebook and upload `app.py` (or paste the code there).

### 2️⃣ Install Dependencies
```python
!pip install streamlit pandas matplotlib wordcloud plotly seaborn nltk
!apt install cloudflared
import nltk
nltk.download('vader_lexicon')
nltk.download('stopwords')

!streamlit run app.py &
!wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64 -O cloudflared
!chmod +x cloudflared
!./cloudflared tunnel --url http://localhost:8501
