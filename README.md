# scispacy-graphql

Ines Montani's Spacy-Graphql app adapted to use AI2's SciSpacy package.

### Example query

```graphql
{
  nlp(text: "Past medical history includes Hypertension, Dyslipidemia, Coronary Artery Disease and Lung Cancer. He presents with pleuritic chest pain, dyspnea, and syncope.",
    model: "en_core_sci_sm") {
    meta {
      lang
      description
    }
    doc {
      text
      tokens {
        text
        pos_
      }
      ents {
        text
        label_
      }
    }
  }
}
```

### Example Response

```json
{
  "data": {
    "nlp": {
      "meta": {
        "lang": "en",
        "description": "Spacy Models for Biomedical Text."
      },
      "doc": {
        "text": "Past medical history includes Hypertension, Dyslipidemia, Coronary Artery Disease and Lung Cancer. He presents with pleuritic chest pain, dyspnea, and syncope.",
        "tokens": [
          {
            "text": "Past",
            "pos_": "ADJ"
          },
          {
            "text": "medical",
            "pos_": "ADJ"
          },
          {
            "text": "history",
            "pos_": "NOUN"
          },
          {
            "text": "includes",
            "pos_": "VERB"
          },
          {
            "text": "Hypertension",
            "pos_": "PROPN"
          },
          {
            "text": ",",
            "pos_": "PUNCT"
          },
          {
            "text": "Dyslipidemia",
            "pos_": "PROPN"
          },
          {
            "text": ",",
            "pos_": "PUNCT"
          },
          {
            "text": "Coronary",
            "pos_": "PROPN"
          },
          {
            "text": "Artery",
            "pos_": "PROPN"
          },
          {
            "text": "Disease",
            "pos_": "PROPN"
          },
          {
            "text": "and",
            "pos_": "CCONJ"
          },
          {
            "text": "Lung",
            "pos_": "PROPN"
          },
          {
            "text": "Cancer",
            "pos_": "PROPN"
          },
          {
            "text": ".",
            "pos_": "PUNCT"
          },
          {
            "text": "He",
            "pos_": "PRON"
          },
          {
            "text": "presents",
            "pos_": "VERB"
          },
          {
            "text": "with",
            "pos_": "ADP"
          },
          {
            "text": "pleuritic",
            "pos_": "ADJ"
          },
          {
            "text": "chest",
            "pos_": "NOUN"
          },
          {
            "text": "pain",
            "pos_": "NOUN"
          },
          {
            "text": ",",
            "pos_": "PUNCT"
          },
          {
            "text": "dyspnea",
            "pos_": "NOUN"
          },
          {
            "text": ",",
            "pos_": "PUNCT"
          },
          {
            "text": "and",
            "pos_": "CCONJ"
          },
          {
            "text": "syncope",
            "pos_": "NOUN"
          },
          {
            "text": ".",
            "pos_": "PUNCT"
          }
        ],
        "ents": [
          {
            "text": "Past medical history",
            "label_": "ENTITY"
          },
          {
            "text": "Hypertension",
            "label_": "ENTITY"
          },
          {
            "text": "Dyslipidemia",
            "label_": "ENTITY"
          },
          {
            "text": "Coronary Artery Disease",
            "label_": "ENTITY"
          },
          {
            "text": "Lung Cancer",
            "label_": "ENTITY"
          },
          {
            "text": "pleuritic chest pain",
            "label_": "ENTITY"
          },
          {
            "text": "dyspnea",
            "label_": "ENTITY"
          },
          {
            "text": "syncope",
            "label_": "ENTITY"
          }
        ]
      }
    }
  }
}
```
