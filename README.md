# StoryPerceptions
This repository contains dataset and analysis code for studying variation in narrative perceptions in social media texts.

Paper: https://aclanthology.org/2024.emnlp-main.1113/

### Setup
Clone the repository:
```
git clone git@github.com:joel-mire/story-perceptions.git
cd story-perceptions
```

Create a virtual environment:
```
python -m venv .venv
source .venv/bin/activate  # On Windows, use `.venv\Scripts\activate`
```

Install dependencies:
```
python -m pip install -r requirements.txt
```

### Preprocess Data
Run `preprocess.ipynb`, which:
* downloads the StorySeeker dataset
* rehydrates the texts from StorySeeker's source dataset, [(TLDR)](https://webis.de/data/webis-tldr-17.html).
* queries GPT series models and Llama3 for story labels (if results aren't already cached)
* preprocesses the crowd annotation data, our meta-annotations for crowd rationales, and the StorySeeker texts and labels.

### Run Analysis
Run `analysis.ipynb`, which uses StoryPerceptions to explore 3 research questions:
1. What are crowd workers’ descriptive perceptions of storytelling in social media texts?
2. How do narrative perceptions differ among crowd workers?
3. How do narrative perceptions differ across prescriptive labels from researchers, descriptive annotations from crowd workers, and predictions from LLM-based classifiers?

#### Data Files Overview
| Filename    | Description |
| -------- | ------- |
| codes.csv  | taxonomy codes, derived through qualitative analysis of crowd workers' free-text responses for our annotation task. See paper for details.|
| pc.csv | short for 'prolific_coded'; includes crowd annotations and our meta-annotations; used for most of the intra-crowd analysis |
| pcru_ann1.csv    | the first author's meta-annotations for the full set of the crowd's free-text annotations   |
| pcru_ann2.csv    | the second author's meta-annotations for a small subset of the crowd's free-text annotations  |
| sp.csv*    | an expanded version of the StorySeeker dataset that includes both descriptive labels from crowd workers and descriptive predictions from LLM-based classifiers, in addition to the pre-existing prescriptive labels from researchers |
| sse.csv*    | the StorySeeker dataset, rehydrated with texts downloaded from the TLDR dataset.    |
| tldr_ss_subset.csv*    | the subset of the TLDR dataset corresponding to the StorySeeker texts   |

\* files generated by `preprocess.ipynb`

### Questions?
Please open an issue or contact [Joel Mire](https://joelmire.notion.site/) with any questions.

### Citation
```
@inproceedings{mire-etal-2024-empirical,
    title = "The Empirical Variability of Narrative Perceptions of Social Media Texts",
    author = "Mire, Joel  and
      Antoniak, Maria  and
      Ash, Elliott  and
      Piper, Andrew  and
      Sap, Maarten",
    editor = "Al-Onaizan, Yaser  and
      Bansal, Mohit  and
      Chen, Yun-Nung",
    booktitle = "Proceedings of the 2024 Conference on Empirical Methods in Natural Language Processing",
    month = nov,
    year = "2024",
    address = "Miami, Florida, USA",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.emnlp-main.1113",
    pages = "19940--19968"
}
```
