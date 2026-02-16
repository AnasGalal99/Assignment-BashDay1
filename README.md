## 1. Display all lines from /etc/passwd that contain the word "bash"
echo "Task1" > results.txt

grep "bash" /etc/passwd >> results.txt

## 2. Display the entire /etc/passwd file except the 5th line.
echo "Task2" >> results.txt

sed '5d' /etc/passwd >> results.txt

## 3. In /etc/passwd, replace every word "bash" with "bourne-again"
echo "Task3" >> results.txt

sed 's/bash/bourne-again/g' /etc/passwd >> results.txt

## 4. Print only the full name/comment field (usually field 5) of all users in the system from /etc/passwd.
echo "Task4" >> results.txt

awk -F: '{print $5}' /etc/passwd >> results.txt

## 5. Print the login (field 1), UID (field 3), and full name (field 5) of all users whose GID (field 4) is greater than 100.
echo "Task5" >> results.txt

awk -F: '$4 > 100 {print $1, $3, $5}' /etc/passwd >> results.txt

## 6. Print lines 10 through 20 from /etc/passwd Display line numbers alongside each line.
echo "Task6" >> results.txt

awk 'NR>=10 && NR<=20 {print NR, $0}' /etc/passwd >> results.txt

## 7. Calculate and display the sum of all GIDs (field 4) from the entire /etc/passwd file
echo "Task7" >> results.txt

awk -F: '{sum += $4} END {print sum}' /etc/passwd >> results.txt


