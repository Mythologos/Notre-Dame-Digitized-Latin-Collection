# Notre Dame Digitized Latin Collection

**Creators**: Stephen Bothwell, Kaitlin Stephan, Hildegund Müller, and David Chiang (University of Notre Dame)

**Maintainer**: Stephen Bothwell

## Summary

This repository, titled the Notre Dame Digitized Latin Collection (ND-DLC), contains a set of Latin texts which were digitized at the University of Notre Dame. 
These works span authors from the Classical, Late, and Medieval periods of Latin, 
and they were digitized in pursuit of questions about prosody across the eras of Latin. 

We created these digitized texts through the following process:
1. We retrieved PDF versions of each text that we digitized, 
and we ensured that we had the rights to use and release data from the given textual editions.
2. We split each PDF into PNGs using `pdf2image` library (available [here](https://github.com/Belval/pdf2image)).
3. We employed the [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) tool with training data (tessdata) for Latin and Ancient Greek via the `pytesseract` library (available [here](https://github.com/madmaze/pytesseract)).
4. We outputted results to hOCR files, and we uploaded these to a locally-hosted version of the 
*Lace* post-correction tool (available [here](https://github.com/brobertson/Lace2)).
5. We post-corrected the OCR results in Lace for the *main text* (and not notes or critical apparati), and we obtained EpiDoc-styled XML documents from Lace with our corrections.
6. We ran an additional Latin spellchecker and performed a few manual checks to root out extraneous text such as marginal numbers and catch any missed errors.
7. We applied the [Hook](https://github.com/Capitains/HookTest) testing suite via its [Docker container](https://github.com/Capitains/docker-hooktest) to ensure our documents were EpiDoc- and CTS-compliant, and we altered our documents until all tests passed.

Through this process, we created the documents presented in this repository. 
This repository is meant to be a public front-end for the outputs of our correction procedure. 
Other stages of the correction process, as well as code for the various stages of our process above, are available in other repositories.

### Use

We sourced the PDFs to construct our digital editions from the [Austrian Academy of Sciences Press](https://www.oeaw.ac.at/en/forschung/verlag/austrian-academy-of-sciences-press) and [Hathitrust](https://www.hathitrust.org/). 
We provide metadata in and accompanying each digital edition, following the CapiTainS implementation of the Canonical Text Services (CTS), to cite each source PDF.
- The Austrian Academy of Sciences Press has kindly granted us permission to release data based on their PDFs.
- All Hathitrust PDFs that we used are in the public domain in the United States. 
In addition, Schmitt's edition of Palladius' *Opus Agriculturae* is in the public domain internationally. 
All texts were digitized by Google, but this has no bearing on the release of texts here, as we do not redistribute the images or OCR from their PDFs.
We also did not make use of their OCR in our digitization procedure.

We release all our digital editions under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International license](https://creativecommons.org/licenses/by-nc-sa/4.0/). 
Our repository contains the text of this license in its LICENSE file.

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
- Pseudo-Apuleius Madaurensis (stoa0030p):
  - *Asclepius* (stoa001)
  - *Peri Hermeneias* (stoa002)
- Tiberius Claudius Donatus (stoa0110a):
  - *Interpretationes Vergilianae* (stoa002)
- Quintus Ennius (phi0043):
  - *Annales* (phi001)
- Rutilius Taurus Aemilianus Palladius (stoa0218):
  - *De Insitione* (stoa001)
  - *Opus Agriculturae* (stoa002)
- Giovanni Boccaccio (stoa0382):
  - *Scripta Breviora* (stoa001)
- John Calvin (stoa0380):
  - *Commentaria Senecae "De Clementia"* (stoa001)
- John of Salisbury (stoa0381):
  - *Epistolae* (stoa001)
- Theodosius II (stoa0279):
  - *Leges Novellae* (stoa001)
    - Theodosius II (stoa001; 1)
    - Valentinian III (stoa001; 2)
    - Majoran (stoa001; 3)
    - Marcian (stoa001; 4)
    - Severus (stoa001; 5)
    - Anthemus (stoa001; 6)

## Contributing

If errors persist in the metadata or body of text within this data, we would be glad to know and correct it!
Please open an issue to start a conversation on the subject. 
In your issue, note the document(s) and section(s) where the information presented is inaccurate.

## Citations

### Our Work

A citation for this work is pending.

### Textual Sources

Please see individual XML documents, as well as their accompanying `__cts__.xml` files, for source information on our source PDFs' editions.

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

@misc{barrusBarrustPyspellchecker2025,
  title = {Barrust/Pyspellchecker},
  author = {Barrus, Tyler},
  urldate = {2025-02-07},
  abstract = {Pure Python Spell Checking http://pyspellchecker.readthedocs.io/en/latest/},
  copyright = {MIT},
  keywords = {levenshtein-distance,python,python-spell-checking,spellcheck,spellchecker,spelling-checker},
  version = {0.8.1}
}

@misc{belvalBelvalPdf2image2025,
  title = {Belval/Pdf2image},
  author = {Belval, Edouard},
  urldate = {2025-01-09},
  abstract = {A python module that wraps the pdftoppm utility to convert PDF to PIL Image object},
  copyright = {MIT},
  keywords = {convert,pdf,pil,pil-image,poppler},
  version = {1.17.0}  
}

@misc{leeMadmazePytesseract2025,
  title = {Madmaze/Pytesseract},
  author = {Lee, Matthias A.},
  urldate = {2025-02-07},
  abstract = {A Python wrapper for Google Tesseract},
  copyright = {Apache-2.0},
  version = {0.3.13}
}

@misc{robertsonBrobertsonLace22024,
  title = {Brobertson/{{Lace2}}},
  author = {Robertson, Bruce},
  urldate = {2024-08-22},
  abstract = {In-broswer OCR editing program that transforms OCR results into structured, citable TEI. No XML experience required!},
  copyright = {GPL-3.0},
  keywords = {exist-db,ocr,tei-xml},
  version = {0.6.22}  
}

@misc{clericeCapitainsDockerhooktest2018,
  title = {Capitains/Docker-Hooktest},
  author = {Cl{\'e}rice, Thibault},
  year = {2018},
  month = nov,
  urldate = {2025-03-14},
  abstract = {Docker Image to run HookTest on a repository},
  copyright = {GPL-3.0},
  howpublished = {CapiTainS}
}
```

## Acknowledgements

We would like to thank the [Navari Family Center for Digital Scholarship (NFCDS)](https://cds.library.nd.edu/)
at the University of Notre Dame for supporting our work on 
digitization and making scholarly materials publicly-accessible.
