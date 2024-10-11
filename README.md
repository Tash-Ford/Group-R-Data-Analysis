# Group-R-Data-Analysis
Group R Data Analysis

## Part 1 

### Question 1
The code in part 1, question 1 reads the data file in as a table. It then displays the first 6 rows in the table.

-	Required package, “readr” installed and loaded using install.packages and library() command. 
-	Data read in as table with the read.table command, the row.names=1 argument creates rows with the gene identifiers as the names. stringsAsFactors=FALSE keeps character vectors. Header=TRUE uses the first row as column names. Row.names=1 uses the first column as row names.  
-	The head() function displays the first 6 lines of the table.

### Question 2
The code in part 1, question 2 creates a new column in the table with the means values of the rows.

-	rowMeans is used to calculate the mean value of each row in the data file, those values are then subset using Gene_Expression$Mean_value <- into the file. na.rm = TRUE tells the command to ignore any missing values.
-	The head() function displays the first 6 lines of the table.

### Question 3
The code in part 1, question 3 lists the 10 genes with the highest mean expression.

-	The order function sorts the data based on the mean values, the - argument must be used to sort in descending order. 
-	head(sorted) subsets the top 10 rows into Top10_Mean 
-	print() displays the data.


### Question 4
The code in part 1, question 4 finds the number of genes that have a mean less than 10.

-	Subset() takes gene expression data with a mean value of less than 10 and adds to the Low_Mean value. 
-	nrow() counts the data to get the number of genes with a mean under 10.

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

-	Making the value salmonella_URL equal to the html file of the Salmonella enterica subsp. enterica serovar Weltevreden, which was found on the website ensembl.
-	The download.file command used to download the value salmonella_URL, and name the file “salmonella.fa.gz”.
-	The gunzip command extracts the fasta file from a zip file.
-	The list.files() command was used to ensure the download of the “salmonella.fa” file was correct and complete.
-	The seqinr::read.fasta command was used to read the fasta data of the “salmonella.fa” file and create a value of salmonella for the data.
-	The length() command was used to determine the length of the salmonella fasta file.

-	Making the value ecoli_URL equal to the html file of the Escherichia coli str. K-12 substr. MG1655 str. K12 which was found on the website ensembl.
-	The download.file command used to download the value ecoli_URL, and name the file “ecoli.fa.gz”.
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
The code in part 2, question 3 calculates the length of all coding sequences in each organism. It also produces a boxplot and calculates mean and median values.

-	salmonella_csl <- sapply(salmonella, length) : sapply works as a loop function when calculating the length of each sequence in the Salmonella data 
-	head(salmonella_csl,25) : displays the first 25 lines. 25 was chosen to limit the amount of raw data displayed.


-	e_coli_csl <- sapply(e_coli, length) : sapply works as a loop function when calculating the length of each sequence in the E.coli data 
-	head(e_coli_csl,25) : displays the first 25 lines. 25 was chosen to limit the amount of raw data displayed.


-	boxplot(salmonella_csl, e_coli_csl,        ylab="Sequence Length",        main="Coding Sequence Length",        names = c("Salmonella","E.coli")) : creates a boxplot of both the Salmonella and the E.coli data. The heading of the plot is changed with the ‘main’ argument, the y axis label with ‘ylab’ and the names of each individual plot with the ‘names’ argument. 


-	mean(salmonella_csl) : calculates the average value, in this case the length, of every sequence.
-	median(salmonella_csl) : calculates the middle value of all the sequences.


-	mean(e_coli_csl) : calculates the average value, in this case the length, of every sequence.
-	median(e_coli_csl) : calculates the middle value of all the sequences.

### Question 4
The code is part 2, question 4 calculates the frequency of both nucleotides and amino acids. Barplots are created for both data types.

Frequency of DNA bases:

-	salmonella_DNA <- unlist(salmonella) : converts the list data into a vector making it easier for analysis
-	salmonella_DNA_comp <- count(salmonella_DNA,1) : used to calculate the amount of each nucleotide in each sequence, <- stores the results in the _comp values
-	salmonella_DNA_prop <- salmonella_DNA_comp/sum(salmonella_DNA_comp) : Dividing the _comp data by the sum of itself determines the frequency as a percentage in decimal form
-	salmonella_DNA_prop : displays the data stored in the value

-	e_coli_DNA <- unlist(e_coli) : converts the list data into a vector amking it easier for analysis
-	e_coli_DNA_comp <- count(e_coli_DNA,1) : used to calculate the amount of each nucleotide in each sequence, <- stores the results in the _comp values
-	e_coli_DNA_prop <- e_coli_DNA_comp/sum(e_coli_DNA_comp) : Dividing the _comp data by the sum of itself determines the frequency as a percentage in decimal form
-	e_coli_DNA_prop : displays the data stored in the value

Barplots:

