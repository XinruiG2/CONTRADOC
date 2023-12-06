## ContraDoc: Understanding Self-Contradictions in Documents with Large Language Models

This is the repo for [ContraDoc: Understanding Self-Contradictions in Documents with Large Language Models](https://arxiv.org/abs/2311.09182).

### Dataset Introduction:

CONTRADOC contains 449 self-contradictory(positive examples) and 442 non-contradictory(negative examples) documents, covering documents sourced from CNN_Dailymain News, Wikipedia and Story Summaries, document length varying from 300 to 2200 tokens. This dataset is created by introducing self-contradiction to documents using GPT-4-Modify => Human Annotate and Verify. This dataset is developed as a benchmark to test model's ability in finding contradiction in long document.

### Dataset Format:

The positive examples are in "pos", while negative examples are in "neg", please refer to the paper for more detials of each label.

``````json
{"pos":
  {"DOC_ID":
    {"text": DOCUMENT, 
      "evidence": SENTENCE_INTRODUCING_CONTRADICTION,
      "unique id": DOC_ID,
      "doc_type":"story_OR_news_OR_wiki",
      "contra_plug": "Insert_OR_Replace", 
      "contra_type": [contradiction type],
      "scope": "global_OR_local_OR_intra",
      "ref sentences"(optional): [sentences contradict the evidence]
    },
  },
},
{"neg":
  {"DOC_ID":
    {"text": DOCUMENT,
      "doc_type": "story_OR_news_OR_wiki",
      "unique id": DOC_ID
    },
  },
}
``````

