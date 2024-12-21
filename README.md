# The Black Spatula Project
[WhatsApp](https://chat.whatsapp.com/DRkjqk1pwTu1pDXC9oeC0q) - [Discord](https://discord.gg/ynSY7q9y) - [GitHub](https://github.com/The-Black-Spatula-Project)

---

## Background
The Black Spatula Project is an open initiative to investigate the potential of large language models (LLMs) to identify errors in scientific papers. We seek to answer the following questions: How many errors can LLMs detect? How serious are those errors? Which model/prompt/pipeline performs the best? How can we use AI to improve scientific integrity?

The project was inspired by a scientific paper that, due to a simple math error that even an AI reviewer could catch, caused many people to toss all of their black plastic kitchen implements. For more details, please check out the [original introduction](https://amistrongeryet.substack.com/p/the-black-spatula-project) by [Steve Newman](https://x.com/snewmanpv), the initiator of the project.

If you’d like to get involved, join our currently very active [WhatsApp](https://chat.whatsapp.com/DRkjqk1pwTu1pDXC9oeC0q) group (for high-level discussion) and/or [Discord](https://discord.gg/ynSY7q9y) (more focused on technical work). To contribute, check out the **Ongoing Tasks** section below.

## Important Links

#### Worksheets
- [WithdrarXiv Spreasheet](https://docs.google.com/spreadsheets/d/1Eo5BH_shOZXKf63_kA7cuDXTBkva0vteB9CBAddq2TI/edit?usp=sharing) - Contains arXiv papers with known errors, prompts for LLMs, and test results (maintaned by Discord community)
- [Black Spatula Draft Analysis Prompts](https://docs.google.com/spreadsheets/d/1IHGQ5s9b6U6cofYsvYEm3ITEf9MrwsMZpqV48FJnyV0/edit?usp=sharing) - Collection of prompts (maintained by WhatsApp community)

#### Other
- [Volunteer Evaluators](https://docs.google.com/spreadsheets/d/1CrkXS2WMx3a5mf5fVC_oSVJYEo3dgYZqAfm6GXX4htA)
- [Potential Funders](https://docs.google.com/spreadsheets/d/1tHEp3nMFgb26um6vBV8Ok2hOTCz8oq9rjMsFoRK38VE)
- [Form Submissions from Steve's Article](https://docs.google.com/spreadsheets/d/1wXZdt3a5_RsLFdKPs6KBr3YtE5D2nLvpJatxMYDQ2Ig)

## Ongoing Tasks

#### Research ([#prompt-and-model](https://discord.com/channels/1318622366322131015/1318756579113304074))
- Manually try some papers you like or from the [WithdrarXiv dataset](https://huggingface.co/datasets/darpa-scify/withdrarxiv) for testing.
    - You can use whatever model you like or have access to, including but not limited to ChatGPT, GPT-o1, Gemini 2.0 Flash Thinking, and Claude 3.5.
    - Please save your prompts and results in the [WithdrarXiv Spreasheet](https://docs.google.com/spreadsheets/d/1Eo5BH_shOZXKf63_kA7cuDXTBkva0vteB9CBAddq2TI/edit?usp=sharing) or [Black Spatula Draft Analysis Prompts](https://docs.google.com/spreadsheets/d/1IHGQ5s9b6U6cofYsvYEm3ITEf9MrwsMZpqV48FJnyV0/edit?usp=sharing). This helps us to keep track of the statistics and guide future directions.
- If you are a domain expert and would like to help verify LLMs’ results, please enter your name and expertise in the [Volunteer Evaluators](https://docs.google.com/spreadsheets/d/1CrkXS2WMx3a5mf5fVC_oSVJYEo3dgYZqAfm6GXX4htA) sheet

#### Pipeline ([#data-ingestion](https://discord.com/channels/1318622366322131015/1318643155419009024))
- Figure out a way to export papers into a format easy to read for LLMs
- Explore different methods for paper submission (checkout [#data-ingestion](https://discord.com/channels/1318622366322131015/1318643155419009024))

#### Website
- Website to post updates and important documents about the project

## Resources & Ideas

#### Potential Paper Sources
- Preprint repositories:
    - [arXiv](https://arxiv.org/): LaTeX, PDF, and HTML
    - [ChemRxiv](https://chemrxiv.org/engage/chemrxiv/public-dashboard): chemistry. PDF only
    - [PsyArXiv](https://osf.io/preprints/psyarxiv): psychology
    - [SOCArXiv](https://osf.io/preprints/socarxiv): social science
- [PubMed Central](https://pmc.ncbi.nlm.nih.gov/) (PMC): biomed papers in PDF and some have HTML. Has API for retrieval.
- [Social Science Open Access Repository](https://www.gesis.org/en/ssoar)
- [Semantic Scholar](https://www.semanticscholar.org/): papers from all open-access sources including the sources above. Has API for search and retrieval.
- WithdrarXiv [paper](https://arxiv.org/abs/2412.03775) & [dataset on HuggingFace](https://huggingface.co/datasets/darpa-scify/withdrarxiv): a large dataset of withdrawn papers from arXiv with associated retraction comments.
- [PubPeer](https://pubpeer.com/): a platform for biomed researchers to post comments on published papers.
- [Retraction Watch Database](https://retractiondatabase.org/RetractionSearch.aspx?): a database of retracted papers and reasons.


#### Implementation Ideas
- Prioritize using papers in LaTeX to retain math formulas. Papers in other domains are usually in PDF but PDF conversion may mess it up.
- From @mhmazur: Use TeX files; Azure's Document Intelligence service for PDF OCR.
- From @Frecias: Grobid for parsing the text in PDF while retaining connections to references. Don’t use it for math/table/figure.
