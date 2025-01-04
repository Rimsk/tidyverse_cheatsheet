# tidyverse_cheatsheet

""A Guide to Importing Data Using the tidyverse: Cheatsheet""

A key initial step in any project is importing external data into R. Data is commonly stored in tabular formats such as CSV files or spreadsheets.

The first section of this cheatsheet demonstrates how to import and save text files into R using the readr package. The second section covers how to import data from Excel spreadsheets using readxl or from Google Sheets using googlesheets4.

  To begin working with data in R, we load the following libraries:

  readr: for importing and saving text files like CSVs.
  
  readxl: for importing data from Excel files.
  
  googlesheets4: for accessing and importing data from Google Sheets.



      library(readr)
      library(readxl)
      library(googlesheets4)

To read files with custom delimiters, use read_delim(). If no delimiter is specified, the function will automatically attempt to detect the correct one.

For example, if you have the following data:

    Apple|Banana|Cherry
    123|456|789
    10|11|NA


You can import it with read_delim(), and it will be automatically parsed like this:

    read_delim("file.txt", delim = "|", show_col_types = FALSE)


To create the file named file.txt, run:

    write_file("Apple|Banana|Cherry\n123|456|789\n10|11|NA", file = "file.txt")

To read a comma-delimited file with period decimal marks, use read_csv().

   For example, if the file you wish to import contains the following:

     Apple,Banana,Cherry
     123,456,789
     10,11,NA

Import the file using read_csv(), and it will appear like this once loaded:

    read_csv("file.csv", show_col_types = FALSE)

To create the file named file.csv, run:

    write_file("Apple,Banana,Cherry\n123,456,789\n410,11,NA", file = "file.csv")


To read a semicolon delimited file with comma decimal marks: read_csv2().

If the file you want to import is the following:


    Apple;Banana;Cherry
     123;456;789
     10;11;NA

Import the file using  read_csv2() and it will appear like this once loaded:

    read_csv2("file.csv", show_col_types = FALSE)

To create the file named file2.csv, run:

    write_file("Apple;Banana;Cherry\n123;456;789\n10;11;NA", file = "file.csv")


    






