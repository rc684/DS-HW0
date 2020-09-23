# DS-Assignment0

* Step 4 Word Count

After setting up the environment and starting pyspark as instructed in assignment, 
I created the wordcount.py file and ran the following command in terminal:

```
spark-submit wordcount.py wiki.txt output_directory
```

Note that both wordcount.py and wiki.txt files are save in the same underlying project folder, 
so there's no need to add path in front of the name of file.

As result, a folder named "output_directory" shown up in the project folder, which contained 2 files:

<img src="https://github.com/rc684/DS-HW0/blob/master/WordCount.png">

where the word counts are listed in the file named "part-00000", with format of ('word', count).
* The file has been renamed as "Word Counts" in the zipped folder.

* Step 5 Bigrams

The code below is ConditionalBigrams.py, in which I first read the wiki.txt file and generated biagrams by shifting 1 index.
Then, I wrote the map-reduce function on these bigrams using similar method as the Word Count in Step 4,
and named the result as "BigramCounts" and I also borrowed the code from Step 4 to get word counts ("wordCounts").

Next, before calculating conditional distribution of a bigram, I created a temp RDD to store the information from bigramCounts,
while having the initial word to be the key, i.e. entry in temp RDD looks like ('a', (('a', 'b'), count)).

And then, I joined the temp RDD with wordCounts on the key of initial word,
so that we have count information for both initial words and bigrams.
Finally, the conditional prob is ready to be calculated with #bigram / #initial word.

<img src="https://github.com/rc684/DS-HW0/blob/master/Bigram_Code.png">


Finishing the code part, I ran the following command in terminal:

```
spark-submit ConditionalBigrams.py wiki.txt Step5_Outcome
```


When it's done, a folder named "Step5_Outcome" was generated in the project folder, which contained 2 sub-folders:

<img src="https://github.com/rc684/DS-HW0/blob/master/Step5_Outcome.png">

Bigram counts are stored at "part1" folder, in the file named "part-00000", with format of (('word1', 'word2'), count)).
* The file has been renamed as "Bigram Counts" in the zipped folder.

<img src="https://github.com/rc684/DS-HW0/blob/master/Step5_Part1.png">

Conditional probability, i.e. frequency distribution is stored at "part2" folder,
in the file named "part-00000", with format of (('word1', 'word2'), prob.)).
* The file has been renamed as "Conditional Prob." in the zipped folder.

<img src="https://github.com/rc684/DS-HW0/blob/master/Step5_Part2.png">
