---
layout: post
title: A Busy Weekend of Hobby Coding
tags: PDF pandas dataframe python toml
---

Late last week I was assigned to code and process a bunch of invoices. Rather than spend work hours automating it with python, I used my 'kids are still asleep' time. While not complete, I am happy with my progress with importing pdf invoices into python. My end goal is to export the data/itemized list to excel (because that is the format that our accouting department speaks).

A bit of poking around for libraries dealing with pdf files in python returned:

-   tabula
-   pdf2text
-   pdfminer
-   textract
-   pypdf2 
-   slate

The ones I found most useful were Tabula for the body/itemization of invoices, and pdfminer for any other content. 

When I am highly experimental my workflow is to use a conda environment with a jupyter notebook. I break apart lines of code in different cells while figuring them out, then build method blocks as I go. Finish a section, build a `def` block, restart the kernal and move on to the next one. Simply because of difficulty getting conda to install some of the above libraries I abandoned some of them. Unfortunately Slate and Textract fell into this category. They looked the most promising and had decent documentation and nice API's.

#### Tabula

I was blown away with how easy Tabula handles tables in PDFs. For invoices this is usually the body of the invoice where items or services are itemized on a line basis. 

Tabula intends the table data from the PDF to go into a pandas dataframe, which is fantastic

To use Tabula in a fresh conda environment:

    conda create -n [nameofenvironment] anaconda

    # add conda forge
    conda config --add channels conda-forge 

    # install required java component
    conda install openjdk

    # install tabula
    pip install tabula-py

For the invoices I had to deal with, importing the table data was as simple as:

```python
import tabula 
df = tabula.read_pdf("test.pdf")
```

That is it. An import and one line of code. My only hang up is the Java dependency. Especially on windows machines keeping the Java versions and updates in line is a tricky thing. Frequently in enterprises some legacy app needs an old version that can't be updated, conflicts arise, chaos ensues. 

#### pdfminer

    conda install pdfminer.six

[StackOverflow](https://stackoverflow.com/questions/26494211/extracting-text-from-a-pdf-file-using-pdfminer-in-python "StackOverflow - ") saved me hours on this one. I found several mentions of pdfminer being tricky to configure. With the amount of set up to extract a PDF, I can see why. That being said, so far pdfminer.six has handled every document I have fed into it. 

Extracting a PDF with pdfminer.six:

```python
import io
from pdfminer.pdfinterp import PDFResourceManager, PDFPageInterpreter
from pdfminer.converter import TextConverter
from pdfminer.layout import LAParams
from pdfminer.pdfpage import PDFPage

def convert_pdf_to_txt(path,password="",maxpages=0):
    '''ref number 26494211'''
    rsrcmgr = PDFResourceManager()
    retstr = io.StringIO()
    codec = 'utf-8'
    laparams = LAParams()
    device = TextConverter(rsrcmgr, retstr, codec=codec, laparams=laparams)
    fp = open(path, 'rb')
    interpreter = PDFPageInterpreter(rsrcmgr, device)
    caching = True
    pagenos = set()

    for page in PDFPage.get_pages(fp, pagenos, maxpages=maxpages,
                                  password=password,
                                  caching=caching,
                                  check_extractable=True):
        interpreter.process_page(page)

    text = retstr.getvalue()

    fp.close()
    device.close()
    retstr.close()
    return text
```

#### Other Options

I also tried:

-   textract - looked most promising, failed due to pulse audio and unrtf dependency.
-   pdf2text - failed due to gcc dependency
-   pypdf2 - installed, but the PDFs in my sample all only returned line returns
-   slate - also promising. failed with error below

```bash
pip install slate
Collecting slate
  Downloading slate-0.3.zip
Collecting distribute (from slate)
  Downloading distribute-0.7.3.zip (145kB)
    100% |████████████████████████████████| 153kB 2.7MB/s 
    Complete output from command python setup.py egg_info:
    Traceback (most recent call last):
      File "<string>", line 1, in <module>
      File "/tmp/pip-build-w16ykv5b/distribute/setuptools/__init__.py", line 2, in <module>
        from setuptools.extension import Extension, Library
      File "/tmp/pip-build-w16ykv5b/distribute/setuptools/extension.py", line 5, in <module>
        from setuptools.dist import _get_unpatched
      File "/tmp/pip-build-w16ykv5b/distribute/setuptools/dist.py", line 7, in <module>
        from setuptools.command.install import install
      File "/tmp/pip-build-w16ykv5b/distribute/setuptools/command/__init__.py", line 8, in <module>
        from setuptools.command import install_scripts
      File "/tmp/pip-build-w16ykv5b/distribute/setuptools/command/install_scripts.py", line 3, in <module>
        from pkg_resources import Distribution, PathMetadata, ensure_directory
      File "/tmp/pip-build-w16ykv5b/distribute/pkg_resources.py", line 1518, in <module>
        register_loader_type(importlib_bootstrap.SourceFileLoader, DefaultProvider)
    AttributeError: module 'importlib._bootstrap' has no attribute 'SourceFileLoader'
    
    ----------------------------------------
Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-build-w16ykv5b/distribute/
```

Went to file a bug report, it is a [known issue](https://github.com/timClicks/slate/issues/38 "GitHub - Slate - Issue 38").

Slate looked as promising as textract, I may revisit once the bug fix is pushed to pypi. 
