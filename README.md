# scispacy-graphql

Ines Montani's Spacy-Graphql app adapted to use AI2's SciSpacy package, and Jeno Pizarro's Negspacy

### Example query

```graphql
{
  nlp(text: "He denies having anosmia, dyspnea or sore throat. I do not think he has COVID, but he could easily have a URTI.",
    model: "en_core_sci_sm") {
    # meta {
    #   lang
    #   description
    # }
    doc {
      # text
      # tokens {
      #   text
      #   pos_
      # }
      ents {
        text
        # label_
        negex
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
      "doc": {
        "ents": [
          {
            "text": "denies",
            "negex": true
          },
          {
            "text": "anosmia",
            "negex": false
          },
          {
            "text": "dyspnea",
            "negex": false
          },
          {
            "text": "sore throat",
            "negex": false
          },
          {
            "text": "COVID",
            "negex": false
          },
          {
            "text": "URTI",
            "negex": true
          }
        ]
      }
    }
  }
}
```
