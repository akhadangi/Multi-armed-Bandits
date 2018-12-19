# Multi-armed-Bandits
In this notebook several classes of multi-armed bandits are implemented. This includes epsilon greedy, UCB, Linear UCB (Contextual bandits) and Kernel UCB. Some of the well cited papers in this context are also implemented.

In the part 1, Python classes EpsGreedy and UCB for both E-Greedy and UCB learners are implemented. Tie-breaking in play() should be completed uniformly-at-random among value-maximising arms.

A breakthrough was made in this context when it was realised that MABs can be evaluated offline or off policy. In part 2, the third algorithm described in the following paper is implemented:

Lihong Li, Wei Chu, John Langford, Robert E. Schapire, ‘A Contextual-Bandit Approach to Personalized News Article Recommendation’, in Proceedings of the Nineteenth International Conference on World Wide Web (WWW 2010), Raleigh, NC, USA, 2010.
https://arxiv.org/pdf/1003.0146.pdf

In part 3, contextual bandits---LinUCB is implemented. This will address the section 3.1 of the WWW’2010 paper with disjoint linear models (Algorithm 1).

After the definitions above provided, EpsGreedy, UCB and LinUCB are evaluated in off-policy mode in part 4 using the dataset uploaded. The following details may be helpful to understand the structure of dataset. 

• 10,000 lines (i.e., rows) corresponding to distinct site visits by users—events in the language of this part;
• Each row comprises 102 space-delimited columns of integers:
– Column 1: The arm played by a uniformly-random policy out of 10 arms (news articles);
– Column 2: The reward received from the arm played—1 if the user clicked 0 otherwise; and
– Columns 3–102: The 100-dim flattened context: 10 features per arm (incorporating the content of the article and its match with the visiting user), first the features for arm 1, then arm 2, etc. up to arm 10.

The running per-round cumulative reward for T = 1..800 as a function of round T, all on one overlayed plot is also plotted in this section. Next, a grid-search based strategy to select the α hyperparameter in LinUCB is devised and implemented.

And finally, in part 5, the kernel methods multi-armed bandits, KernelUCB (with online updates) that is Algorithm 1 of this paper:

Michal Valko, Nathan Korda, R´emi Munos, Ilias Flaounas, and Nello Cristianini, ‘Finite-time analysis of kernelised contextual bandits.’ In Proceedings of the Twenty-Ninth Conference on Uncertainty in Artificial Intelligence (UAI’13), pp. 654-663. AUAI Press, 2013.
https://arxiv.org/ftp/arxiv/papers/1309/1309.6869.pdf

is implemented. Next, a MAB hyperparameter setting and with choice of the Gaussian/RBF kernel, a plot like in Part 4(a) demonstrating competitive performance relative to LinUCB is demonstrated. Note this kernel is imported as rbf kernel in the given notebook and beware that while the RBF’s parameter is also called ‘gamma’ it is distinct to the ‘gamma’ in KernelUCB.
