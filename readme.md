# LaTeX Template for Project Report



___Author: Aadarsha Paudel___ ( aadarsha@yahoo.com )



This is the documentation for this template. This template can be used on final report with slight modification. _(Of course, do it yourself)_

First, download this template; See the _green_ __Clone or Download__ button above? Click on it and choose __Download ZIP__. It will download a .zip containing of all the files here.

> Note: This is the template  I made for my use (on my project) so it may not get an problem fix unless it occurs to me directly, nor will you get any support from me. Just read this documentation and you probably should be able to figure out on your own.

> If you can't solve the problem, there is a thing called "Search Engines" available in the internet. Use that.

> I have tried this first on MiKTeX but it showed me weird error about section numbering that I couldn't fix but texlive-most + vscode (with latex workbench extension) worked fine for me in Arch Linux.

> This documentation is just for a basic guidelines and is not a way for you to learn latex. Also, I cannot guarentee that the information you can find here are 100% accurate or error proof. Use this / Follow this at your own risk. **You are on your own if any problem occurs.**

## Basic Requirement

- A functioning brain.
- An internet connection.
- A general idea about what your project is.

## System Requirements

You need something that can compile the .tex (LaTeX file) into PDF. Latex works just fine in almost all operating systems but I strongly advise you to use linux for this as it is faster and easier *(and I've tested on and its working for me, at least)* 

### Windows

You need to install [MiKTeX](https://miktex.org/). After installing this package, you can simply open the .tex files by right clicking > Open As > TeXworks (if it isn't already default for .tex files, if it is, just double click it).

> Note: Choose "Always" option when asked about __Install Extensions/Package Automatically__ or something similar in MiKTeX installer. This will avoid any distraction when compiling.

> Note: There are few packages used here which aren't installed by default on MiKTeX so you need to download it (don't worry MiKTeX will do it automatically) but you need internet connection on first compile of this template.

> If come across any error saying "Number not found or something for \section{", it won't work no matter how much you try to fix it.  _(If you can, congrats)_ Solution I found: Use Linux.

### Linux

> Just to be clear, I haven't tried this on anything other than Arch Linux so I don't know properly but almost all process is similar if you can do basic search on the internet if you run into any issues (what did you expect, you are running linux in the first place). 

For linux, you can compile LaTeX to PDF by command line (you can do that with MiKTeX console on windows, but clicking Play (>) button is easier.

You can simply use any text editor of choice but VSCode with LaTeX extensions is better choice.

First, install __texlive__ package.

#### Arch Linux, Manjaro

Open Terminal and type, ```sudo pacman -S texlive-most```.

You need to install following packages: 1 2 3 4 7 9

```bash
:: There are 12 members in group texlive-most:
:: Repository extra
   1) texlive-bibtexextra  2) texlive-core  3) texlive-fontsextra
   4) texlive-formatsextra  5) texlive-games  6) texlive-humanities
   7) texlive-latexextra  8) texlive-music  9) texlive-pictures
   10) texlive-pstricks  11) texlive-publishers  12) texlive-science

Enter a selection (default=all): 1 2 3 4 7 9
```

Let it download and after than you can now compile latex. Congratulations. 

#### Ubuntu 18.04 and Debian Based

```bash
sudo apt install <PACKAGE_NAME>
```

There are several packages you can install. Here is a quick list;

- ```texlive-base``` - 136 MB
- ```texlive-latex-recommended``` - 177 MB
- ```texlive``` - 240 MB
- ```texlive-latex-extra``` - 404 MB
- ```texlive-full``` - 4714 MB

You can just install ```texlive``` package if you simply want stuff to work normally. For full packages, install ```texlive-full```. (Make sure you see the around 4GB package size). This above list is of Ubuntu 18.04 but possibly works with Debian, Linux Mint, Elementary OS, MX Linux, Kali Linux _(What are you doing, replace Kali with Ubuntu or Mint, boot kali as Live ISO)_ and other debian/ubuntu based distros.

> If you see errors about packages missing or some ```filename.sty``` missing, try installing ```texlive-latex-extra``` package too.

#### Other Distros

I haven't really tried, but you can lookup on internet on how to install these packages. If you can't find it, install MiKTeX, its available for Linux too.

### Editors/IDE for LaTeX in Linux

- ``gnome-latex`` [lightweight, does what is says, compiling latex]
- ``gummy`` [fairly similar to gnome-latex]
- ``vim`` [with plugins, you require 3 digit IQ to use, *pro tip: use :q to close vim*]
- any other text editor works, but you likely won't get "Convert to PDF" button on other text editors.
- **Visual Studio** ```Code``` also has ```Latex Workshop``` extension _(by James Yu)_ that does auto compiling on each file change. **BEST CHOICE FOR YOU**

> If you are having trouble choosing, use Visual Studio Code.
> 
> VS Code isn't available in ubuntu repository so you need to either use Software Center (It has Snap Package) or download a .deb file from its official website and install it using ```sudo apt install ./filename.deb``` *(Replace filename with the file name, the ```./``` infront is required to let apt know that you are using local packages and not looking for package in repository)*

> **Pro Tip:** You can search packages for latex text editor by ```pacman -Ss latex``` or ```apt search latex```, choose one and install. Almost all do same thing; give you a button to compile LaTeX to PDF easily.

### Mac

I don't have one, you don't have one. But incase you are rich and like fancy toys, see the Windows section above. MiKTeX works fine on Mac too. (You can install ```texlive``` package too if you want fancy terminal compiling.)

## Usage

> Note: You need to compile the ```report.tex``` file only. All other files (in files/ folder are automatically inserted into PDF.

This whole template is divided into various files.

The main file is ```report.tex``` which is on Project's base directory.

Other files are located in ```files/``` folder.

Major Files;

- ```abstract.tex``` - for abstract
- ```introduction.tex``` - Introduction
- ```literature.tex``` - Literature Review
- ```methodology.tex``` - Methodology
- ```time.tex``` - Time Schedule
- ```conclusion.tex``` - Conclusion
- ```references.tex``` - References

Judging from the file name, you can pretty much figure out what content goes where. If you can't figure out, good luck, I can't do anything for you.

The page numbers are automatically configured, so is the Table of Contents, List of Figures, List of Tables and List of Abbreviations.



## Compiling Document

While Visual Studio Code + Latex Workshop does fine to compile latex to PDF, it won't include list of abbreviations (glossaries). To add that, you need to this guide.



As I mentioned earlier, this template uses ```glossaries``` package, which requires to run ```makeglossaries report``` command after compiling and recompining it again by command ```pdflatex report```.



Here is a quick command you can run (after ```cd```ing to the directory you have this files on; easy way to do this, use Visual Studio Code and ```Ctrl + ~``` will show you terminal in that directory.)

```bash
pdflatex report
makeglossaries report
pdflatex report
```

(The two times compiling is because, first time you need to regular compiling, after that makeglossaries will determine the abbreviations you have used and makes an index and second time you compile to include that determined glossaries on the PDF file)

PS; The ```report``` on above command is the file name (you don't need to mention filename explictly in latex in most of the times)

#### List of Abbreviations

There is a ```abbr.tex``` file in ```files/``` folder. You can put your abbreviation there. (See the file, you can copy one entry and modify it to your required abbreviation)

The basic usage for creating new abbreviation is;

```tex
\newacronym{<ID>}{<SHORT_FORM>}{<FULL_FORM>}
```

Example: For NY as New York

```tex
% Abbreviations
\newacronym{ny}{NY}{New York}
```

> Note: % starts comment in LaTeX, similar to // in C

To use an short form, use this command,

```tex
\acrshort{<ID>}
```

Example: For the example above, to print NY in document and automatically include it in List of Abbreviations too, use this;

```tex
\acrshort{ny}
```

This will print out __NY__ in the paragraph. More examples;

```tex
I live in \acrshort{ny}. I love \ac{ny}. \ac{ny} is the best.
```

Output:

```
I live in NY. I love NY. NY is the best.
```

It will automatically make glossaries (after you type the makeglossaries command) after compiling and recompiling it again. [See the section above this about "Compiling"]

#### Section

Chapters are already fixed in in the report.tex file, so you don't have to change anything. As for sections, they can vary to your project so you need to add it yourself.

__# How to add new section?__

```tex
\section{Awesome Title}
```

This will automatically place it into table of contents, give it section numbering and format it to correct style (Bold, Size 12pt, Uppercase) automatically.

#### Line Break and Paragraph Spacing

For creating new line break, you need to type enter key two times. (Two new lines are required to change a paragraph.)

Example:

```tex
This is line 1.
This is line 2.

This is line 3.
This is line 4.
```

This will display as:

```
This is line 1. This is line 2.

This is line 3. This is line 4.
```

Also, latex by default put some spacing on the paragraphs excluding the first one.

Eg:

```
This is line 1. This is line 2.

   This is line 3. This is line 4.
```

> See space infront of "This is line 3."

To remove that, use ```\noindent```.

Usage:

```tex
This is line 1.
This is line 2.

\noindent
This is line 3.
This is line 4.
```

This will remove that spacing in front.

### For Images, Tables, Text Formatting

Learn latex yourself, they are the basic stuffs. I can't make a 1000 word documentation on what's already there.

> If you want to learn it, See "Luke Smith's Latex Tutorials". It short and easy to understand __(Ignore the portion about setup in Linux, you already have it and you can use that code on any IDE/Text Editor; just see for the latex codes and formatting)

> There are other ebooks about this and wikibooks has its own version which is full with almost all default options you can use on latex as well as various miscellaneous stuffs too.



I use arch btw.
