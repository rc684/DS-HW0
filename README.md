# DS-Assignment0

* Step 4 Word Count

After setting up the environment and starting pyspark as instructed in assignment, 
I created the wordcount.py file and ran the following command in terminal. 

```
spark-submit wordcount.py wiki.txt output_directory

```

Note that both wordcount.py and wiki.txt files are save in the same underlying project folder, 
so there's no need to add path in front of the name of file.

As result, a folder named "output_directory" shown up in the project folder, which contained 2 files:

<img src="https://github.com/rc684/DS-HW0/blob/master/WordCount.png">

where the word counts are listed in the file named "part-00000", with in the format of ('word', count).


* Step 5 Bigrams

The code is written in ConditionalBigrams.py, in which I 

