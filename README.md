# Mistral-Coder
Mistral Coding Machine!


# https://huggingface.co/spaces/awacke1/MistralCoder 

🐍 Write a Python Streamlit program that shows a thumbs up and thumbs down button for scoring an evaluation. When the user clicks, maintain a saved text file that tracks and shows the number of clicks with a refresh and sorts responses by the number of clicks.

https://huggingface.co/docs/transformers/main/model_doc/mistral

https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.1

```
import streamlit as st
from datetime import datetime

# Load saved data or initialize if not available.
try:
    with open('clicks.txt', 'r') as f:
        response_dict = json.load(f)
except FileNotFoundError:
    response_dict = {}

def save_response():
    # Save current response in JSON format to local file.
    with open('clicks.txt', 'w') as f:
        json.dump(response_dict, f)


if __name__ == '__main__':
    # Set title and layout for app.
    st.title("Thumb's Up!")
    st.set_page_config(
        page_title="Thumb's Up",
        page_icon=":guardsman:", 
        layout="wide"
    )

    # Add images of thumb's up and thumb's down buttons
    st.image(
        'https://cdn.pixabay.com
```

# 📊 Create a Pandas DataFrame and display it using Streamlit. Use emojis to indicate the status of each row (e.g., ✅ for good, ❌ for bad).

```
import pandas as pd
import streamlit as st

df = pd.read_csv('example.csv')

st.write('<style>.table-body tr:hover td {
            background-color: lightgray;
          }.th,.td {
            border: none;
            padding: 8px;
            text-align: center;
            font-size:16px;
          }</style>')

with st.echo()
    df[['column_1','column_2']].style.applymap({
        True: '<span style="background-color:green; color:white">'+'✅'+'</span>',
        False: '<span style="background-color:red; color:white">'+'❌'+'</span>'
    }).to_html()
```

# 🗂 Using Gradio, create a simple interface where users can upload a CSV file and filter the data based on selected columns.



