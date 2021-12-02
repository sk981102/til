# Bayesian Learning 


### How is the bayesian approach different from traditional machine learning?

The simple answer is that bayesian learning takes prior knowledge from the data when calculating posterior of individual observations. However, initially, this fundamental concept created confusion as the traditional ML algorithms also utilize data; the neural network-based algorithms use conditional probability at each layer. 

Simply put, the Bayesian can produce probabilistic predictions over several hypotheses rather than assigning each instance to a single hypothesis. 

The difference became crystalized when delving into the pros and cons of the bayesian approach compared to the traditional ML algorithms.

### Pros and Cons of Bayesian Approach
- Pros
    - new observations or evidence can incrementally improve the model. Whereas traditional machine learning algorithms, you need to train the whole data set
    - ability to express uncertainty
        - "If we consider a simple scenario where we have to predict which team is going to win the cricket world cup this year using the past performance of each team, then classical machine learning techniques can be used to predict only the winning team, whereas Bayesian learning can be used to determine the probability of each team winning the world cup."

- Cons
    - difficulty in acquiring the initial knowledge
    - significant computation cost
        - the algorithm has to compute the posterior probability for every hypothesis (can be extremely costly for high dimensional data) for each instance
        - can be improved by **Gibbs Sampling**, which randomly selectly hypothesis and use those selected P(h|D) to predict new instance


### Models using the Bayesian Approach
- **NAIVE BAYES**

- **Bayesian with MAP**

- **Bayesian with MCMC**

- **Bayesian Network**


### Resources
https://wso2.com/blog/research/comparing-bayesian-and-classical-learning-techniques/

https://docs.google.com/presentation/d/e/2PACX-1vQ7oPr3nmaQtpeMKbIP5pAoug6C7V5q6C5i4J1HRNzTv_kfrgIqIMy6E3kMH4YsaLOrTBzR3wAVDfCf/pub?start=false&loop=false&delayms=3000&slide=id.gc762e611a2_0_817