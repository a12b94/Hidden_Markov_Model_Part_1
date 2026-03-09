# Introduction
Machine learning is nowadays a key topic in the fast expanding field of artificial intelligence. More than that, machine learning provides several solutions for different fields such as finance, recommendation systems (Netflix as a example) or beloved short reels with reinforcement learning for social media users. 

It is not only interesting how machine learning algorithm works, rather the complexity of understanding and implementation to derive meaningful insights. While modern modeling provides a fast solution nowadays with scikit.learn as an example, understanding still remains necessary.  

# Objective 
This is the first part of a longer planned series for Hidden Markov Models. The objective is not to use precoded libraries like hmmlearn for modelling. Rather the implementation from scratch and creation of a own HMM-class with NumPy only is the primary goal to improve my own coding experience. 
Probabilistic modeling, math and derive insights from a modell are also several objectives. 

As an example the Nasdaq-100 is used because the state classification or distinction in financial time series is a common topic.

# Key insights 

If one considers financial time series as a system that possesses a theoretical equilibrium, then it should be represented by a hidden Markov model (
However, that's not the main criterion. After all, the key characteristic of a Markov chain is that the next state depends only on the current state. But an equilibrium or "steady state" should exist.). Ultimately, an equilibrium should be reached in the Markov chain after a sufficient number of iterations.
This is evident in the presented transition matrices. While the original class used 100 iterations with a break at 50 iterations, the hmmlearn class only used 10 iterations. The differences are marginal. This speaks, firstly, to the correct implementation within the class itself.

<img width="1262" height="528" alt="image" src="https://github.com/user-attachments/assets/c0211b20-9aaa-4c0e-a850-2f966756a1a6" />

On the other hand, the transition matrix offers an interpretation of the modeled system. 
While "0" represents bear markets, 1 represents bull markets. Despite the dot-com bubble, the system tends to remain in state 1. This is evident from the high 1 -> 1 probability of 0.7 or 0.69 respectively. Furthermore, it can be interpreted that transitions from bullish to bearish do not occur very frequently, while transitions from bearish to bullish are comparatively more probable. This means that, despite the dot-com bubble, the Nasdaq tends to enter bullish territory more often and remain there.


To provide a graphical impression of the classification, the two price charts from the Nasdaq are shown. Smoothed probabilities were used for the classification. Green in this case represents "bull-regimes", while salmon is used to visualize "bear-regimes". At first glance, there is hardly any difference to the custom-written class and to hmmlearn. Both models seem to reproduce the regimes well. In particular, the rapid "V-reversals" are captured well. 

<img width="1296" height="682" alt="image" src="https://github.com/user-attachments/assets/969ab25d-2356-4f0b-8b1c-4fc504915f8e" />

Furthermore, the negative log likelihood is very similar. It can be seen that, for example, more iterations in the EM algorithm do not necessarily lead to a higher log likelihood.
- The negative log-likelihood from the own written class is: -1315.6970262095192
- The negative log-likelihood from the hmmlearn package is: -1315.753264634938

However, a graphical assessment is insufficient. Therefore, as a final point, the confusion matrix for both models is presented. This is typically used for models that solve classification problems.

<img width="1258" height="528" alt="image" src="https://github.com/user-attachments/assets/fa59185a-601c-46d4-996e-c92fc2dc83a5" />

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

While this project/notebook is for demonstrating purposes only and the results speaks for themselves, a implementation of discrete hmms for positional trading strategys is not a valid approach. However, the next part consists of the creation of hidden markov models with gaussian emissions. 
The result should look like the next image shown.

<img width="1164" height="528" alt="image" src="https://github.com/user-attachments/assets/5289ca29-a536-4c87-a7ff-48437d432ff1" />

### References 

"zero with dot" with a really nice example of a own written HMM-class. His work was a really good coding inspiration.\
https://zerowithdot.com/hidden-markov-model/

Mark Stamp and his introduction into HMMs.\
https://www.cs.sjsu.edu/~stamp/RUA/HMM.pdf

Rabiner and his tutorial for HMMs.\
https://www.cs.sjsu.edu/~stamp/RUA/Rabiner.pdf
