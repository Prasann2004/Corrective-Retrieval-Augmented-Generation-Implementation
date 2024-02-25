# Corrective-Retrieval-Augmented-Generation-Implementation
A simple python implementation of [Corrective Retrieval Augmented Generation](https://arxiv.org/abs/2401.15884) .

Algorithm :
Require :E (Retrieval Evaluator), W (Query Rewriter), G (Generator)
Input :x (Input question), D = {d1, d2, ..., dk} (Retrieved documents)
Output :y (Generated response)
1 scorei = E evaluates the relevance of each pair (x, di), di ∈ D
2 Confidence = Calculate and give a final judgment based on {score1, score2, ...scorek}
// Confidence has 3 optional values: [CORRECT], [INCORRECT] or [AMBIGUOUS]
3 if Confidence == [CORRECT] then
4   Internal_Knowledge = Knowledge_Refine(x, D)
5   k = Internal_Knowledge
6 else if Confidence == [INCORRECT] then
7   External_Knowledge = Web_Search(W Rewrites x for searching)
8   k = External_Knowledge
9 else if Confidence == [AMBIGUOUS] then
10   Internal_Knowledge = Knowledge_Refine(x, D)
11   External_Knowledge = Web_Search(W Rewrites x for searching)
12   k = Internal_Knowledge + External_Knowledge
13 end
14 G predicts y given x and k


![image](https://github.com/Prasann2004/Corrective-Retrieval-Augmented-Generation-Implementation/assets/83667133/e894c778-cf01-4e94-888c-1a7b3ea102ca)

