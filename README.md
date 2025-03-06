
# Customer Reviews Classification Using IBM Granite-3.2-8b Model 🔍

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/19w0eSMSeVjYxfxLobWYNnC5fI6XsEg_s)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1MF9D-2jQEj9NVXMPuXVSn4yK6AtDw7Ne)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An advanced NLP solution for multi-aspect customer review analysis using IBM's Granite-3.2-8b-instruct model.

## Features ✨
- Sentiment classification (Positive/Negative/Mixed)
- Aspect tagging (Battery Life, Screen Quality, Performance)
- Customizable model parameters
- Error handling for disabled model versions
- Colab-ready implementation

## Installation 🛠️

```bash
git clone https://github.com/yourusername/customer-reviewsClassification_UsingIBMGranite_AIModel.git
cd customer-reviewsClassification_UsingIBMGranite_AIModel
pip install -r requirements.txt
```

## Usage Example 💻

```python
from langchain_community.llms import Replicate
import os

# Configure model with optimal parameters
model = Replicate(
    model="ibm-granite/granite-3.2-8b-instruct",
    input={
        "temperature": 0.7,
        "max_length": 200,
        "top_p": 0.9,
        "repetition_penalty": 1.2
    }
)

reviews = [
    "Battery lasts all day but phone gets hot during gaming",
    "Screen dim outdoors but excellent colors indoors"
]

response = model.invoke(
    f"Classify sentiment and aspects for: {' '.join(reviews)}"
)
print(response)
```

## Optimal Parameters ⚙️

```json
{
  "top_k": 1,
  "top_p": 0.85,
  "max_tokens": 200,
  "temperature": 0.65,
  "repetition_penalty": 1.5,
  "stopping_sequence": "\n"
}
```

## Example Output 📄

```text
Positive (Battery Life), Negative (Thermal Performance)

Mixed (Screen Visibility), Positive (Color Accuracy)
```

## Troubleshooting 🔧

**Error:** `Version disabled`  
✅ **Solution:** Verify model name is exactly `ibm-granite/granite-3.2-8b-instruct`

**Error:** API authentication failure  
✅ **Solution:** Ensure valid `REPLICATE_API_TOKEN` in environment variables

