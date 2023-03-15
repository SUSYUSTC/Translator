# Translator
This is a project to provide translation of scientific papers with heavy math symbols from any language to any language while keeping the math symbols unchanged. In most translation softwares you wouldn't be able to keep equations and it would annoy you.
This project is based on the following two tools:
1. mathpix: it provides an interface to convert text+equation images to latex code.
2. translate-shell: it provides a terminal interface to google translate

The main work in this project is to translate a latex file from one language to another and an interface to combine them.

## Requirements
1. A mathpix account with OCR https://mathpix.com/docs/ocr/overview
2. python 3 with library `requests`: `pip install requests`
3. translate-shell: `sudo apt-get install translate-shell`
4. texlive (or any other tool to generate pdf from tex): `sudo apt-get install texlive-full`

## Usage
1. In `Translator/scripts/mpix.py`, replace 'YOUR_APP_ID' and 'YOUR_APP_KEY' with the OCR ID and key you get from mathpix website (the rate limit is 200 times per minute which is more than enough unless you want to translate a huge batch)
2. Add directory `Translator/scripts` to PATH
3. Screenshot each part of your paper one by one and name them by part1.png, part2.png, ... partXXX.png in your directory.
4. Run `translate.sh` in this folder then `main.pdf` (and `main.tex`) is all you need!
5. Since this project is small, sometimes you need to slightly change the final tex file for compilation.
6. The current code is translating English into Chinese. If you want to translate from/to other languages, you just need to change `language_from` and `language_to` in `Translator/scripts/translate_tex.py`

## Examples
In the example directory, run `translate.sh` and you would expect to get the same with `main.tex` and `main.pdf`.
