## GuruChandali-BookTemplates-Latex

### Intro
 All basic book templates used in creating books published from Guruchandali.

 All are LaTex files. Compiler needs to be XeTex (declared in the first line of the main Tex file; is enough for frontends like TexStudio, check for the required hack in other setups like Overleaf). Main tex files have names like "Template XXXX.tex".
 
 The main class used is 'Memoir'. Default Bengali font-class is Bengali Ananta. If you switch, remember to switch all necessary fonts for Bold and Italic, and change the corresponding entries in the main File.

### Details
 For now, only two templates are there: \
 8.5 X 5.5 (US stock Statement Paper Size)\
 7.25 X 4.75 (Custom size used in India)
 
 A book has three parts: FrontMatter, MainMatter, and BackMatter.

 FrontMatter is called in the main file through the '\input' command. This File and other necessary files (Adoption, BookList, ForeWord, and PrintersPage) are in the 'FrontMatter' directory. As you'll see, you don't need to open these (except the ForeWord and the BookList to edit) for editing the elements of the book. All those are set as commands in the main Tex file, so just concentrate on the content. 

 MainMatter can be a single file or can be broken into chapters (I prefer the Latter). Two chapters are supplied with various possible stylings (there can be many more), including the heading styles, header-footer styles, and table-of-content entry styles. Chosse any one in a single book.

 BackMatter is not qualitatively different from the frontmatter and things can switch places (warning: title pages in Memoir are a little tricky, so don't disturb the ordering if you are not feeling confident or have a deadline).  

 Happy pagemaking! 

## OCR কল

Go to the Folder `GuruOCR` to find the files. The folder contains three Python scripts and a Mathematica Notebook. The scripts are designed to extract text from images and PDFs using the ***Mistral AI*** *OCR model*. The Mathematica Notebook is designed to run loops with the same scripts. Given a directory with multiple images or PDFs, the notebook will call the model for each file and save the results (in *JSON* or *MarkDown* format) in separate folders.

### What you need
 
- [Python 3.8+](https://www.python.org/downloads/)
- [Pip](https://pip.pypa.io/en/stable/installation/)

1. To get started, create a Mistral account or sign in at [console.mistral.ai](https://console.mistral.ai/).
2. Then, navigate to "Workspace" and "Billing" to add your payment information and activate payments on your account.
3. After that, go to the "API keys" page and make a new API key by clicking "Create new key". Make sure to copy the API key, save it safely, and do not share it with anyone.
4. In the Terminal, run the following command to install the library to use the Mistral API:
    ```
    pip install mistralai
    ```  
5. Edit the `mistral_api_key` variable in all three `.py` files with your *API key*.

### How to use

- **Single Use**: Open your terminal and run the following command:
    ```
    python <path_to_script> <path_to_pdf> <path_to_result_file>
    ```
    For example, if you use the terminal to go to this directory, run the script `script_OCR_Mistral_py2md.py` and want to extract text from the file `example.pdf`, give the result file a name like `result.md` extension and then run:
    ```
    python script_OCR_Mistral_py2md.py example.pdf result.md
    ```
    The result will be saved in the file `result.md` in the same directory.
- **Batch Use**: Open the Mathematica Notebook `OCR_Mistral_Example.nb` and run the cells. The notebook will call the Python scripts for each file in the directory you specify and save the results in separate folders. You can choose to save the results in *JSON* or *MarkDown* format. More details are given in the notebook.
- **Python Scripts**: 
    - `script_OCR_Mistral_py2md.py`: Extracts text from images and PDFs and saves the result in *MarkDown* format.
    - `script_OCR_Mistral_py2json.py`: Extracts text from images and PDFs and saves the result in *JSON* format.
    - `script_OCR_Mistral.py`: Extracts text from images and PDFs and saves the result in both formats. Example:
        ```
        python script_OCR_Mistral.py example.pdf result.json result.md
        ```

In Windows, use the command `python.exe` instead of `python` to run the scripts.

### Some notes

 - Like all OCR models, this model is **not perfect** and may not work well with all images or PDFs. The quality of the results depends on the quality of the input files.
 - Problems may arise while extracting text from images with complex layouts or images with a lot of noise. The model works best with images that have clear text and a simple layout.
 - The **example PDF file** is the scanned copy of the seminal book by Jagadish Chandra Bose, "**Abyakta**". The book is in the public domain and can be downloaded from [Internet Archive](https://archive.org/details/dli.scoerat.3652abyakta/mode/2up).
 - It is chosen because it shows the limits of this model for Bengali text. The model is not able to extract the text correctly from the images. The model works well with English text (especially scientific text), but it is not trained for Bengali text. We may use a fine-tuned model later.
