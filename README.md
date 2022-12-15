# Find--S-algorithm
The find-S algorithm is a basic concept learning algorithm in machine learning. The find-S algorithm finds the most specific hypothesis that fits all the positive examples. We have to note here that the algorithm considers only those positive training example.



import csv
a = []
with open('enjoysport.csv', 'r') as csvfile:
 for row in csv.reader(csvfile):
 a.append(row)
 print(a)
print("\n The total number of training instances are : ",len(a))
num_attribute = len(a[0])-1
print("\n The initial hypothesis is : ")
hypothesis = ['0']*num_attribute
print(hypothesis)
for i in range(0, len(a)):
 if a[i][num_attribute] == 'yes':
 for j in range(0, num_attribute):
 if hypothesis[j] == '0' or hypothesis[j] == a[i][j]:
 hypothesis[j] = a[i][j]
 else:
 hypothesis[j] = '?'
 print("\n The hypothesis for the training instance {} is : 
\n" .format(i+1),hypothesis)
print("\n The Maximally specific hypothesis for the training 
instance is ")
print(hypothesis)


Data Set:
sunny warm normal strong warm same yes
sunny warm high strong warm same yes
rainy cold high strong warm change no
sunny warm high strong cool change yes

Output: 
The Given Training Data Set 
['sunny', 'warm', 'normal', 'strong', 'warm', 'same', 'yes']
['sunny', 'warm', 'high', 'strong', 'warm', 'same', 'yes']
['rainy', 'cold', 'high', 'strong', 'warm', 'change', 'no']
['sunny', 'warm', 'high', 'strong', 'cool', 'change', 'yes']
The total number of training instances are : 4
The initial hypothesis is : 
['0', '0', '0', '0', '0', '0']
The hypothesis for the training instance 1 is : 
['sunny', 'warm', 'normal', 'strong', 'warm', 'same']
The hypothesis for the training instance 2 is : 
['sunny', 'warm', '?', 'strong', 'warm', 'same']
The hypothesis for the training instance 3 is : 
['sunny', 'warm', '?', 'strong', 'warm', 'same']
The hypothesis for the training instance 4 is : 
['sunny', 'warm', '?', 'strong', '?', '?']
The Maximally specific hypothesis for the training instance is 
['sunny', 'warm', '?', 'strong', '?', '?'
