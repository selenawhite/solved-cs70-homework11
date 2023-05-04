Download Link: https://assignmentchef.com/product/solved-cs70-homework11
<br>
Random Cuckoo Hashing

Cuckoo birds are parasitic beasts. They are known for hijacking the nests of other bird species and evicting the eggs already inside. Cuckoo hashing is inspired by this behavior. In cuckoo hashing, when we get a collision, the element that was already there gets evicted and rehashed.

We study a simple (but ineffective, as we’ll see) version of cuckoo hashing, where all hashes are random. Let’s say we want to hash <em>n </em>pieces of data <em>D</em><sub>1</sub><em>,D</em><sub>2</sub><em>,…,D<sub>n </sub></em>into <em>n </em>possible hash buckets labeled 1<em>,…,n</em>. We hash the <em>D</em><sub>1</sub><em>,…,D<sub>n </sub></em>in that order. When hashing <em>D<sub>i</sub></em>, we assign it a random bucket chosen uniformly from 1<em>,…,n</em>. If there is no collision, then we place <em>D<sub>i </sub></em>into that bucket. If there is a collision with some other <em>D<sub>j</sub></em>, we evict <em>D<sub>j </sub></em>and assign it another random bucket uniformly from 1<em>,…,n</em>. (It is possible that <em>D<sub>j </sub></em>gets assigned back to the bucket it was just evicted from!) We again perform the eviction step if we get another collision. We keep doing this until there is no more collision, and we then introduce the next piece of data, <em>D<sub>i</sub></em><sub>+1 </sub>to the hash table.

<ul>

 <li>What is the probability that there are no collisions over the entire process of hashing <em>D</em><sub>1</sub><em>,…,D<sub>n </sub></em>to buckets 1<em>,…,n</em>? What value does the probability tend towards as <em>n </em>grows very large?</li>

 <li>Assume we have already hashed <em>D</em><sub>1</sub><em>,…,D<sub>n</sub></em><sub>−1</sub>, and they each occupy their own bucket. We now introduce <em>D<sub>n </sub></em>into our hash table. What is the expected number of collisions that we’ll see while hashing <em>D<sub>n</sub></em>? (<em>Hint</em>: What happens when we hash <em>D<sub>n </sub></em>and get a collision, so we evict some other <em>D<sub>i </sub></em>and have to hash <em>D<sub>i</sub></em>? Are we at a situation that we’ve seen before?)</li>

</ul>

<h1>2          Markov’s Inequality and Chebyshev’s Inequality</h1>

A random variable <em>X </em>has variance var(<em>X</em>) = 9 and expectation E[<em>X</em>] = 2. Furthermore, the value of <em>X </em>is never greater than 10. Given this information, provide either a proof or a counterexample for the following statements.

<ul>

 <li>P[<em>X </em>≤ 1] ≤ 8<em>/</em></li>

 <li>P[<em>X </em>≥ 6] ≤ 9<em>/</em></li>

 <li>P[<em>X </em>≥ 6] ≤ 9<em>/</em></li>

</ul>

<h1>3          Easy A’s</h1>

A friend tells you about a course called “Laziness in Modern Society” that requires almost no work. You hope to take this course next semester to give yourself a well-deserved break after working hard in CS 70. At the first lecture, the professor announces that grades will depend only on two homework assignments. Homework 1 will consist of three questions, each worth 10 points, and Homework 2 will consist of four questions, also each worth 10 points. He will give an A to any student who gets at least 60 of the possible 70 points.

However, speaking with the professor in office hours you hear some very disturbing news. He tells you that, in the spirit of the class, the GSIs are very lazy, and to save time the grading will be done as follows. For each student’s Homework 1, the GSIs will choose an integer randomly from a distribution with mean <em>µ </em>= 5 and variance <em>σ</em><sup>2 </sup>= 1. They’ll mark each of the three questions with that score. To grade Homework 2, they’ll again choose a random number from the same distribution, independently of the first number, and will mark all four questions with that score.

If you take the class, what will the mean and variance of your total class score be? Use Chebyshev’s inequality to conclude that you have less than a 5% chance of getting an A when the grades are randomly chosen this way.

<h1>4          Confidence Interval Introduction</h1>

We observe a random variable <em>X </em>which has mean <em>µ </em>and standard deviation <em>σ </em>∈ (0<em>,</em>∞). Assume that the mean <em>µ </em>is unknown, but <em>σ </em>is known.

We would like to give a 95% confidence interval for the unknown mean <em>µ</em>. In other words, we want to give a random interval (<em>a</em><em>,b</em>) (it is random because it depends on the random observation <em>X</em>) such that the probability that <em>µ </em>lies in (<em>a</em><em>,b</em>) is at least 95%.

We will use a confidence interval of the form (<em>X </em>−<em>ε</em><em>,X </em>+<em>ε</em>), where <em>ε </em><em>&gt; </em>0 is the width of the confidence interval. When <em>ε </em>is smaller, it means that the confidence interval is narrower, i.e., we are giving a more <em>precise </em>estimate of <em>µ</em>.

<ul>

 <li>Using Chebyshev’s Inequality, calculate an upper bound on P{|<em>X </em>−<em>µ</em>| ≥ <em>ε</em>}.</li>

 <li>Explain why P{|<em>X </em>−<em>µ</em>| <em>&lt; </em><em>ε</em>} is the same as P{<em>µ </em>∈ (<em>X </em>−<em>ε</em><em>,X </em>+<em>ε</em>)}.</li>

 <li>Using the previous two parts, choose the width of the confidence interval <em>ε </em>to be large enough so that P{<em>µ </em>∈ (<em>X </em>−<em>ε</em><em>,X </em>+<em>ε</em>)} is guaranteed to exceed 95%.</li>

</ul>

[Note: Your confidence interval is allowed to depend on <em>X</em>, which is observed, and <em>σ</em>, which is known. Your confidence interval is not allowed to depend on <em>µ</em>, which is unknown.]

<ul>

 <li>The previous three parts dealt with the case when you observe one sample <em>X</em>. Now, let <em>n </em>be a positive integer and let <em>X</em><sub>1</sub><em>,…,X<sub>n </sub></em>be i.i.d. samples, each with mean <em>µ </em>and standard deviation <em>σ </em>∈ (0<em>,</em>∞). As before, assume that <em>µ </em>is unknown but <em>σ </em>is known.</li>

</ul>

Here, a good estimator for <em>µ </em>is the <em>sample mean X</em>¯ := <em>n</em><sup>−1 </sup><sub>∑</sub><em><sup>n</sup><sub>i</sub></em><sub>=1 </sub><em>X<sub>i</sub></em>. Calculate the mean and variance of <em>X</em>¯.

<ul>

 <li>We will now use a confidence interval of the form (<em>X</em>¯ −<em>ε</em><em>,X</em>¯ +<em>ε</em>) where <em>ε </em><em>&gt; </em>0 again represents the width of the confidence interval. Imitate the steps of (a) through (c) to choose the width <em>ε </em>to be large enough so that P{<em>µ </em>∈ (<em>X</em>¯ −<em>ε</em><em>,X</em>¯ +<em>ε</em>)} is guaranteed to exceed 95%.</li>

</ul>

To check your answer, your confidence interval should be <em>smaller </em>when <em>n </em>is larger. Intuitively, if you collect more samples, then you should be able to give a more <em>precise </em>estimate of <em>µ</em>.