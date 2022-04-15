# Big-O Notation

## What is Big-O Notation?
  - Big-O() notation describes the efficiency of code. 
  - Between the parentheses, we write some algebraic expression. the  algebraic will be always a mathmatical function.
  - e.g. of Big-O --> O(log<sub>n</sub>), O(n), O(1), O(n<sup>2</sup>), O(n<sup>3</sup>)
  - The **n** represent the length of the inputs.

```
    Function decode(input): # input is a string
        create output string
        for each letter in input:
            get new_letter from letter's location in cipher
            add new_letter to output
        return output
```
  - The piece of code above will be explain like this:
    - Creating the variable *output* and return it, it will happen once every time the function run, So we represent that like this: **Big-O(2)**
    - Now, the lines inside the for loop have to get run for every letter in the input
    - So, we can add 2*n, since n is the number of letters in our string, and we have two lines hat need to get run for each one.
    - And for each time we need to do a computation to get the next letter. So we need to add 1 before in 3*n
    - So the Big-O for this code will be **Big-O(3n + 2)**
    - For example, if the input string had 10 letters the calculation would look like this:
      - 3*10 + 2 = 32
      - And to get the efficiency, we need to multiply the 32 by the time that the code needs to run.

  - To be more precise, we should go deep into this piece of code to understand the efficiency and Big-O 
    - Think in this line `get new_letter from letter's location in cipher`, this line will take a different number of computation based on cipher algorithm.
    - So, cipher will take each letter from the string and compare it with each letter in cipher.
    - So, that will add more complexity to the code, that's mean we will do 26 check for each letter.
    - The Big-O now will be more complex Big-O((3+26)n + 2)
    - So if we have a word contain 10 letters, we need 292 step to solve it
    - And if we have a word contain 1 million letter the steps we need to solve it would be 29 million.


# Worst case and Approximation

  - What is the worst case in cipher when it compare each letter?
    - The worst case will be reaching the last letter *z*.
    - But in the real world we don't looping through the whole letters. The approximate looping will be 13.
    - So, the Big-O would be Big-O((13+3)n + 2) --> Big-O(16n + 2)
  - In real interview we wouldn't say  "The Big-O of this code well be Big-O(16n + 2)".
  - In real interview we use approximation, and we say this code will be Big-O(n)


## Examples of Big-O

<p style="color:green; font-size:18px">
    input manatees: a list of "manatees", where one manatee is represented by a dictionary
    a single manatee has properties like "name", "age", et cetera </br>
    n = the number of elements in "manatees"</br>
    m = the number of properties per "manatee" (i.e. the number of keys in a manatee dictionary)</br>
    manatees = [</br>
        "manatee1":{</br>
            "name": ,</br>
            "age":</br>
        },</br>
        "manatee2":{</br>
            "name": ,</br>
            "age":</br>
        }</br>
    ]</br>
</p>


```
def example1(manatees):
    for manatee in manatees:
        print manatee['name']
```
<span>Ex1: Big-O(n) for time, Big-O(1) for space </span>


```
def example2(manatees):
    print manatees[0]['name']
    print manatees[0]['age']
```
<span>Ex2: Big-O(1) for time, Big-O(1) for space </span>


```
def example3(manatees):
    for manatee in manatees:
        for manatee_property in manatee:
            print manatee_property, ": ", manatee[manatee_property]
```
<span>Ex3: Big-O(n<sup>2</sup>) for time, Big-O(1) for space </span>


```
def example4(manatees):
    oldest_manatee = "No manatees here!"
    for manatee1 in manatees:
        for manatee2 in manatees:
            if manatee1['age'] < manatee2['age']:
                oldest_manatee = manatee2['name']
            else:
                oldest_manatee = manatee1['name']
    print oldest_manatee
```
<span>Ex4: Big-O(n<sup>2</sup>) for time, Big-O(1) for space </span>


### Here are the answers and explanations:

  - Example 1
     - We iterate over every manatee in the manatees list with the for loop. Since we're given that manatees has n elements, our code will take approximately O(n) time to run.

  - Example 2
     - We look at two specific properties of a specific manatee. We aren't iterating over anything - just doing constant-time lookups on lists and dictionaries. Thus the code will complete in constant, or O(1), time.

  - Example 3
     - There are two for loops, and nested for loops are a good sign that you need to multiply two runtimes. Here, for every manatee, we check every property. If we had 4 manatees, each with 5 properties, then we would need 5+5+5+5 steps. This logic simplifies to the number of manatees times the number of properties, or O(nm).

  - Example 4
     - Again we have nested for loops. This time we're iterating over the manatees list twice - every time we see a manatee, we compare it to every other manatee's age. We end up with O(nn), or O(n^2) (which is read as "n squared").

    - Throughout the course, you can reference the Big-O Cheat Sheet to keep track of time complexities for many of the algorithms and data structures we study.