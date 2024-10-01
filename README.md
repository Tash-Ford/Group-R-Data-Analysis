# Group-R-Data-Analysis
Group R Data Analysis

## Part 1 

### Question 1

### Question 2

### Question 3

### Question 4

### Question 5
The code in Part 1 Question five is used to create a histogram of the mean values of the gene expression data. The histogram creates a visual presentation of this data.

-	The hist() command is used to use the provided data to create a histogram.
-	The Gene_Expression$Mean_value is used to provide the data that will be used to plot the histogram
-	The breaks = 1000 is to create at most 1000 bars in the histogram, 
-	Xlim,provides a limit of the x axis at 60000
-	The xlab command allows a label to be placed at the x axis
-	The main command allows a title to be written for the histogram

### Question 6
The code in Part 1 Question 6 is used to convert a csv file growth data into an R object, and to list column names of the growth data r object.

-	Library(“R.utils”), which loads into the library the R.Utils package which has specific programs and functions.
-	Making the value URL equal to the html file of the growth data csv file, found in the GitHub repository.
-	The download.file command used to download the value URL, and name the file “growth_data”.
-	The list.files() command was used to ensure the download of the “growth_data” file was correct and complete.
-	The read.csv command was used to read the “growth_data” as a data frame and assign it to a variable. 
-	Colnames( growth_data), is used to output the column names of the growth data.

### Question 7
The code in Part 1 Question 7 is used to calculate the mean and standard deviation of the growth data tree circumference at both the northeast and southwest site at both 2005 and 2020.

-	To subset the data for south west and northeast into years of 2005 and 2020, I used the subset command with the Site == “northeast” and “southwest”, and selected the circumference growth year , of both 2005 and 2020, to create 4 subsets, northeast 2005, northeast 2020, southwest 2005, and southwest 2020.
-	To find the mean the mean() command was used on each of the subsets to find the desired mean of each site and the year.
-	To find the standard deviation  the sd() command was used on each of the subsets to find the desired mean of each site and the year.

### Question 8

### Question 9

### Question 10


## Part 2

### Question 1
The code used in Part 2 Question 1, was used to download the DNA sequence of E.coli (Escherichia coli str. K-12 substr. MG1655 str. K12 (GCA_000005845)) and Salmonella (Salmonella enterica subsp. enterica serovar Weltevreden (GCA_005518735)), to find the amount of coding sequences present in both organisms and present the results in a table and to describe any difference between Salmonella and E.coli.

-	Library(“seqinr”), which loads into the library the seqinr package which has specific programs and functions.
-	Library(“R.utils”), which loads into the library the R.Utils package which has specific programs and functions.

-	Making the value URL2 equal to the html file of the Salmonella enterica subsp. enterica serovar Weltevreden, which was found on the website ensembl.
-	The download.file command used to download the value UR2L, and name the file “salmonella.fa.gz”.
-	The gunzip command extracts the fasta file from a zip file.
-	The list.files() command was used to ensure the download of the “salmonella.fa” file was correct and complete.
-	The seqinr::read.fasta command was used to read the fasta data of the “salmonella.fa” file and create a value of salmonella for the data.
-	The length() command was used to determine the length of the salmonella fasta file.

-	Making the value URL3 equal to the html file of the Escherichia coli str. K-12 substr. MG1655 str. K12 which was found on the website ensembl.
-	The download.file command used to download the value UR2L, and name the file “ecoli.fa.gz”.
-	The gunzip command extracts the fasta file from a zip file.
-	The list.files() command was used to ensure the download of the “ecoli.fa” file was correct and complete.
-	The seqinr::read.fasta command was used to read the fasta data of the “e.coli.fa” file and create a value of e_coli for the data.
-	The length() command was used to determine the length of the e.coli fasta file.

-	To present the data in a table the as.table command was used, to create a table with provided information, in combination with the command rbind, which joins multiple rows together, using the command c, which concatenates the length of salmonella and the length of e.coli, into one row. The colnames command was used to name the columns of the table “Salmonella” and “E-coli”. The rowname command was used to name the row “Coding DNA sequences”. To call the table the value table1 was used to present the data into the table.

### Question 2
The code used in part 2 Question 2, was used to find the total amount of coding DNA that is in the Salmonella and E.coli data, to present the results in a table and to describe any difference between Salmonella and E.coli.

-	salmonella_length <-as.numeric(summary(salmonella)[,1])
o	The as.numeric command was used to ensure the values of the salmonella data were in a numeric value 
o	The summary value is used to efficiently provide the final answer to a command.
o	Using the square brackets with a comma then 1 [,1], indicates that all rows and only the first column will be summarised together.
o	Putting all this information into its own value ‘salmonella_length’
o	The sum(salmonella_length) command, sums the salmonella_length value, which provides the total amount of coding DNA in salmonella.


-	e_coli_length <- as.numeric(summary(e_coli)[,1])
o	The as.numeric command was used to ensure the values of the e.coli data were in a numeric value 
o	The summary value is used to efficiently provide the final answer to a command.
o	Using the square brackets with a comma then 1 [,1], indicates that all rows and only the first column will be summarised together.
o	Putting all this information into its own value ‘e_coli_length’
o	The sum(e_coli_length) command ,sums the e_coli_length value, which provides the total amount of coding DNA in e_coli.

-	To present the data in a table the as.table command was used, to create a table with the  provided information, in combination with the command rbind, which joins multiple rows together, using the command c, which concatenates the length of all salmonella coding DNA and the length of all e.coli coding DNA, into one row. The colnames command was used to name the columns of the table “Salmonella” and “E-coli”. The rowname command was used to name the row “Total coding DNA”. To call the table the value table2 was used to present the data into the table.

### Question 3

### Question 4

### Question 5

### Question 6