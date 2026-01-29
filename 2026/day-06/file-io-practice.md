# File Read and Write Practice (Day 06)

Today I practiced basic file read and write commands in Linux.
I created a text file and used simple commands to add and read text.

## Commands I used

1. touch notes.txt  
Created an empty file named notes.txt

2. echo "This is line 1" > notes.txt  
Wrote first line into the file (overwrite)

3. echo "This is line 2" >> notes.txt  
Added second line to the file

4. echo "This is line 3" | tee -a notes.txt  
Displayed text and added it to file at same time

5. cat notes.txt  
Read full file content

6. head -n 2 notes.txt  
Read first 2 lines of file

7. tail -n 2 notes.txt  
Read last 2 lines of file

## What I learned

- > is used to overwrite file  
- >> is used to append text  
- tee is useful to write and see output  
- cat, head, tail help read files fast
