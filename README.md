# Useful tools
explaining useful tools and commands for everyday tasks!

### pdftk: 
it stands for pdf toolkit and is a versataile command-line utility designed for manipulating pdf files.

you can do many things including:
1. merging PDFs:

  - `pdftk <input_files> cat output <output_file>`
  
  this command will merge input files together and put them in output file!

2. Splitting PDFs:

  - `pdftk <input_file> burst output <output_pattern>`
  
this command will split pdf file into single pages. 

  * you can use %d to automate the naming process: `pdftk input.pdf burst output pages%d.pdf` it outputs pages in pdf format with the names like page1.pdf, page2.pdf, etc...

3. Rotating pages:

  - `pdftk <input_file> cat <page_range><rotation> output <output_file>`
  
  * Page range: you can select pages in several ways: 
    1. Specific page: 5 e.g.
    2. Multiple pages: 1,3,5 e.g.
    3. Page range: 5-20 e.g.
    4. All the pages: 1-end
    5. Reverse range: end-1
    6. Mixed: for example 1-20 21,23 56
    7. Repeating pages: 1 1 1 this outputs first page 3 times!

  * Rotation: the rotation direction
    1. N(north): no Rotation
    2. E(east): 90° clockwise
    3. S(south): 180° Rotation
    4. W(west): 90° counterclockwise

4. Extracting pages:

  - `pdftk <input_file> cat <page_range> output <output_file>`

  * it extracts pages from input file with the given pattern and puts it in output file.
  
5. Adding backgrounds or stamps:

  - for adding a background: `pdftk <input_file> background <background_file> output <output_file>`
  
  - for adding a stamp: `pdftk <input_file> stamp <stamp_file> output <output_file>`
  
  * Difference between stamp and background is that stamp adds the overlay on top of the existing content but background adds it beneath the existing content.
  
6. Repairing PDFs: pdftk attempts to rebuild the structure of the pdf file during this process however if the corruption is severe the repair might not be successful!

- `pdftk <corrupted_file.pdf> output <repaired_file.pdf>`