-	barplot(salmonella_DNA_prop,xlab="Nucleotides",ylab="Frequency", main="Salmonella nucleotide frequency") : The frequency of nucleotides is displayed as a barplot with the barplot() command. The plot heading is determined with “main”, the x and y axis labels are determined using “xlab” and “ylab” respectively.

-	barplot(e_coli_DNA_prop,xlab="Nucleotides",ylab="Frequency", main="E coli nucleotide frequency") : The frequency of nucleotides is displayed as a barplot with the barplot() command. The plot heading is determined with “main”, the x and y axis labels are determined using “xlab” and “ylab” respectively.

Salmonella protein sequence frequency:

-	salmonella_prot <- lapply(salmonella, translate) : translates all sequences in the dataset to proteins sequences
-	salmonella_aa <- unique(salmonella_prot[[2]])
salmonella_aa <- salmonella_aa[salmonella_aa != "*"] : To define the amino acid alphabet, unique() extracts unique amino acids while salmonella_aa[salmonella_aa != “*”] removes any unknown amino acids. 
-	salmonella_aa_len <- length(salmonella_aa_len) : calculates length and adds to a value
-	salmonella_aa_count <- lapply(salmonella_prot, function(sequence) {  count(sequence, wordsize = 1, alphabet = salmonella_aa)}) : The aa alphabet is used calculate the number of each amino acid in the sequences using count(). Wordsize=1 sets the number of characters in the word to 1.
-	salmonella_aa_table <- do.call(rbind, salmonella_aa_count) : creates a table with the count data
-	salmonella_aa_totals <- colSums(salmonella_aa_table) : calculates the total of each column, in this case, it adds the amount of each amino acid across the sequences
-	salmonella_aa_prop <- salmonella_aa_totals/sum(salmonella_aa_totals) : The proportion of each total is calculated by dividing each total by the overall total
-	salmonella_aa_prop : displays the resulting data

E.coli Protein sequence frequency

-	e_coli_prot <- lapply(e_coli, translate) : translates all sequences in the dataset to proteins sequences
-	e_coli_aa <- unique(e_coli_prot[[2]]) 
e_coli_aa <- e_coli_aa[e_coli_aa != "*"] : To define the amino acid alphabet, unique() extracts unique amino acids while e_coli _aa e_coli _aa != “*”] removes any unknown amino acids.
-	e_coli_aa_len <- length(e_coli_aa) : calculates length and adds to a value
-	e_coli_aa_count <- lapply(e_coli_prot, function(sequence) {  count(sequence, wordsize = 1, alphabet = e_coli_aa)}) : The aa alphabet is used calculate the number of each amino acid in the sequences using count(). Wordsize=1 sets the number of characters in the word to 1.
-	e_coli_aa_table <- do.call(rbind, e_coli_aa_count) : creates a table with the count data
-	e_coli_aa_totals <- colSums(e_coli_aa_table) : calculates the total of each column, in this case, it adds the amount of each amino acid across the sequences
-	e_coli_aa_prop <- e_coli_aa_totals/sum(e_coli_aa_totals) : The proportion of each total is calculated by dividing each total by the overall total
-	e_coli_aa_prop : displays the resulting data

Bar plot for E.coli amino acid frequency

-	barplot(e_coli_aa_prop,xlab="Amino Acids",ylab="Frequency", main="E coli Amino Acid Frequency") : The frequency of each amino acid is displayed as a barplot with the barplot() command. The plot heading is determined with “main”, the x and y axis labels are determined using “xlab” and “ylab” respectively.

Bar plot for Salmonella amino acid frequency

-	barplot(salmonella_aa_prop,xlab="Amino Acids",ylab="Frequency", main="Salmonella Amino Acid Frequency") : The frequency of each amino acid is displayed as a barplot with the barplot() command. The plot heading is determined with “main”, the x and y axis labels are determined using “xlab” and “ylab” respectively.


### Question 5

### Question 6
-	The lapply() command used with the translate command, translated the salmonella nucleotide sequence into a protein sequence. The unlist command converts the protein sequence into a single character vector.
-	Using unique() command with a salmonella_prot sequence 2, and then the specific symbols[!= “*”], allows the character vectors present in salmonella_prot 2 to be turned into amino acid letter representatives, excluding the symbol of *, which is the alphabet of the amino acids represented by aa.

