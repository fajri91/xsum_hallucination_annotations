# XSum Hallucination Annotations

This repository contains the faithfulness and factuality annotations of XSum
summaries from our paper
"[On Faithfulness and Factuality in Abstractive Summarization](https://www.aclweb.org/anthology/2020.acl-main.173.pdf)"
at ACL 2020.

Please cite our paper if you use our data.

```
@InProceedings{maynez_acl20,
  author =      "Joshua Maynez and Shashi Narayan and Bernd Bohnet and Ryan Thomas Mcdonald",
  title =       "On Faithfulness and Factuality in Abstractive Summarization",
  booktitle =   "Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics",
  year =        "2020",
  address = "Online",
}
```

## Introduction

Neural abstractive summarization models are highly prone to hallucinate content
that is unfaithful to the input document. The popular metric such as ROUGE fails
to show the severity of the problem. Our dataset is unique in that we have
conducted a large scale human evaluation of several neural abstractive
summarization systems to better understand the types of hallucinations they
produce. Our human annotators found substantial amounts of hallucinated content
in all model generated summaries. However, our analysis does show that
pretrained models are better summarizers not only in terms of raw metrics, i.e.,
ROUGE, but also in generating faithful and factual summaries as evaluated by
humans. Furthermore, we show that textual entailment measures better correlate
with faithfulness than standard metrics, potentially leading the way to
automatic evaluation metrics as well as training and decoding criteria. We
believe that this dataset will help advance the quality of neural summarization
by enabling research to better train and evaluate for trustworthy systems that
could have been more challenging to do otherwise.

## Dataset

The dataset consists of faithfulness and factuality annotations of abstractive
summaries for the [XSum dataset](https://www.aclweb.org/anthology/D18-1206.pdf).
We have crowdsourced 3 judgements for each of 500 x 5 document-system
pairs. This will be a valuable resource to the abstractive summarization
community.

### Faithfulness annotations

Raters are shown the news article and the system summary, and are tasked with
identifying and annotating the spans that aren't supported by the input
article. The csv file contains the following columns:

```
bbcid: Document id in the XSum corpus.
system: Name of neural summarizer.
summary: Summary generated by ‘system’.
hallucination_type: Type of hallucination (intrinsic or extrinsic)
hallucinated_span: Hallucinated span in the ‘summary’.
worker_id: 'wid_0', 'wid_1', 'wid_2'
```

### Factuality annotations

Raters are shown the news article and the hallucinated system summary, and are
tasked with assessing the summary whether it is factual or not. The csv file
contains the following columns:

```
bbcid: Document id in the XSum corpus.
system: Name of neural summarizer.
summary: Summary generated by ‘system’.
is_factual: yes/no
worker_id: 'wid_0', 'wid_1', 'wid_2'
```

## License

This dataset is released under the Creative Commons Attribution 4.0 International ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode)).

## Contact us

If you have a technical question regarding the dataset or publication, please
create an issue in this repository. This is the fastest way to reach us.

If you would like to share feedback or report concerns, please email us at
xsum-hallucinations-acl20@google.com.
