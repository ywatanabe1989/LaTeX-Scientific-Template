![CI](https://github.com/ywatanabe1989/LaTeX-Scientific-Template/actions/workflows/compile.yml/badge.svg)

## LaTeX Template for Scientific Manuscripts (Based on Elsevier's Guidelines) with Integrated Automatic Revision Systems

This LaTeX template is designed following the guidelines for an [Elsevier scientific manuscript](https://www.elsevier.com/researcher/author/policies-and-guidelines/latex-instructions) and can be adapted for other journal guidelines.

## Why LaTeX?
LaTeX is advantageous because it is:
- Well-organized
- Consistent
- Convenient for writing mathematical expressions
- Compatible with various text editors
- Equipped with automatic numbering, bookmarking, and referencing
- Efficient for version tracking
- Complementary to AI technology

## Installation on Ubuntu

```bash
$ ./.scripts/sh/install_on_ubuntu.sh
$ ./.scripts/sh/install_python.sh
```

## Usage Instructions

#### Files to Edit
- [`./bibliography.bib`](./bibliography.bib) – Bibliography database
- [`./main.tex`](./main.tex) – Main structure of the manuscript
- [`./src/`](./src/) – Components of the manuscript
- [`./configs/`](./configs/) – Configuration files for revising or adding citations using ChatGPT

The script [`./compile.sh`](./.scripts/sh/compile.sh) compiles the file [`./main.tex`](./main.tex) and generates the document [`./compiled.pdf`](./compiled.pdf). The usage examples are as follows:

```bash
./compile.sh

./compile.sh -p # Commit all changes and push the repository to GitHub [-p|--push]
./compile.sh -r # Revise TeX files listed in ./configs/files_to_revise.txt using ChatGPT [-r|--revise]
./compile.sh -i # Insert citations into the files listed in ./configs/files_to_revise.txt from ./bibliography.bib using ChatGPT [-i|--insert-citations]

yes | ./compile.sh -r -i -p # Automatically answer 'yes' to all prompts
```
Compilation logs can be found at [`./.logs/compile.log`](./.logs/compile.log).

To use ChatGPT, set your OpenAI API key as an environment variable with the command:

```bash
echo 'export OPENAI_API_KEY="YOUR_OPENAI_API_KEY"' >> ~/.bashrc
```

To reset versioning:

```bash
rm compiled_v* diff_v* -f
mv old .old/old-$(date +%s)
```

To last push

``` bash
git reset HEAD~1
```

To revert to a certain point:

```bash
git checkout <commit-hash> -- src/
```

Replace `YOUR_OPENAI_API_KEY` with your actual API key. For more information, visit the [OpenAI API documentation](https://openai.com/blog/openai-api). Your API key should resemble 'sk-**AN'.

## Project Structure (Tree)

Refer to [`./.tree.txt`](./.tree.txt) for the project structure, automatically generated by executing [`./compile.sh`](./compile.sh). The primary components are as follows:

```
.
├── bibliography.bib
├── configs
├── main.tex
└── src
    ├── abstract.tex
    ├── additional_info.tex
    ├── authors.tex
    ├── discussion.tex
    ├── figures
    │   ├── Figure_ID_01.tex
    │   ├── Figure_ID_02.tex
    │   ├── Figure_ID_03.tex
    │   ├── Figure_ID_04.tex
    │   ├── Figure_ID_05.tex
    │   ├── Figure_ID_06.tex
    │   └── Figure_ID_07.tex
    ├── graphical_abstract.tex
    ├── highlights.tex
    ├── introduction.tex
    ├── journal_name.tex
    ├── keywords.tex
    ├── methods.tex
    ├── results.tex
    ├── styles
    │   ├── bibliography.tex
    │   ├── formatting.tex
    │   └── packages.tex
    ├── tables
    │   ├── Table_ID_01.tex
    │   ├── Table_ID_02.tex
    │   └── Table_ID_03.tex
    └── title.tex
```


## Contact

For questions or feedback, please email ywata1989@gmail.com.
