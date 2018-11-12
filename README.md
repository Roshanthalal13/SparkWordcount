# Spark_Wordcount

## About Me
My name is Roshan Thalal. I am currently studying at Northwest Missouri State University. I am a Data Science and Informatics Major. 

## Objective
The objective of this project is to use Spark in order to count the most repeted words in the NightandDay movie script.

## Requirements

1. Spark-shell 
2. SBT
3. ".txt" file of the document you want use for your Spark Word Count Project
4. Scala 


Note: I downloaded the movie script from the following link https://www.springfieldspringfield.co.uk/movie_script.php?movie=knight-and-day


## Commands
Open you Command Prompt Window and then type the following line of code.
## Step 1:
...
> spark-shell
...

When you type this line of code you shoud be able to see this in you screen: 



Note: If you don't something similar to the screen or if you see any things that say 'Spark' command not found then it means you have not set your enviroment variable properly. See the image below to set your Enviroment variable.











After setting up the System Variable and Path, Start a new command prompt and then try step 1 again. You should be good to go now :) .

## Step 2:
Now type these multiple lines of code in your command prompt once you succeed Step 1.
...
> val inputFile = sc.textFile("C:/44517/ConardSparkWordCount/AMSND.txt")
...

You should see this output after passing step 2.



Note: Inside the Parenthesis (""), you have to put your '.txt' files location.

## Step 3:
This line of code is seperating all those sentences by space and then filtering them and counting them.
...
> val topWordCount = inputFile.flatMap(str=>str.split(" ")).filter(!_.isEmpty).map(word=>(word,1)).reduceByKey(_+_).map{case (word, count) => (count, word)}.sortByKey(false)
...

You shoud get this once you pass the step 3.


## Step 4
This line of command will list you top 10 most repeated words in your '.txt' file.
...
>topWordCount.take(10).foreach(x=>println(x))
...


## Final Output
Your final output should look like this,


![step4output](https://user-images.githubusercontent.com/42624428/48320731-8154fb80-e5e2-11e8-8d45-f5d6b4a251d1.PNG)












The most frequently used word here in this file is a character '-'. It was repeated for 238 time and the second most used word is 'I'.




## Histogram
Using the data use collected from the Spark Word Count, I have creatd a Histogram.











## Note



If you get such error too that means you are using something wrong in your command just like. I put 'FlatMat' instead of 'FlatMap'.



----- Now you can amaze your friend by this magical tool :) -----