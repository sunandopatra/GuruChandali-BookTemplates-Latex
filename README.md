# GuruChandali-BookTemplates-Latex

## Intro
    All basic book templates used in creating books published from Guruchandali.
    All are LaTex files. Compiler needs to be XeTex (declared in the first line of the main Tex file; is enough for frontends like TexStudio, check for the required hack in other setups like Overleaf). Main tex files have names like "Template XXXX.tex".
    The main class used is 'Memoir'. Default Bengali font-class is Bengali Ananta. If you switch, remember to switch all necessary fonts for Bold and Italic, and change the corresponding entries in the main File.

## Details
For now, only two templates are there: 
 8.5 X 5.5 (US stock Statement Paper Size)
 7.25 X 4.75 (Custom size used in India)
 
 A book has three parts: FrontMatter, MainMatter, and BackMatter.

 FrontMatter is called in the main file through the '\input' command. This File and other necessary files (Adoption, BookList, ForeWord, and PrintersPage) are in the 'FrontMatter' directory. As you'll see, you don't need to open these (except the ForeWord and the BookList to edit) for editing the elements of the book. All those are set as commands in the main Tex file, so just concentrate on the content. 

 MainMatter can be a single file or can be broken into chapters (I prefer the Latter). Two chapters are supplied with various possible stylings (there can be many more), including the heading styles, header-footer styles, and table-of-content entry styles. Chosse any one in a single book.

 BackMatter is not qualitatively different from the frontmatter and things can switch places (warning: title pages in Memoir are a little tricky, so don't disturb the ordering if you are not feeling confident or have a deadline).  

 Happy pagemaking! 
