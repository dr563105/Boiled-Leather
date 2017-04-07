# Boiled-Leather
A script to create the boiled leather reading order of AFFC and ADWD (a part of the A Song of Ice and Fire series) 

User guide:
this is a guide for how to make your own e-book of the Boiled Leather reading order.

I'm currently planning my first reread of the series, and for that, I'd like to use the All Leather Must Be Boiled order for AFFC/ADWD. I read the E-books, but really don't want to change between them every chapter. So I've created a Python script that takes the chapters from an unpacked .epub file, renames them and puts them in order. Then it's just putting it all together with your favourite e-book editor.

First, the ingredients:

    1. 1 Windows computer (I know it works on Windows. 
    If any of you have Linux/OSX and it doesn't work, please comment and 
    I'll see if I can get it working for you too).
    2. 1 AFFC and 1 ADWD e-book.
    3. Python 3.5 installed.
    4. The script and a copy of a .txt file of the Boiled Leather chronology 
    (Follow this link to my github. Press the green "Clone or Download" button, and download as .zip. 
    It contains the script, the .txt file ("chapters.txt") and a second .txt file of the 
    "non-veteran version" ("chapters (non-veteran).txt"). 
    You can ignore this second .txt file; it is for people who haven't read AFFC or ADWD. 
    If that's you, please see this comment thread)
    5. Calibre or another e-book manager/editor

Then the instructions:

    First you need to make sure that your e-books are in .epub format, 
    as this is just a .zip archive with another name. If your books are in .mobi or .azw3 (Amazon e-books) 
    you can use Calibre to convert them to .epub format. I've done this with several books,
    with no problems in formatting.
    Make a work folder (I put mine on the desktop), which will house all the files needed.
    Place the python script and the .txt file in the work folder,
    and create a subfolder called "book" (this will hold the renamed files).
    Take the .epub files for your books, and unpack them like .zip files 
    (either use 7zip or change the file extension from .epub to .zip).
    Rename the folders for the books so they're called AFFC and ADWD respectively. 
    After this step, your folder should look something like this. 
    
I've just made a backup of the folders for the sake of it.
Check the folders for .html files (these hold the text of the chapters). 
Mine are all called index_split_xxx.html, where xxx is 000 to 106 for my copy of ADWD. These are all the chapters, appendicies, front page, table of contents and all that goodness. Here's a picture of mine
Check the .html files until you find the one for the prologues (or press "Edit ebook" in Calibre). For my copy of AFFC this is number 007 and for ADWD this is 005.

If the names and numbers for your books are different you will have to open the python script (I heartily recommend Notepad++ for this, but regular, old notepad will do fine)

If the chapter starting numbers are different, say 3 for AFFC and 4 for ADWD you have to change line 4 from start = [7,5] to start = [3,4]

If the name of the files are different, say they're called "chapter_xxx" you have to change line 5: og_file = "index_split" to og_file = "chapter"

If there are no leading zeroes in the files, so the first is index_split_0.html or whatever, instead of index_split_000.html, change line 6 from padding = 3 to padding = 0.

So if the files are called "chapter_x.html", and starts with number 3 (AFFC) and number 4 (ADWD), the first few lines should look like this

If something else is different please post a comment with the details, then I'll see what I can do.

Once all of this is in order you run the python script by double clicking it. If it works as it should, a command prompt / terminal should briefly appear and then disappear again, and all of the contents should be in the "book" folder, named "1 - ADWD 1.html", "2 - AFFC 1.html" and so on. Here's a pic of mine

Now for editing the e-book together. I use Calibre for this:

    Open Calibre
    press the arrow besides "Add books" in the main window and select the fifth option: "Add empty book".
    Add the metadata you want (Author, title, series). Make sure you add it as an EPUB book (see picture

)
Right click this new, empty book in the main window, and select the second to last option: "Edit book". This will bring up a new window (picture
)
Press "file" and select "import files into book". Navigate to the work folder and import all the .html files. Now all the text is in the book, and it should be in the correct order. (picture
)
Decide on which stylesheet to use and import it (import files into book -> select all the .css files in either the AFFC or ADWD folder).
Import any images you want or need (in my e-books there are banners at the start of every chapter). Select a chapter and check if the images display. If they don't display (like here
) go to the "Tools" menu and select "Arrange into Folders". This will bring up a menu, which should be configured correctly automatically, so just press "ok". The chapters should now properly display the banners (like here
).
Now to add a table of contents: Select "tools" -> "Table of contents" -> "Edit table of contents". This will bring up a window
. Select "Generate ToC from files". The window should now look like this

    .
    Now save the e-book and add it to your favourite e-reader.

At this point the e-book is ready to be read. I haven't added the maps or appendix because I really don't like to use them on my kindle. But if you'd like them, shoot me a message, and I'll conjure up an extension to the tutorial for this too. I hope this guide was easy to follow. Thank you for reading
