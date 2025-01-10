# Digitized Latin Collection

**Creators**: Stephen Bothwell, Kaitlin Stephan, Hildegund Müller, and David Chiang (University of Notre Dame)

**Maintainer**: Stephen Bothwell

## Summary

This repository, titled the Digitized Latin Collection (DLC), contains a set of Latin texts which were digitized at the University of Notre Dame. 
These works span authors from the Classical, Late, and Medieval periods of Latin, 
and they were digitized in pursuit of questions about prosody across the eras of Latin. 

We created these digitized texts through the following process:
1. We retrieved PDF versions of each text that we digitized, 
and we ensured that we had the rights to use and release data from the given textual editions.
2. We split each PDF into PNGs using `pdf2image` library (available [here](https://github.com/Belval/pdf2image)).
3. We employed the [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) tool with training data (tessdata) for Latin and Ancient Greek.
4. We outputted results to hOCR files, and we uploaded these to a locally-hosted version of the 
Lace post-correction tool (available [here](https://github.com/brobertson/Lace2)).
5. We post-corrected the OCR results in Lace for the *main text* (and not notes or critical apparati), and we obtained EpiDoc-styled XML documents from Lace with our corrections.
6. We ran an additional Latin spellchecker and performed a few manual checks to root out extraneous text such as marginal numbers and catch any missed errors.

Through this process, we created the documents presented in this repository. 
This repository is meant to be a public front-end for the outputs of our correction procedure. 
Other stages of the correction process, as well as code for the various stages of our process above, are available in other repositories.

## Contents

This repository contains the following authors and texts (each ordered by URI):
- Ambrose of Milan (stoa0022):
  - *De Excessu Fratris* (stoa001)
  - *De Fide* (stoa002)
  - *De Mysteriis* (stoa003)
  - *De Paenitentia* (stoa005)
  - *De Abraham* (stoa018)
  - *De Bono Mortis* (stoa020)
  - *De Cain et Abel* (stoa021)
  - *De Isaac vel Anima* (stoa033)
  - *De Iacob* (stoa034)
  - *De Ioseph* (stoa035)
  - *De Noe* (stoa039)
  - *De Obitu Theodosii* (stoa040)
  - *De Obitu Valentiani* (stoa041)
  - *De Paradiso* (stoa042)  
  - *De Sacramentis* (stoa043)
  - *Explanatio Symboli* (stoa050)
  - *Exameron* (stoa054)
- Apuleius Madaurensis (stoa0030):
  - *Asclepius* (stoa008)
  - *Peri Hermeneias* (???)
- Tiberius Claudius **Donatus** (stoa0110a):
  - *Interpretationes Vergilianae* (stoa002)
- Quintus Ennius (phi0043):
  - *Annales* (phi001)
- Rutilius Taurus Aemilianus **Palladius** (stoa0218):
  - *Opus Agriculturae* (stoa002)
- Giovanni Boccaccio (???):
  - *Scripta Breviora* (???)
- John Calvin (???):
  - *Commentaria Senecae "De Clementia"* (???)
- John of Salisbury (???):
  - *Epistolae* (???)
- Theodosius II (stoa0279):
  - *Codex Theodosianus* (stoa001)

## Contributing

If errors persist in the metadata or body of text within this data, we would be glad to know and correct it!
Please open an issue to start a conversation on the subject. 
In your issue, note the document(s) and section(s) where the information presented is inaccurate.

## Citations

### Our Work

A citation for this work is pending.

### Textual Sources

Please see each XML document for source information on its PDF and edition.

### Software Sources

Please consult the following sources for information on the software used:

```
@inproceedings{smithOverviewTesseractOCR2007,
  title = {An Overview of the Tesseract {{OCR}} Engine},
  booktitle = {Ninth International Conference on Document Analysis and Recognition ({{ICDAR}} 2007)},
  author = {Smith, R.},
  year = {2007},
  volume = {2},
  pages = {629--633},
  publisher = {IEEE},
  address = {Curitiba, Brazil},
  doi = {10.1109/ICDAR.2007.4376991},
  abstract = {The Tesseract OCR engine, as was the HP Research Prototype in the UNLV Fourth Annual Test of OCR Accuracy, is described in a comprehensive overview. Emphasis is placed on aspects that are novel or at least unusual in an OCR engine, including in particular the line finding, features/classification methods, and the adaptive classifier.},
  langid = {english},
  keywords = {Filters,Independent component analysis,Inspection,Open source software,Optical character recognition software,Pipelines,Prototypes,Search engines,Testing,Text recognition}
}

@misc{robertsonBrobertsonLace22024,
  title = {Brobertson/{{Lace2}}},
  author = {Robertson, Bruce},
  year = {2024},
  month = aug,
  urldate = {2024-08-22},
  abstract = {In-broswer OCR editing program that transforms OCR results into structured, citable TEI. No XML experience required!},
  copyright = {GPL-3.0},
  keywords = {exist-db,ocr,tei-xml},
  url = {https://github.com/brobertson/Lace2}
}

@misc{belvalBelvalPdf2image2025,
  title = {Belval/Pdf2image},
  author = {Belval, Edouard},
  year = {2025},
  month = jan,
  urldate = {2025-01-09},
  abstract = {A python module that wraps the pdftoppm utility to convert PDF to PIL Image object},
  copyright = {MIT},
  keywords = {convert,pdf,pil,pil-image,poppler},
  url = {https://github.com/Belval/pdf2image}
}
```

## Acknowledgements

We would like to thank the [Navari Family Center for Digital Scholarship (NFCDS)](https://cds.library.nd.edu/)
at the University of Notre Dame for supporting our work on 
digitization and making scholarly materials publicly-accessible.