-	To find the 3 length K-mers in Salmonella, the count () command was used, with the command word size=3, and using the alphabet of aa. The data was then turned into a data frame for easier access of the data.
o	To find the overrepresented 3 length K-mers of salmonella, the arrange() command was used, with a negative(-
) frequency command to ensure the data would be represented in decreasing order.
The head() command was used with a maximum of 10, to show the 10 most overrepresented 3 length K-mers.
o	To find the underrepresented 3 length K-mers of salmonella, the arrange() command was used, with a frequency command to ensure the data would be represented in increasing order.
The head() command was used with a maximum of 10, to show the 10 most underrepresented 3 length K-mers.
-	To find the 4 length K-mers in Salmonella, the count () command was used, with the command word size=4, and using the alphabet of aa. The data was then turned into a data frame for easier access of the data.
o	To find the overrepresented 4 length K-mers of salmonella, the arrange() command was used, with a -frequency command to ensure the data would be represented in decreasing order.
The head() command was used with a maximum of 10, to show the 10 most overrepresented 4 length K-mers.
o	To find the underrepresented 4 length K-mers of salmonella, the arrange() command was used, with a frequency command to ensure the data would be represented in increasing order.
The head() command was used with a maximum of 10, to show the 10 most underrepresented 4 length K-mers.
-	To find the 5 length K-mers in Salmonella, the count () command was used, with the command word size=5, and using the alphabet of aa. The data was then turned into a data frame for easier access of the data.
o	To find the overrepresented 5 length K-mers of salmonella, the arrange() command was used, with a -frequency command to ensure the data would be represented in decreasing order.
The head() command was used with a maximum of 10, to show the 10 most overrepresented 5 length K-mers.
o	To find the underrepresented 5 length K-mers of salmonella, the arrange() command was used, with a frequency command to ensure the data would be represented in increasing order.
The head() command was used with a maximum of 10, to show the 10 most underrepresented 5 length K-mers.

-	The lapply() command used with the translate command, translated the E.coli nucleotide sequence into a protein sequence. The unlist command converts the protein sequence into a single character vector.
-	To find the 3 length K-mers in E.coli the count () command was used, with the command word size=3, and using the alphabet of aa. The data was then turned into a data frame for easier access of the data.
o	To find the overrepresented 3 length K-mers of E.coli, the arrange() command was used, with a -frequency command to ensure the data would be represented in decreasing order.
The head() command was used with a maximum of 10, to show the 10 most overrepresented 3 length K-mers.
o	To find the underrepresented 3 length K-mers of E.coli, the arrange() command was used, with a frequency command to ensure the data would be represented in increasing order.
The head() command was used with a maximum of 10, to show the 10 most underrepresented 3 length K-mers.
-	To find the 4 length K-mers in E.coli, the count () command was used, with the command word size=4, and using the alphabet of aa. The data was then turned into a data frame for easier access of the data.
o	To find the overrepresented 4 length K-mers of E.coli, the arrange() command was used, with a -frequency command to ensure the data would be represented in decreasing order.
The head() command was used with a maximum of 10, to show the 10 most overrepresented 4 length K-mers.
o	To find the underrepresented 4 length K-mers of E.coli, the arrange() command was used, with a frequency command to ensure the data would be represented in increasing order.
The head() command was used with a maximum of 10, to show the 10 most underrepresented 4 length K-mers.
-	To find the 5 length K-mers in E.coli, the count () command was used, with the command word size=5, and using the alphabet of aa. The data was then turned into a data frame for easier access of the data.
o	To find the overrepresented 5 length K-mers of E.coli, the arrange() command was used, with a -frequency command to ensure the data would be represented in decreasing order.
The head() command was used with a maximum of 10, to show the 10 most overrepresented 5 length K-mers.
o	To find the underrepresented 5 length K-mers of E.coli, the arrange() command was used, with a frequency command to ensure the data would be represented in increasing order.
The head() command was used with a maximum of 10, to show the 10 most underrepresented 5 length K-mers.


-	To plot the 3 length K-mers that are overrepresented in Salmonella and E.coli, new data frames were created, making the 3 length K-mers the row names for both salmonella and E.coli. This was done by using a [,-1] to remove the entire first column and then replace it with the 3 length K-mers names.
-	To make the plot, the plot() command was used looking at both salmonella and E.coli’ 10 most overrepresented 3 length K-mers. The main= command was used to give a title, xlab, used to give a title to the x-axis, ylab was used to give label to y axix.
o	The text command was used along with labels=row.names to label the frequency points on the graph, with the corresponding 3 length K-mer, cex command used to size the labels, the pos command to position the labels relative to the point, and the col command used to colour the labels, with E.coli as green and salmonella as red.
 
-	To plot the 3 length K-mers that are underrepresented in Salmonella and E.coli, new data frames were created, making the 3 length K-mers the row names for both salmonella and E.coli. This was done by using a [,-1] to remove the entire first column and then replace it with the 3 length K-mers names.
-	To make the plot, the plot() command was used looking at both salmonella and E.coli’ 10 most underrepresented 3 length K-mers. The main= command was used to give a title, xlab, used to give a title to the x-axis, ylab was used to give label to y axis.
o	The text command was used along with labels=row.names to label the frequency points on the graph, with the corresponding 3 length K-mers, cex command was used to size the labels, the pos command to position the labels relative to the point, and the col command used to colour the labels, with E.coli as green and salmonella as red.
 




