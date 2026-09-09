# DNA Sequence Analysis Toolkit

A Python-based bioinformatics toolkit for performing fundamental DNA sequence analysis using **Biopython**. The project demonstrates a complete computational workflow, including FASTA sequence loading, nucleotide composition analysis, GC content calculation, reverse complement generation, transcription, translation, ORF detection, motif searching, and visualization.

---

## Project Overview

DNA sequence analysis is an important component of computational biology and bioinformatics. This project demonstrates how Python and Biopython can be used to extract basic biological information from a DNA sequence.

The toolkit performs several fundamental sequence-analysis tasks and presents the results through numerical outputs and visualizations.

### Main analyses include:

* Nucleotide composition
* GC content calculation
* Nucleotide percentage analysis
* Reverse complement generation
* DNA transcription to RNA
* RNA translation to protein
* Open Reading Frame (ORF) detection
* DNA motif searching
* FASTA sequence loading
* Sequence visualization

The project was developed and executed using **Google Colab**, **Python**, and **Biopython**.

---

## Objectives

The main objectives of this project are to:

1. Demonstrate fundamental DNA sequence manipulation using Python.
2. Apply Biopython for biological sequence analysis.
3. Load DNA sequences from FASTA format.
4. Calculate nucleotide composition and GC content.
5. Perform DNA transcription and RNA translation.
6. Identify potential Open Reading Frames (ORFs).
7. Search for specific DNA sequence motifs.
8. Visualize nucleotide composition and GC content.
9. Build a reproducible workflow for basic bioinformatics analysis.

---

## Technologies Used

* **Python 3**
* **Biopython**
* **Matplotlib**
* **Google Colab**
* **FASTA format**

### Python Libraries

```python
from Bio.Seq import Seq
from Bio import SeqIO
import matplotlib.pyplot as plt
from collections import Counter
```

---

## Analysis Workflow

The project follows the workflow below:

```text
DNA Sequence
     |
     v
FASTA Input / Sequence Loading
     |
     v
Nucleotide Composition
     |
     +----> GC Content
     |
     +----> Nucleotide Percentages
     |
     +----> Reverse Complement
     |
     +----> Transcription
     |
     +----> Translation
     |
     +----> ORF Detection
     |
     +----> Motif Search
     |
     v
Visualization & Results
```

---

## Features

### 1. FASTA Sequence Loading

The project demonstrates how to create and parse a FASTA-formatted DNA sequence using Biopython's `SeqIO` module.

Example FASTA record:

```text
>Test_Sequence
ATGGCCATTGTAATGGGCCGCTGAAAGGGTGCCCGATAG
```

The sequence is successfully loaded and its identifier and length are extracted.

* **Sequence ID:** `Test_Sequence`
* **Sequence Length:** `39 bp`

---

### 2. Nucleotide Composition

The toolkit calculates the number of occurrences of each nucleotide in the DNA sequence.

For the example sequence:

| Nucleotide | Count |
| ---------- | ----: |
| A          |     9 |
| T          |     8 |
| G          |    14 |
| C          |     8 |

The total sequence length is **39 nucleotides**.

---

### 3. GC Content

GC content represents the percentage of guanine (G) and cytosine (C) nucleotides in a DNA sequence.

For the example sequence:

**GC Content: 56.41%**

A bar chart is also generated to visualize the GC content.

---

### 4. Nucleotide Percentages

The percentage of each nucleotide is calculated from the total sequence length.

| Nucleotide | Percentage |
| ---------- | ---------: |
| A          |     23.08% |
| T          |     20.51% |
| G          |     35.90% |
| C          |     20.51% |

These values provide a detailed representation of the sequence composition.

---

### 5. Reverse Complement

The toolkit generates the reverse complement of the DNA sequence using Biopython.

**Original DNA:**

```text
ATGGCCATTGTAATGGGCCGCTGAAAGGGTGCCCGATAG
```

**Reverse Complement:**

```text
CTATCGGGCACCCTTTCAGCGGCCCATTACAATGGCCAT
```

---

### 6. Transcription

The DNA sequence is transcribed into RNA using Biopython.

**DNA:**

```text
ATGGCCATTGTAATGGGCCGCTGAAAGGGTGCCCGATAG
```

