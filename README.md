<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: SARAVANA KUMAR M            </h3>
<h3>Register Number: 212222230133           </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
Score: 643  Solution :  8RzF:oG ]%;CPORRMe!zGvk<br>
Score: 609  Solution :  8RzF:oG ]%;CPqRRMe!zGvk<br>
Score: 604  Solution :  8RzF:oG ]%;CPqRRMe!zGqk<br>
Score: 594  Solution :  8RzF:oG ]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
....................................................<br>
..................................................<br>
................................................<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 0  Solution :  Artificial Intelligence<br>

<h2>PROGRAM:</h2>
<HR>

```
import random
import string

# Generate a random solution by creating a list of random characters
# with the same length as the given answer
def generate_random_solution(answer):
    l = len(answer)  # Find the length of the answer
    return [random.choice(string.printable) for _ in range(l)]

# Evaluate how close the solution is to the answer by calculating the difference
def evaluate(solution, answer):
    target = list(answer)
    diff = 0
    for i in range(len(target)):
        s = solution[i]
        t = target[i]
        # Calculate the difference in ASCII values and sum up the absolute difference
        diff += abs(ord(s) - ord(t))
    return diff

# Mutate the solution by randomly changing one character
def mutate_solution(solution):
    ind = random.randint(0, len(solution) - 1)
    solution[ind] = random.choice(string.printable)
    return solution

# Hill Climbing algorithm to find the closest solution to the given answer
def SimpleHillClimbing():
    answer = "Artificial Intelligence"
    best = generate_random_solution(answer)
    best_score = evaluate(best, answer)
    
    while True:
        print("Score:", best_score, " Solution:", "".join(best))  
        
        if best_score == 0:  # If the score is zero, we found the exact match
            break
        
        # Create a new solution by mutating the current best solution
        new_solution = mutate_solution(list(best))
        score = evaluate(new_solution, answer)   
        
        if score < best_score:  # If the new solution is better, update the best solution
            best = new_solution
            best_score = score

# Run the Simple Hill Climbing algorithm
SimpleHillClimbing()
```

<H2>OUTPUT:</H2>
<HR>

![image](https://github.com/user-attachments/assets/5401a3a5-c1d9-4b1d-b20c-74ec0ed7f391)

![image](https://github.com/user-attachments/assets/c0c88332-00cb-41a7-ad38-2fd405c3233b)

<H2>RESULT:</H2>

Thus, the program for Simple Hill Climbing Algorithm executed successfully.

