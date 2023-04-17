# CS4365-Project3
Implementing a theorem prover for a clause logic using the resolution 
principle. Well-formed sentences in this logic are clauses. Instead of using the 
implicative form, we will be using the disjunctive form, since this form is more suitable for automatic manipulation.

To prove that a clause is valid using the resolution method, we attempt to show that the negation of the clause is unsatisfiable, meaning it cannot be true under any truth assignment. This is done using the following algorithm:
1. Negate the clause and add each literal in the resulting conjunction of literals to the 
set of clauses already known to be valid.
2. Find two clauses for which the resolution rule can be applied. Change the form of the 
produced clause to the standard form and add it to the set of valid clauses.
3. Repeat 2 until False is produced, or until no new clauses can be produced. If no new 
clauses can be produced, report failure; the original clause is not valid. If False is 
produced, report success; the original clause is valid.

Your program should take exactly one argument from the command line:
The path to a .kb file that contains the initial KB and the clause whose validity we want to test. 
Your program should adhere to the following policy:
• If the negated version of the clause to validate has ANDs, your program should split it into 
separate clauses. These clauses should be added to the KB from left to right order.
1. a contradiction is found (in which case ’Contradiction’ should be added to the KB) or 
2. all possible resolutions have been performed.
• Redundant generated clauses should not be added to the KB. A clause is redundant if the KB
contains another clause which is logically equivalent to it.
• Clauses that evaluate to True should not be added to the KB.
• Generated clauses should not have redundant (repeated) literals

To Run
python main.py demo1.in.txt