**RNA:**

```text
AUGGCCAUUGUAAUGGGCCGCUGAAAGGGUGCCCGAUAG
```

---

### 7. Translation

The RNA sequence is translated into a protein sequence.

**Protein:**

```text
MAIVMGR*KGAR*
```

The `*` symbol represents a stop codon in the translated sequence.

---

### 8. Open Reading Frame (ORF) Detection

A custom Python function is implemented to identify candidate ORFs by searching for the start codon `ATG` followed by an in-frame stop codon (`TAA`, `TAG`, or `TGA`).

For the example sequence, two candidate ORFs were identified:

| Start | End | Protein    |
| ----: | --: | ---------- |
|     0 |  24 | `MAIVMGR*` |
|    12 |  24 | `MGR*`     |

This demonstrates how computational logic can be used to identify potential coding regions within a DNA sequence.

---

### 9. Motif Search

The toolkit can search for specific DNA motifs within the sequence.

For this example, the motif:

```text
ATG
```

was searched.

The motif was found at positions:

```text
[0, 12]
```

This functionality can be adapted to search for other biologically relevant sequence patterns.

---

### 10. Visualization

Matplotlib is used to visualize the results of the sequence analysis.

The project generates:

* **Nucleotide composition plot**
* **GC content plot**

### Nucleotide Composition

![Nucleotide Composition](images/nucleotide%20composition.png)

### GC Content

![GC Content](images/gc%20content.png)

The plots are saved as high-resolution PNG images using `dpi=300`.

---

## Example Results

The example DNA sequence produced the following results:

| Analysis            | Result          |
| ------------------- | --------------- |
| Sequence Length     | 39 bp           |
| A Count             | 9               |
| T Count             | 8               |
| G Count             | 14              |
| C Count             | 8               |
| GC Content          | 56.41%          |
| ATG Motif Positions | 0, 12           |
| Candidate ORFs      | 2               |
| Translated Protein  | `MAIVMGR*KGAR*` |

---

## Project Structure

```text
DNA-Sequence-Analysis-Toolkit/
│
├── DNA_Sequence_Analysis_Toolkit.ipynb
└── README.md
```

> The notebook creates the example `sequence.fasta` file during execution for demonstrating FASTA parsing and sequence loading.

---

## How to Run

### Using Google Colab

1. Open the `.ipynb` notebook from this repository.
2. Open the notebook in Google Colab.
3. Run the cells sequentially.
4. Biopython will be installed automatically by the notebook.
5. The complete DNA sequence analysis workflow will then be executed.

### Running Locally

Install the required Python packages:

```bash
pip install biopython matplotlib
```

Then open the notebook using Jupyter Notebook or JupyterLab.

---

## Requirements

The project requires:

```text
biopython
matplotlib
```

Python 3 is recommended.

---

## Limitations

This project is designed as an educational demonstration of fundamental DNA sequence analysis.

The current implementation uses a relatively small example sequence and a custom ORF-detection approach. Therefore, it is not intended to replace specialized genome annotation or advanced sequence-analysis software.

The ORF detection implemented in this project focuses on identifying candidate regions beginning with `ATG` and ending at an in-frame stop codon.

---

## Future Improvements

The toolkit can be extended with additional bioinformatics functionality, including:

* Support for multiple FASTA sequences
* User-uploaded FASTA files
* Automated DNA sequence validation
* Analysis of all six reading frames
* More comprehensive ORF detection
* Codon usage analysis
* Protein property analysis
* Sliding-window GC content analysis
* Interactive visualizations
* Command-line interface
* Automated analysis reports

---

## Conclusion

The **DNA Sequence Analysis Toolkit** demonstrates how Python and Biopython can be used to perform a fundamental bioinformatics workflow on DNA sequences.

The project combines sequence manipulation, statistical analysis, biological transformations, motif searching, candidate ORF identification, FASTA parsing, and visualization into a single reproducible workflow.

It provides a practical foundation for further development toward more advanced computational biology and bioinformatics applications.

---

## Author

**Rumaisa Muneer**

Developed as a practical bioinformatics and computational biology project using **Python**, **Biopython**, and **Google Colab**.
