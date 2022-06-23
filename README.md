# ECCC: Khmer Speech Translation Corpus of the Extraordinary Chambers in the Courts of Cambodia

This repository is for sharing the dataset of Khmer speech translation corpus for the low-resource speech translation track at Workshop on Asian Translation (WAT) 2022

## Background of ECCC

It is a spoken language translation (SLT) corpus of Khmer to English and French, namely ECCC, which is an international court dataset consisting of text and speech in Khmer, English, and French. However, this provided dataset is only for Khmer SLT, which has the speech in Khmer and translation text into English and French. This dataset has a wide range of speakers: witnesses, defendants, judges, clerks or officers, co-prosecutors, experts, defense counsels, civil parties, and interpreters.

## Statistical data

We randomly selected 20% of the original ECCC of the Khmer SLT [Soky et al.,2021].

 | Dataset | # utterances | Duration |
 | --- | --- | --- |
 | Training | 11.563 | 29:07:31 |
 | Dev | 624 | 1:39:53 |
 | Testing | 626 | 1:38:27 |

## Baseline Systems

The goal of this task is to translate from the Khmer speech to English/French.
### Baseline setting

#### - ASR
| Encoder | 6 |
| Decoder | 6 | 
| FFN units | 1024 | 
| Attention head | 4 |
| Attention-dim | 256 |
| Epochs | 60 |
| Batch-size | 64 |
| BPE | 3000 |
#### - MT
| Encoder | 6 |
| Decoder | 6 | 
| FFN units | 1024 | 
| Attention head | 4 |
| Attention-dim | 256 |
| Epochs | 100 |
| Batch-size | 96 |
| BPE | 3000 per language |
#### - ST
| Encoder | 6 |
| Decoder | 6 | 
| FFN units | 1024 | 
| Attention head | 4 |
| Attention-dim | 256 |
| Epochs | 60 |
| Batch-size | 64 |
| BPE | 3000 per language |

* Note: The ASR encoder is also used to initialize the ST encoder, and MT decoder is initialized the ST decoder.
### Results

| System | Task | Performance | Input | output |
| --- | --- | --- | --- | --- |
| ASR | Khmer | 21.5% (WER) | Khmer speech | Khmer text |
| MT | Khmer-English | 11.3 (BLEU) | Khmer text | English text |
| MT | Khmer-French | 8.7 (BLEU) | Khmer text | French text |
| ST | Khmer-English | 5.1 (BLEU) | Khmer speech | English text |
| ST | Khmer-French | 5.1 (BLEU) | Khmer speech | French text |

## Citation

```
@INPROCEEDINGS{soky-eccc-2021,
    author={Soky, Kak and Mimura, Masato and Kawahara, Tatsuya and Li, Sheng and Ding, Chenchen and Chu, Chenhui and Sam, Sethserey},
    booktitle={2021 24th Conference of the Oriental COCOSDA International Committee for the Co-ordination and Standardisation of Speech Databases and Assessment Techniques (O-COCOSDA)},
    title={Khmer Speech Translation Corpus of the Extraordinary Chambers in the Courts of Cambodia (ECCC)},
    year={2021},
    pages={122-127},
    doi={10.1109/O-COCOSDA202152914.2021.9660421}}
```

## License

All the resources are property of NIPTICT, NICT, and Kyoto University.
This dataset will only allow to use in the WAT 2022.

## Acknowledgement

We would like to thank the National Institute of Posts, Telecoms, and Information Communication Technology (NIPTICT), Phnom Penh, Cambodia for giving us the resources of ECCC corpus.