# Difference to Other Projects

## A New Era Begins
With first ideas publicly emerging in early 2016, XEL has been the pioneer of Blockchain-based grid-computing. While many seemed to have doubts as to whether this technology can work at all, other projects quickly adopted this new idea, that we came up with, and started working on their interpretation of how a Blockchain based computation project should look like.  Now, we are thrilled that we could plant a seed in the Blockchain economy and cause an entirely new niche to develop - one that has never been thought of before.

## What is a Super-Computer
Before we can elaborate on the differences in the approaches adopted by other projects, we would like to define the term "supercomputer" first. A supercomputer, to us, is a general purpose computer that can prove significantly more computation power than what we can get out of a consumer-grade computer. One way to achieve that is to use the well-researched methodology of grid-computing; that is, the interconnection of many individual computers over a network to bundle their combined computational power into one, holistic pool of computing resources. One strict criterion is the applicability of those resources to a variety of different algorithmic problems. If you wanted to summarize that in three words, you could probably say, that a super-computer is defined by scalability, availability, and flexibility.

XEL's architecture reflects precisely that. Once you broadcast your task to the Blockchain, your task is available to all workers (nodes, that are running the miner to solve your tasks) at once. The bigger the network is, the more computation power is potentially available to you - it scales infinitely with the number of users on the platform. This computational power is available to you at any time, and the integrated programming language, ePL, allows you to code arbitrary tasks that solve problems in your particular research domain. XEL is a decentralized super-computer.

## The Direction of Other Projects
Since the development of a properly working programming language is an arduous task which only a few people master, it is understandable that other projects have chosen a different direction. Since allowing users to code in a traditional, Turing complete language is a no-no (\*) (halting problem, malleability, DOS attacks by resource exhausting code, ...), other projects typically focus on a variety of different yet fixed use-cases. That is, these projects code the algorithms themselves, and let the users provide the input. Don't get me wrong, these approaches (that might include rendering tasks, training neural networks, ...) are very helpful to have, yet I would consider them more rendering or machine-learning farms than true versatile super-computers.

(\*) (in case of Ethereum, a Turing complete language is fine since you have to deposit a certain amount of gas. Once you run out of gas, the execution terminates - deterministically at the same time for every node that executed that code snippet. This does not work for computation engines where people execute different (non-deterministic) parts of the program, and where it is desired to execute the entire code until the end.

## The Issue of Verification
Typically, the idea of a Blockchain-based super-computer is that you pay for others to solve your tasks and return the solution to you. Moreover, because you pay, you certainly want to make damn sure that you get the correct result. Well, XEL has solved that very issue pretty elegantly. The ePL language, as you will learn in the programming tutorial, has a beautiful property that allows the scientist, those who programmed the job, to introduce a verification function. If that verification is not passed, the result will not even be broadcasted by the network. All the solutions that you receive, therefore, can be seen as verified and correct.

This is not easy to do when you rely on specific use-cases like rendering or machine learning. Contrary to XEL, which runs the code natively, other projects typically use virtual machines (such as Docker) fitted with a third-party rendering engine or machine learning environment. These software tools are so complex that they do not only add a potential source of error, but they do not necessarily produce the same outputs when running on different machines. So if I render a picture on my computer, and you render the same picture on your computer, the two results might be just not binary identical. That makes verification very hard. Besides, there is no way to specify how the result should look like beforehand. You can tell XEL how to verify whether a result indeed evaluates a complicated formula to zero, but you have no chance to specify how a correctly rendered image would look like - you don't even know until you see it - leaving you just the option of probabilistic verification (as in verifying a small portion of the image). Malicious workers have a clear incentive here to only carry out a portion of the job (low quality or incomplete rendering, lousy training, ...), just enough, so it slips through current "probabilistic" verification methods, so they get paid.

In summary, work verification is a complex issue that XEL does not have, and that we think has yet to be solved by other projects. We are very interested to see how the first real solution will look like, since it is a tough issue to solve, and we hope that it won't include a **centralized watchdog**.


## Locking

Since rendering or training a DNN is a very resource intensive tasks, other projects usually have to "assign" individual tasks to individual nodes and only allow this one individual node to work on it. This is the right thing to do because nobody wants to work for 2 hours on a render job only to find out that someone else was quicker. However, this also has one potential drawback: what happens with very slow nodes or nodes that acquire a lock but leave? Such behavior can cause the task to run significantly longer than it would on the own (low grade) home computer. Also, in how many slices do you cut those jobs and how many locks do you offer? This number certainly limits the amount of computation power you can get out of it at all. If a task can only be cut into 100 individual pieces (because a smaller denomination would add too much overhead compared to the size of each piece), then you will only get 100 nodes working on your task at most - no matter if the network has 100 or 100,000,000 nodes active. XEL does not have this problem since the computational power of all 100,000,000 nodes would be available at once. This is possible due to how ePL is designed (one iteration of each program runs a few seconds at most) and how it allowed avoiding any locking at all (the search space is designed so large that it is unlikely that two nodes will work on the same task simultaneously).

## Hosting Databases, Websites, ...

Well, I am sure that there are certainly use-cases for that. But how is this supposed to calculate my monte carlo simulation? This certainly is no super-computer.