Homework 2
=======
Monday, October 15, 2018

## Question 1

From your home directory, make a folder called 'lower_folder' within a folder called 'upper_folder'. Go into upper_folder and change the name of lower_folder to 'renamed_folder'. Nagivate into renamed_folder and change the name of rename_folder to renamed_again. Make another folder called 'where_is_this_folder', do you think that this folder has been made in ~/upper_folder/rename_folder or ~/upper_folder/rename_again? Delete all the folders that were created when done. 


```bash
cd ~/
mkdir upper_folder
mkdir upper_folder/lower_folder
cd upper_folder
mv lower_folder renamed_folder
cd renamed_folder
mv ../renamed_folder ../renamed_again
mkdir where_is_this_folder
cd ..
tree
cd ~/
rmdir -p upper_folder/renamed_again/where_is_this_folder
```

The file 'test' is under ~/upper_folder/rename_again

### Question 1 Comments:
Hi, this was very well done, just one thing to caution is that if your directories contain any files the rmdir operation will fail. If that is the case you can simply do rm -rf upper_folder, the -f switch forces the delete without posting prompts. I would be just careful with using the -f option along with wildcards i.e. * as this can lead to wiping out everything in your working directory. 
Also if you wanted test to be in your directory you should have done touch ~/upper_folder/renamed_again/test

## Question 2

Make an example matrix and use built in example dataframe:

```R
myvector <- 101:112
mymatrix <- matrix(myvector, ncol = 3)

mydf <- head(mtcars) 
```

Access the second column of the matrix and the dataframe. Are there different ways to do the same thing? 

```R
mymatrix[,2]
mydf[,2]
mydf[[2]]  # or you can use
mydf[2] # or you can use if you want the headers
```

Access the second value of the second column directly from the original matrix or dataframe.  Are there different ways to do the same thing? 

```R
mymatrix[6]
mymatrix[2,2] # alternative
mydf[2,2]
```

## Question 3


Make a public folder, then make a short bash script in that folder. Here is an example:

```bash
#!/bin/sh
# This is a comment!
echo Hello World        # This is a comment, too!
```

Change the permission so that the person beside you can run the script. What is the minimum amount of permission that you can give and still for others to be able to run it?

```bash
mkdir /pub/jje/ee282/qingda
cd /pub/jje/ee282/
chmod 755 qingda
cd qingda
touch mytest
vim mytest
chmod 555 mytest
```

This might depend on if your classmate is in the same group as you are. Also if you do the chmod at the end the permission just have to be 050 for someone else in your group to run the script. 
