# Question
Alice has an even number of N beads, and each bead has a number from 1 to N painted on it. She would like to make a necklace out of all the beads, with a special requirement: any two beads next to each other on the necklace must sum to a prime number. Alice needs your help to calculate how many ways it is possible to do so.
For example:
<pre>
	N = 4
	There are two possible ways to build the necklace. Note that the last bead connects to the first bead.
	1 2 3 4
	1 4 3 2</pre>
Note: The necklace should be unique. For example: 1 2 3 4 is the same as 2 3 4 1 and 3 4 1 2 and 4 1 2 3.

# Answer

1. Circular -> 1,2,3,4 == 2,3,4,1 == 3,4,1,2 == 4,1,2,3
2. Must alternate even / odd. (odd + odd) == even == (even + even) and any number that is even is not a prime. (excl. 2, which we cannot sum anyway).
3. Must be of even length -> This is because it must alternate. (This is in the question specification)
4. The inverse is equivalent -> 1,2,3 == 3,2,1. (Wearing the necklace from the other-side of the entrance)

* There are n! linear permutations
* There are (n!/n) == (n-1)! circular permutations. (Because we can turn the necklace n iterations and it's still the same necklace)
* There are (n-1)!/2 permutations w.r.t. each circular permutation having a reflection.
  * Note: The actual question examples doesn't take this into consideration. So I will not consider this.
  * e.g. The first example: 1 2 3 4 is the equivalent to 4 3 2 1 if necklace is worn from the inverted side.
  * The second example: 1 4 3 2 is a circular equivalent to 4 3 2 1.
  * Therefore the provided example answer is incorrect for N=4, because they are both the same permutation
	
Information on circular permutations from:  N. F. Taussig on <a href='https://math.stackexchange.com/a/2395407'>Stack Exchange </a>