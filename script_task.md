#!/usr/bin/bash

# 1. Name and Age

echo "What is your name?"
read name

echo "What is your age?"
read age

birth_year=$((2023 - $age))

echo "Hello $name! You were born in $birth_year."

# 2. creating a directory with the name inputed

mkdir $name && cd $name

cd ..

# 3. Listing all files in the current directory, sorted by file size

du -sh * | sort -hr

# 4. Counting the number of files in the current directory and output the result.

find . -maxdepth 1 -type f | wc -l

# 5. Taking a list of numbers as input from the user and output the sum of those numbers

echo "Enter numbers separated by space"
read -a arr
sum=0
for i in "${arr[@]}"
do
   sum=$((sum+i))
done
echo "The sum is $sum"

# 6. Output a random number between 1 and 100

echo $((RANDOM % 100 + 1))

# 7. 
mkdir bakup-dir
mv -b script_task.sh /bakup-dir
# 8. This command below will check whether the google website is up or down and output the status message from the web server. If the website is up, you will see a status code of 200 OK. If the website is down, you will see a different status code.

curl -Is http://www.google.com | head -1

# 9. The formula used is fahrenheit = (celsius * 1.8) + 32.

read -p "Enter degree celsius temperature: " C
F=$((180*$C/100+32))
echo The temperature $C in Fahrenheit is $F

# 10. To reverse a sentence in Linux script command
# This will prompt the user to enter a sentence and then output the sentence in reverse order. You can also use other commands such as awk, sed, or write a shell script to reverse input one-by-one.

echo "Enter a sentence:" 
read sentence 
echo $sentence | rev
