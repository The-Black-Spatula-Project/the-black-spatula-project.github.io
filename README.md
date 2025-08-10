# The Black Spatula Project
[WhatsApp](https://chat.whatsapp.com/DRkjqk1pwTu1pDXC9oeC0q) - [Discord](https://discord.gg/Zxf9p7hAnG) - [GitHub](https://github.com/The-Black-Spatula-Project)

---

## Background
The Black Spatula Project is an open initiative to investigate the potential of large language models (LLMs) to identify errors in scientific papers. We seek to answer the following questions: How many errors can LLMs detect? How serious are those errors? Which model/prompt/pipeline performs the best? And ultimately, how can we use AI to improve scientific integrity?

The project was inspired by a scientific paper that, due to a simple math error that even an AI reviewer could catch, caused many people to toss all of their black plastic kitchen implements. To learn more about the story of this project, please check out [the initial post](https://amistrongeryet.substack.com/p/the-black-spatula-project) and [latest update](https://amistrongeryet.substack.com/p/black-spatula-day-five) by [Steve Newman](https://x.com/snewmanpv), the initiator of the project.

If you’d like to get involved, join our currently very active [WhatsApp](https://chat.whatsapp.com/DRkjqk1pwTu1pDXC9oeC0q) group (for high-level discussion) and/or [Discord](https://discord.gg/Zxf9p7hAnG) (more focused on technical work). To contribute, check out the **Ongoing Tasks** section below.

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
    - Please save your prompts and results in the [WithdrarXiv Spreasheet](https://docs.google.com/spreadsheets/d/1Eo5BH_shOZXKf63_kA7cuDXTBkva0vteB9CBAddq2TI/edit?usp=sharing) or [Black Spatula Draft Analysis Prompts](https://docs.google.com/spreadsheets/d/1IHGQ5s9b6U6cofYsvYEm3ITEf9MrwsMZpqV48FJnyV0/edit?usp=sharing). This helps us keep track of the statistics and guide future directions.
- If you are a domain expert and would like to help verify LLMs’ results, please enter your name and expertise in the [Volunteer Evaluators](https://docs.google.com/spreadsheets/d/1CrkXS2WMx3a5mf5fVC_oSVJYEo3dgYZqAfm6GXX4htA) sheet

#### Pipeline ([#data-ingestion](https://discord.com/channels/1318622366322131015/1318643155419009024))
- Figure out a way to export papers into a format easy to read for LLMs
- Explore different methods for paper submission (checkout [#data-ingestion](https://discord.com/channels/1318622366322131015/1318643155419009024) and the [repository](https://github.com/anusheel/black-spatula-project))

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

#### Potential Error Types
- Math and numerical errors: data inconsistencies, calculation mistakes, etc.
- Methodology problems: problematic methods, inconsistent methods, etc.
- Writing and logical problems: incorrect interpretation of results, unsupported conclusions, etc.
- Figure and table discrepancies: labeling/formatting errors, mismatches with narrative, etc.
- Citation errors: invalid citations, missing citations, etc.
- Other minor problems: grammar issues, typos, incorrect table/figure numbers, etc.

#### Implementation Ideas
- Prioritize using papers in LaTeX to retain math formulas. Papers in other domains are usually in PDF but PDF conversion may mess it up.
- From @mhmazur: Use TeX files; Azure's Document Intelligence service for PDF OCR.
- From @Frecias: Grobid for parsing the text in PDF while retaining connections to references. Don’t use it for math/table/figure.

## Classification of errors and misconduct in scientific publications

### 1. Trivial Error (Level 1) | No formal correction required:
This is a purely cosmetic mistake with no impact on the data, interpretations, or credibility of the paper. Such trivial errors do not affect the reader's understanding or the scientific content. Examples: a minor typo or spelling mistake, a formatting glitch, or a trivial error in a reference. Journals generally do not issue formal corrections for these, since they do not alter the meaning or validity of the work.

### 2. Minor Error (Level 2) | Formal erratum if needed:
This category covers small mistakes in the content that have a negligible impact on data or conclusions. The error is obvious or easy to correct in context, and it does not change the quantitative results or scientific claims. In many cases, a brief erratum or correction notice may be published to fix the record, although the core findings remain unchanged. Examples: a minor typo in a data value that doesn't affect any calculations, an incorrect unit of measure (clearly a slip that readers can infer from context), a minor reference numbering error, or a mislabeled figure panel that readers can figure out from the description.

### 3. Notable Error (Level 3) | Localized impact on data or clarity:
An error more significant than a trivial typo, potentially affecting a specific table, figure, or section, but localized in scope. This error might slightly alter a particular result or cause some confusion, yet it has minimal to no effect on the overall conclusions of the paper. The main claims of the study still hold true, the authors or journal may issue a clarification or detailed correction to address the issue, ensuring readers are aware of the corrected detail. Examples: a small miscalculation in a supplementary analysis (with negligible effect on the primary outcome), a minor misreporting of a subset of sample data, or an inadvertently duplicated image panel in a figure (where the duplication is an assembly mistake that does not misrepresent the experimental results or affect the conclusions).

Examples:

• **Phillips H. R. P. et al. Science 2019, "Global distribution of earthworm diversity"** An erratum reported a bug in data preparation that removed some zero‑abundance sites in part of the dataset. Reanalysis lowered predicted global means and slightly shifted geographic patterns, while key environmental drivers and overall interpretation remained.

DOI: 10.1126/science.abd9834. 

***

• **Walton G. M. et al. Science 2023, "Where and with whom does a brief social‑belonging intervention promote progress in college"** An erratum corrected a labeling error in a supplementary table and noted that re‑running the preregistered analyses did not change the reported effects.

DOI: 10.1126/science.ads9718. See also the article record that flags the erratum.

DOI: 10.1126/science.ade4420. 

***

• **Gould C. A. et al. Science 2022, "Ultrahard magnetism from mixed‑valence dilanthanide complexes"** An erratum corrected a mistaken table entry. The spectral fits and magnetism claims remained as reported.

DOI: 10.1126/science.adf5804.

***

### 4. Localized Methodological Flaw or Omission (Level 4) | Needs public correction:
This error stems from a flaw in one part of the study's methodology, analysis, or data presentation. The flaw has a tangible impact on that section's findings, but it is not fatal to the paper's overall conclusions. In other words, one experiment or analysis may be flawed while the others are sound, so the paper is largely reliable except for the affected portion. Such errors must be addressed openly, for example via a detailed correction or corrigendum, to maintain transparency.

The correction would typically explain the flaw and, if possible, provide revised data or an omission notice for that part. Examples: a calibration error affecting the results of one figure, a mistake in data processing for a specific analysis, or omission of a key experimental detail that slightly limits reproducibility (but can be provided after the fact). In these cases, the authors might redo the flawed experiment or clarify the methods in a correction, and importantly, the overall interpretation of the study remains the same after the fix.

Examples:

• **Gore A. et al. Nature 2005, "The zebrafish dorsal axis is apparent at the four‑cell stage"** A corrigendum swapped the labels for two morpholino conditions in Figure 3 and in a supplementary table and updated the corresponding text. Conclusions were stated to stand.

DOI: 10.1038/nature11788.

***

• **Eisenbarth S. C. et al. Nature 2012, "NLRP10 is a NOD‑like receptor essential to initiate adaptive immunity by dendritic cells"** A corrigendum reported that a Dock8 mutation explained the dendritic‑cell migration phenotype in the knockout line. The authors reinterpreted which gene caused that phenotype while noting other findings.

DOI: 10.1038/nature16074. 

***

• **Liu Y. et al. Science 2023, "Spatially resolved single‑cell translatomics at molecular resolution"** An erratum corrected a mislabeled ribosome‑profiling dataset description. Analyses and conclusions remained. 

DOI: 10.1126/science.ado9025.

***

### 5. Major Error Affecting Conclusions (Level 5) | Corrigendum or partial retraction:
This is a serious error that undermines a significant part of the study's results or interpretations. It goes beyond a localized glitch, the mistake could change a key outcome or conclusion of the paper, though it might not invalidate everything. For instance, a critical dataset or analysis might be flawed, biasing one of the main claims. In such scenarios, a formal corrigendum (major correction) is required if the issue can be corrected, or a partial retraction may be issued if only a section of the paper is invalid while the rest remains trustworthy.

A partial retraction means that the problematic portion (for example one figure or a section of results) is withdrawn, but the majority of the article's content and conclusions are left intact and valid. This level of error demands a prominent public notice because readers need to be alerted that some conclusions have changed. Examples: A miscalculation that, when corrected, alters an important quantitative result (perhaps changing the strength of a result but not its overall direction) discovery that one experimental group's samples were compromised (invalidating that part of the study, but other independent confirmations support the main thesis) or a significant error in statistical analysis that requires re-analysis and slightly revised conclusions.

The journal might publish a correction explaining the changes in conclusions, or retract the flawed portion of the study while affirming the remainder.

Examples:

• **Worobey M. et al. Science 2022, "The Huanan Seafood Wholesale Market in Wuhan was the early epicenter of the COVID‑19 pandemic"** An erratum corrected distance data used in mapping analyses. The interpretation of market centrality was maintained.

DOI: 10.1126/science.adp1133.

***

• **Bushdid C. et al. Science 2014, "Humans can discriminate more than 1 trillion olfactory stimuli"** An erratum corrected specific reporting details tied to the original calculations. The headline claim was not changed by the notice.

DOI: 10.1126/science.ado6457.

***

• **Neurology Editorial Office 2017, Partial retraction notice for a 2016 Neurology research article.** The notice removed an author and replaced an affected figure after misconduct findings, and the remainder of the article was republished as corrected.

DOI: 10.1212/WNL.0000000000003650.

***

### 6. Severe Error, Unreliable Results (Level 6) | Candidate for retraction (Under review):
This category involves an error or a cluster of problems so severe that they render a substantial portion of the research unreliable or irreproducible. At this stage, the paper's scientific validity is in serious doubt. The issues are more widespread than a single figure, they call into question the overall findings of the study. Typically, when such severe problems come to light, the journal and authors will initiate an investigation to determine the extent of the flaw. During this period, the article is essentially a "candidate for retraction" pending the outcome of the review. In many cases, journals will issue an Expression of Concern to warn readers that the results may not be reliable while the issues are being investigated.

If the review confirms that the main results cannot be trusted, a retraction will follow. Examples: pervasive statistical errors that affect most of the analyses, discovery of a fundamental mistake in study design or experimental setup that biases the results, or realization that a key reagent or cell line was contaminated or misidentified, thus invalidating the experiments. At Level 6, there may still be hope to correct some parts, but the problems are serious enough that the entire paper is at risk of retraction if not resolved. Readers are alerted to use extreme caution with the findings until a final determination (correction or retraction) is made.

Examples:

• **Flore O. et al. Nature 1998, "Transformation of primary human endothelial cells by Kaposi’s sarcoma‑associated herpesvirus"** Editorial Expression of Concern issued in 2025 during an institutional review.

DOI: 10.1038/s41586‑025‑09239‑w.

***

• **Lu X. et al. Nature 2004, "The netrin receptor UNC5B mediates guidance events controlling morphogenesis of the vascular system"** Editorial Expression of Concern posted in 2023 that cites image integrity issues and an institutional report.

DOI: 10.1038/s41586‑023‑06944‑2.

***

• **Vaitiekėnas S. et al. Science 2018, "Flux‑induced topological superconductivity in full‑shell nanowires"** Editorial Expression of Concern published in 2021 while concerns were investigated.

DOI: 10.1126/science.abl5286.

***

### 7. Major Error Invalidating Main Findings (Level 7) | Retraction for honest but fatal mistakes:

This level represents a fatal error in the paper that fully invalidates the central findings, where the mistake is honest (not misconduct). In such cases, the authors and journal acknowledge that the paper's conclusions are no longer trustworthy due to the error, and the only responsible course is to retract the paper from the literature. Unlike Level 6, here it is clear that the problem cannot be fixed or isolated, the main claim of the study collapses. However, it is also clear that this resulted from unintentional error rather than any fraudulent intent.

Some papers have been retracted due to not being able to replicate them.

Retractions at this level are typically accompanied by an explanation that the authors made a mistake that undermines the results. All parties (authors, editors) generally agree to retract to preserve the integrity of the literature. Examples: A critical laboratory error (such as using the wrong cell line or animal strain) that nullifies the findings, a coding or calculation error that, when corrected, eliminates the key results, or post‑publication discovery that the data were misinterpreted such that the primary conclusion is wrong. These are often "honest mistakes", for example an experimental protocol flaw or an unforeseen artifact, but they are so severe that the main conclusions are no longer trustworthy, and the paper must be withdrawn for the sake of scientific accuracy.

Examples:

• **Wolfe‑Simon F. et al. Science 2010, "A bacterium that can grow by using arsenic instead of phosphorus"** Retracted in 2025 after years of failed replication.

**What happened and current discussion:** Follow‑up work did not detect arsenate in GFAJ‑1 DNA and showed that apparent growth in arsenate media can be explained by phosphate released during ribosome breakdown or by trace phosphate. Science retracted the paper in 2025 stating that by today’s standards the reported experiments did not support the key conclusions. The authors filed a letter disagreeing and some commentators argue this case reflects a shift toward retracting papers for non‑misconduct reasons when core claims fail robust replication. Coverage notes the scientific consensus that the claim did not hold up, while debate continues about when journals should retract long‑debated work.

DOI of the retraction: 10.1126/science.adu5488.

***

• **Lee S. W. et al. Science 2009, "A type I‑secreted, sulfated peptide triggers XA21‑mediated innate immunity"** Retraction cites strain mislabeling and assay problems that invalidate the main claim.

DOI of the retraction: 10.1126/science.342.6155.191‑a.

***

• **Lombardi V. C. et al. Science 2009, "Detection of an infectious retrovirus, XMRV, in blood cells of patients with chronic fatigue syndrome"** Retracted after contamination findings and failure to replicate.

**What happened and current discussion:** Large multi‑laboratory blinded studies could not detect XMRV in patient samples. Evolutionary analyses showed XMRV originated as a recombinant formed during passage of a human prostate tumor in mice and is present in the 22Rv1 cell line, pointing to laboratory contamination as the source of positive signals. The field now regards XMRV as not a human pathogen. Reviews frame this case as a cautionary example about contamination control, blinded validation, and the need for replication before clinical claims.

DOI of the retraction: 10.1126/science.334.6063.1636‑a.

***

## Research Misconduct Levels (8-10)

### 8. Serious Misconduct (Level 8) | Plagiarism or data manipulation (Retraction):
This category marks the threshold where errors are no longer honest mistakes but clear research misconduct. Level 8 involves serious ethical breaches such as plagiarism, unethical research practices, or deliberate data manipulation/falsification in one part of the work. For example, the authors might have copied substantial portions of text or data from others, manipulated images or selectively reported data to misrepresent findings, or even conducted experiments on subjects without ethical approval.

These actions violate fundamental principles of research integrity and demand a public correction of the record. In virtually all such cases, the journal will retract the paper, and the retraction notice will cite the specific misconduct (plagiarism, figure manipulation, or unethical methods ) as the reason. Although the misconduct is serious, it may be limited in scope, perhaps isolated to a portion of the paper or to a single publication.

The impact on the literature is concerning but might be confined, meaning it doesn't necessarily undermine an entire body of science beyond the paper in question, but the credibility of the work and authors is badly damaged. Examples: A researcher is found to have plagiarized a paragraph of the introduction and fabricated a few data points in one figure, or an animal study is retracted because the authors failed to obtain animal ethics committee approval (an unethical oversight), casting doubt on that experiment's legitimacy. In all such cases, formal retraction is the remedy, since the paper's integrity is compromised by misconduct rather than error.

Examples:

• **LaCour M. J. and Green D. P. Science 2014, "When contact changes minds"** Retraction followed discovery of irregularities and lack of verifiable data.

DOI of the retraction: 10.1126/science.aac6638.

***

• **Shu L. L. et al. PNAS 2012, "Signing at the beginning makes ethics salient and decreases dishonest self‑reports in comparison to signing at the end"** Retraction due to data integrity problems.

DOI of the retraction: 10.1073/pnas.2115397118.

***

• **Chen C. Y. Journal of Vibration and Control 2009, "The Development of Half‑circle Fuzzy Numbers and Application in Fuzzy Control"** Retracted after the publisher uncovered a fabricated peer‑review ring tied to submissions.

Article page shows the retraction.

DOI: 10.1177/1077546309349849.

***

### 9. Malicious Misconduct (Level 9) | Fraud with broad Impact (Retraction with sanctions):
Level 9 represents deliberate fraud that is broader in scope or impact, indicating a willful intent to deceive that affects more than just a trivial portion of one study. This is the kind of misconduct where an author, or authors, has engaged in falsification, fabrication, or other fraudulent practices in a significant way, potentially across multiple figures, experiments, or even multiple papers. The impact of the fraud is "broad" in the sense that it may have misled an entire field of research or wasted substantial resources as others tried to build on false findings. For example, a researcher might fabricate an entire dataset or image in a paper that becomes highly cited, thus steering many other scientists down a wrong path before the fraud is uncovered.

Such misconduct usually triggers not only a retraction of the paper, but also institutional investigations and sanctions against the author. Journals will retract the work, and the retraction notice may explicitly label the issues as data fabrication or falsification. Often, these cases lead to multiple retractions if the same researcher's other publications are found fraudulent.

The key difference from Level 8 is the scale and intent, Level 9 misconduct is egregious and systematic, rather than a one-off lapse. Examples: A scientist is discovered tohave fabricated images for half of the figures in the paper or to have manipulated data in a clinical trial to produce a desired outcome, and this deception went unnoticed until other labs failed to replicate the results. The fallout can be broad, an entire line of research might be undermined. The response from the scientific community is typically severe, including retraction of the publication(s) and possible barring of the author from future research funding or positions. In summary, Level 9 is fraud on a grand scale, and while the corrective action on the literature is still a retraction, the case is treated as a serious offense against scientific integrity, often noted in retraction statements and accompanied by community reproach.

Examples:

• **Schön J. H. et al. Nature 2001, "Self‑assembled monolayer organic field‑effect transistors"** Retracted after a broad investigation found fabricated and duplicated data across the corpus.

Retraction notice DOI: 10.1038/nature01464.

***

• **Hwang W. S. et al. Science 2005, "Patient‑specific embryonic stem cells derived from human SCNT blastocysts"** University and journal investigations concluded the data were fabricated.

Editorial retraction DOI: 10.1126/science.1124926.

***

• **Dunoyer P. et al. The Plant Cell 2004, "Probing the microRNA and small interfering RNA pathways with virus‑encoded suppressors of RNA silencing"** Retraction cites image manipulation and duplications.

Retraction notice DOI: 10.1105/tpc.15.00407. 

***

### 10. Extreme Misconduct and Public Harm (Level 10) | Fraud with major consequences (Retraction and Scandal):
This is the most severe category, where fraudulent research not only constitutes deliberate deceit but also has direct, major consequences for public welfare or policy. In Level 10 cases the misconduct can be considered scandalous, it may have led to public health scares, dangerous clinical practices, or significant harm to society's trust in science. The research fraud is often highly publicized and may involve a larger conspiracy or gross negligence, and it typically results in extraordinary repercussions beyond the academic sphere.

The immediate action on the literature is still to retract the paper, or a series of papers, but in addition, there is often widespread public outrage, legal action, or regulatory changes that follow. Examples: The infamous 1998 study linking vaccines to autism (Ileal-lymphoid-nodular hyperplasia, non-specific colitis, and pervasive developmental disorder in children), later exposed as fraudulent, is a prime example of Level 10 misconduct. In that case, data were misrepresented for hidden motives, and the publication ignited a decline in vaccination rates worldwide, leading to disease outbreaks and putting lives at risk. The paper was eventually fully retracted, and the lead author was stripped of his medical license for ethical violations. Another example might be a researcher who fabricates clinical trial data for a new drug, resulting in patients suffering harm before the fraud is caught.

In these extreme scenarios, the misconduct undermines public trust and can cause tangible harm to people or the environment. Retractions here are accompanied by strong statements of condemnation. Often, the case becomes a cautionary tale in the media and academic discussions about research ethics. Level 10 represents the collapse of both scientific integrity and social responsibility, and it underscores why rigorous ethical standards and oversight are crucial.

Examples:

• **Wakefield A. J. et al. The Lancet 1998, "Ileal‑lymphoid‑nodular hyperplasia, non‑specific colitis, and pervasive developmental disorder in children."** Fully retracted in 2010 after investigations showed ethics breaches and data misrepresentation.

Retraction DOI: 10.1016/S0140‑6736(10)60175‑4.

Original DOI: 10.1016/S0140‑6736(97)11096‑0.

***

• **Macchiarini P. et al. The Lancet 2011, "Tracheobronchial transplantation with a stem‑cell‑seeded bioartificial nanocomposite trachea"** Retracted after findings of ethics violations and misrepresentation of outcomes.

Retraction DOI: 10.1016/S0140‑6736(18)31558‑7.

Original DOI: 10.1016/S0140‑6736(11)61715‑7.

***

• **Mehra M. R. et al. The Lancet 2020, "Hydroxychloroquine or chloroquine with or without a macrolide for treatment of COVID‑19"** Fully retracted due to unverifiable third‑party data and serious integrity concerns.

Retraction DOI: 10.1016/S0140‑6736(20)31324‑6.
