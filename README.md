# Introduction
Machine learning is nowadays a key topic in the fast expanding field of artificial intelligence. More than that, machine learning provides several solutions for different fields such as finance, recommendation systems (Netflix as a example) or beloved short reels with reinforcement learning for social media users. 

It is not only interesting how machine learning algorithm works, rather the complexity of understanding and implementation to derive meaningful insights. While modern modelling provides a fast solution nowadays with scikit.learn as an example, understanding still remains necessary.  

# Objective 
This is the first part of a longer planned series for Hidden Markov Models. The objective is not to use precoded libraries like hmmlearn for modelling. Rather the implementation from scratch and creation of a own HMM-class with NumPy only is the primary goal to improve my own coding experience. 
Probabilistic modelling, math and derive insights from a modell are also several objectives. 

As an example the Nasdaq-100 is used because the state classification or distinction in financial time series is a common topic.

# Key insights 

If one considers financial time series as a system that possesses a theoretical equilibrium, then it should be represented by a hidden Markov model. Ultimately, an equilibrium should be reached in the Markov chain after a sufficient number of iterations.
This is evident in the presented transition matrices. While the original class used 100 iterations with a break at 50 iterations, the hmmlearn class only used 10 iterations. The differences are marginal. This speaks, firstly, to the correct implementation within the class itself.

<img width="1262" height="528" alt="image" src="https://github.com/user-attachments/assets/c0211b20-9aaa-4c0e-a850-2f966756a1a6" />

On the other hand, the transition matrix offers an interpretation of the modeled system. 
While "0" represents bear markets, 1 represents bull markets. Despite the dot-com bubble, the system tends to remain in state 1. This is evident from the high 1 -> 1 probability of 0.7.

Plot of the price chart with the smooted probabilities 

<img width="1296" height="682" alt="image" src="https://github.com/user-attachments/assets/969ab25d-2356-4f0b-8b1c-4fc504915f8e" />



# Challenges 
Challenges are divided into its different groups. 

- Coding:
  - Working with classes to create objectes was a new experience and not a key topic of my previous projects. The challenge was the whole implementation from scratch with numpy only for the main logic.
 
- Math:
  - As an industrial engineer and my last math modules dated back to 2021, the reading and understanding of mathematical formulas needed more time than usual.

- Probability:
  - Probability theory was until this project not a part of my knowledge since courses or something else were not visited directly. Especially scaling or normalization to get the desired probability measurement was a theoretical challenge.   


# Lessons learned and lookahead 
I never fully completed a ML/DS course. My knowledge is mainly based on trial and error as well as research.
For this reason, one of my long-term goals is to gain more confidence and competence in machine learning, probability theory, and data science. After all, theory is a good foundation for everything else.

While this project/notebook is for demonstrating purposes only and the results speaks for themselves, a implementation of discrete hmms for trading strategys is not a valid approach. However, the next part consists of the creation of hidden markov models with gaussian emissions. 

### References 

"zero with dot" with a really nice example of a own written HMM-class. His work was a really good coding inspiration.\
https://zerowithdot.com/hidden-markov-model/

Mark Stamp and his introduction into HMMs.\
https://www.cs.sjsu.edu/~stamp/RUA/HMM.pdf

Rabiner and his tutorial for HMMs.\
https://www.cs.sjsu.edu/~stamp/RUA/Rabiner.pdf
