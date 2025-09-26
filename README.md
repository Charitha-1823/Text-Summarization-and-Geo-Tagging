#  Text Summarization and Location Extraction Pipeline

This project demonstrates a *text summarization pipeline* combined with *geographical entity recognition* and *geocoding*.  
It takes raw articles as input, generates concise summaries, extracts places mentioned, and maps them to their latitude and longitude.

---

##  Features
- *Abstractive Summarization* using Hugging Face Transformers (BART.)
- *Named Entity Recognition (NER)* with spaCy to extract locations.
- *Geocoding* of identified places using GeoPy (Nominatim).
- *Evaluation Metrics* for summarization quality:
  - ROUGE (Precision, Recall, F1)
  - BERTScore (Semantic similarity)
- *Interactive UI* via Gradio for easy experimentation.
- CSV export of results for further analysis.

---

## Project Workflow
1. *Input*: News articles (CSV file with article and highlights columns).
2. *Preprocessing*: Clean and truncate long texts.
3. *Summarization*: Generate concise summaries with a pre-trained model.
4. *Location Extraction*: Detect geographical names (GPE entities).
5. *Geocoding*: Convert place names to latitude and longitude.
6. *Evaluation*: Compare generated summaries with ground-truth using ROUGE and BERTScore.
7. *Output*: Save results into a clean CSV with:
   - Original text
   - Generated summary
   - Places found
   - Latitude & Longitude

---

##  Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/Charitha-1823/Text-Summarization-and-Geo-Tagging
cd Text-Summarization-and-Geo-Tagging
pip install -r requirements.txt

Run the Pipeline
python summarization_geo_pipeline.py \
  --input /path/to/input.csv \
  --output /path/to/output.csv \
  --sample 500 \
  --model "facebook/bart-large-cnn" \
  --batch-size 2 \
  --max-length 120
