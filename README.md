# Comments-on-DPBalance

Review 1
Double blind policy: Does this paper conform to the double-blind submission policy? If not, please provide explanations with clear evidence in the confidential TPC comments section of the review.
Yes, this paper conforms to the double-blind policy (1)

Paper Summary: Please summarize the paper in your own words.
This paper proposes a privacy budget scheduling mechanism (privacy is a resource), DPBalance, which considers efficiency and fairness in Federated Learning as a Service (FLaaS) platforms. The authors first propose a series of utility functions that consider data analyst-level dominant shares and FL-specific performance metrics. Then, they formulated an optimization problem to improve the efficiency and fairness of the FL platform. To address the proposed problem, the problem is decomposed into two sub-problems and develop a sequential allocation mechanism using the Lagrange multiplier method and greedy heuristics to solve them, respectively. Theoretical proofs are provided for the satisfaction of four key economic properties, as well as the existence of a fairness-efficiency tradeoff in privacy budgeting. Extensive experiments demonstrate that DPBalance outperforms state-of-the-art solutions regarding both efficiency and fairness.

Strengths: What are the main reasons to accept the paper? You may comment on the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
This paper addresses the challenge of efficient scheduling of FL pipelines for Federated Learning as a Service (FLaaS) platforms by jointly considering both efficiency and fairness. Training models on crowdsourced private data in Federated Learning fashion within the privacy budget is known as an interesting problem. In contrast, fairness in privacy is less been considered in prior works. The proposed DPBalance mechanism is novel and comprehensive, incorporating dominant shares across different FL pipelines to calculate data analyst-level fairness and platform-level efficiency. The Lagrange multiplier method and effective greedy heuristics used in the algorithm design are regular and efficient. Proofs of Pareto Efficiency, Sharing Incentive, Envy-Freeness, and Weak Strategy Proofness further strengthen the paper’s contribution. In summary, the problem is well-defined, the algorithm is well-established, the potential impact of DPBalance is significant, and it demonstrates the practical importance of FLaaS platforms.

Weaknesses: What are the main reasons NOT to accept the paper? Again, think about the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
The technical depth and novelty are not sound. The considered system is a federated learning system. While privacy mechanisms like DP and RDP have a strong impact on the learning process, the influence of private noise (e.g., Gaussian) on the trained model is ignored (such influence is usually non-linear). When designing the system to have better efficiency and fairness, the practical FL platform may have worse performance (in efficiency and fairness) without such consideration. Basically, at least some basic analysis of the designed method for the FL learning process is necessary for the paper.

The experiment is too simple. It is only an optimization simulation (via Gurobi solver) without any learning. Moreover, the FL training process usually takes several hundreds of rounds,10 rounds is too short for most FL tasks.

Quality of Writing: What is the presentation quality of this paper? Your overall rating should take this into consideration.
This paper is well written.

Overall Rating: Your overall rating (based on strengths, weaknesses, and quality of writing).
accept - I lean towards accepting this paper, but am willing to be convinced otherwise. (3)

Feedback to Authors: Detailed comments that you would like to provide to the authors. Please do not repeat what you stated above.
The authors should pay attention to the details of writing. For example, the function “sig()” in equation (10) should be the “sgn()”, the signum function defined in equation 9.

The experiment, like the reference paper [11] on a small dataset and model, is beneficial in proving the effectiveness of the proposed method.

Review 2
Double blind policy: Does this paper conform to the double-blind submission policy? If not, please provide explanations with clear evidence in the confidential TPC comments section of the review.
Yes, this paper conforms to the double-blind policy (1)

Paper Summary: Please summarize the paper in your own words.
The paper proposes a privacy budget scheduling mechanism called DPBalance, that considers efficiency and fairness in the context of FLaaS model training: DPbalance considers fairness among the different data analysts using the FLaaS cloud and the efficiency of the FLaaS cloud itself.

The work considers privacy as a resource, assuming differential privacy techniques where the privacy grows smaller as the encrypted data is shared longer. Then, the work investigates privacy allocation strategies to consider fairness and efficiency when multiple data scientists use FL pipelines on the same data originated from data owners (who crowd-sourced it to the cloud).

Strengths: What are the main reasons to accept the paper? You may comment on the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
The paper is the first to treat the problem of fairness among data analysts and efficiency from the point of view of the cloud provider at the same time. The mathematical model is novel but similar to those used in other papers to evaluate the fairness of computer resource sharing, for example using the concept or dominant resources. The difference that privacy is a non-refuelable resource is very interest and different from other resource sharing problems.

Weaknesses: What are the main reasons NOT to accept the paper? Again, think about the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
The paper spends most of its space with the mathematical modeling and, yet, the proof of a number of theorems are not included because of lack of space.

The performance evaluation is very short.

The offered demand (number of data analysts, number of requested FL pipelines per analyst, and other parameters) is not justified on real setups but rather on settings similar to the DPF paper, one of the strategies the proposed DPBalance is compared with.

Quality of Writing: What is the presentation quality of this paper? Your overall rating should take this into consideration.
The paper is well-written.

On page 6, I could not really understand the sentence: 3 Each data analyst i returns unused privacy resource back if there is privacy resource left or its γij from pipeline j with minimal μij Pareto-dominates than data analyst i’s share γixi because of one-or-more property (line 7).”

Minor mistakes:

Abstract: Deferentially >> Differentially

Page 8: with three baseline scheduling algorithm >> algorithms

Page 9 (2 times): “outperforms than other three” >> outperforms the other three

Overall Rating: Your overall rating (based on strengths, weaknesses, and quality of writing).
accept - I lean towards accepting this paper, but am willing to be convinced otherwise. (3)

Feedback to Authors: Detailed comments that you would like to provide to the authors. Please do not repeat what you stated above.
The paper does not state if the problem of privacy as a resource also exists for other privacy mechanisms different from differential privacy. Is differential-privacy a de facto standard for federated learning? Is the proposed technique useful for other encryption algorithms?

The simulation parameters should be further justified, if possible, based on real settings; and/or other scenarios with different numbers of data analysts should also be simulated.

Review 3
Double blind policy: Does this paper conform to the double-blind submission policy? If not, please provide explanations with clear evidence in the confidential TPC comments section of the review.
Yes, this paper conforms to the double-blind policy (1)

Paper Summary: Please summarize the paper in your own words.
The paper proposed a privacy budget scheduling mechanism that optimizes both efficiency and fairness which is considered an important topic in using federated learning as a service. The paper is first to consider both efficiency and fairness in budgeting unlike the related work which focus on either one of them. The paper proposed a utility function for FL performance metrics and utilizes Lagrange multiplier, The authors proved existence of a fairness-efficiency tradeoff in privacy budgeting.

Strengths: What are the main reasons to accept the paper? You may comment on the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
The paper has a valid unique contribution in an important problem in federated learning privacy. Balancing the efficiency and fairness is essential problem. The authors proposed a comprehensive utility model for the sequential allocation. The work sounds and proof was presented for the existence of a tradeoff between fairness and efficiency under practical conditions.

Weaknesses: What are the main reasons NOT to accept the paper? Again, think about the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
The paper relies on simple approach to solve the balancing problem. I think the problem needs more sophisticated solution given the complexity and the tradeoff of fairness and efficiency. The evaluation needs further enhancement to include some recent papers that tackled the problem

Quality of Writing: What is the presentation quality of this paper? Your overall rating should take this into consideration.
the paper needs writing improvement to make it easy to follow

Overall Rating: Your overall rating (based on strengths, weaknesses, and quality of writing).
accept - I lean towards accepting this paper, but am willing to be convinced otherwise. (3)

Feedback to Authors: Detailed comments that you would like to provide to the authors. Please do not repeat what you stated above.
The paper requires writing improvement as it is not easy to follow, evaluation needs further improvement by adding more baseline mechanisms I suggest to include a table for all the variables and acronyms as the paper has plenty. The authors need to add more references to the related work more explanation of the problem will be useful as the paper targets a narrow area in the federated learning research

Review 4
Double blind policy: Does this paper conform to the double-blind submission policy? If not, please provide explanations with clear evidence in the confidential TPC comments section of the review.
Yes, this paper conforms to the double-blind policy (1)

Paper Summary: Please summarize the paper in your own words.
The paper discusses the problem of privacy-aware scheduling in a system where multiple analysts use cloud-based Federated learning pipelines as a service due to its data privacy benefits. Considering the data block's privacy budget as a resource, this paper focuses on balancing fairness and efficiency in resource allocation. For this purpose, the authors developed 'DPBalance', a novel privacy budget scheduling mechanism that jointly optimizes both the efficiency and fairness of scheduling. To optimize efficiency and fairness in a joint way, the authors designed a sequential mechanism using the Lagrange multiplier method and greedy heuristics. Moreover, they theoretically prove that their scheduling mechanism, 'DPBalance, satisfies Pareto Efficiency, Sharing Incentive, Envy-Freeness, and Weak Strategy proof-ness, along with the existence of a fair-efficiency tradeoff in the privacy budget. In the end, they show that their proposed mechanism performs better than state-of-the-art solutions.

Strengths: What are the main reasons to accept the paper? You may comment on the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
The main reasons to accept the paper as follows:

The authors in this paper has addressed an important problem of privacy budget scheduling in Federated learning as a service. which is a recent emerging cloud based service.
The authors introduced the privacy as a resource to be allocated which is very novel.
Instead of just considering efficiency or fairness of the allocation process which has been already considered in recent privacy budget scheduling the authors focused on the joint optimization of both to find an optimal tradeoff. This is an important problem as it ensures the optimal utilization of privacy resources while maintaining fairness among data analysts.
This paper develops a comprehensive utility function that captures the characteristics of FLaaS training and allows for a more accurate evaluation of efficiency and fairness.
Weaknesses: What are the main reasons NOT to accept the paper? Again, think about the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
While the paper has some good points, there are also some areas where it could be improved:

The part where it talks about other research in the same area is quite short. Including more research could help us learn more about recent advancements in this field."
Limited novelty in algorithm design. The paper employees Lagrange multiplier method for algorithm design. In practical applications, particularly in high-dimensional system, this can lead to significant computational complexity and increased computational time.
The paper does not mention scalability explicitly. Depending on the application, the proposed mechanism may or may not scale well to large datasets or a large number of data analysts.
Quality of Writing: What is the presentation quality of this paper? Your overall rating should take this into consideration.
The paper demonstrates a comprehensive and well-structured presentation. It begins by introducing the background and motivation, followed by the system model and problem formulation. The algorithm design and theoretical analysis are presented in detail, and the evaluation section provides empirical evidence to support the proposed mechanism. The paper provides mathematical equations to support the definitions. A mathematical optimization problem formulation is provided for using the Lagrange dual method and the decomposition of the main optimization problem into subproblems with constraints is also presented in a clear way. In the evaluation section, the paper clearly provides the question it is aiming to answer and then provides each answer in detail in separate subsections. The graphical representation of results is also clear and concise. Overall, the presentation quality of the paper is commendable.

Overall Rating: Your overall rating (based on strengths, weaknesses, and quality of writing).
accept - I lean towards accepting this paper, but am willing to be convinced otherwise. (3)

Feedback to Authors: Detailed comments that you would like to provide to the authors. Please do not repeat what you stated above.
Dear authors, no doubt your paper targets a novel system providing federated learning as a service with the help of cloud services while maintaining the privacy of data and optimizing the tradeoff between fairness and efficiency, You can design a new algorithm that can perform better in large systems.

Review 5
Double blind policy: Does this paper conform to the double-blind submission policy? If not, please provide explanations with clear evidence in the confidential TPC comments section of the review.
Yes, this paper conforms to the double-blind policy (1)

Paper Summary: Please summarize the paper in your own words.
This paper proposes DPBalance, which seeks to allocate a privacy budget across multiple federated learning tasks. Unlike prior works on privacy budget allocation, DPBalance accounts for both fairness and efficiency in the allocation, which allows it to outperform previously proposed privacy allocation methods in federated learning. The key idea is to design a utility function that incorporates both federated learning-specific performance metrics (namely, data training loss) and the “dominant shares” of the privacy budget allocated to specific federated learning tasks. This formulation also allows for proving that several fairness-relevant properties, such as envy-freeness, hold for certain utility parameterizations. Experiments demonstrate that DPBalance outperforms state-of-the-art solutions by 40% or more on both fairness and efficiency metrics.

Strengths: What are the main reasons to accept the paper? You may comment on the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
The formulation of a utility function that captures efficiency concerns as weights to the privacy dominant share is interesting and allows known machinery for studying fair resource allocation to be used in this problem.

Balancing fairness and efficiency is an important problem in deciding how to add differential privacy to federated learning jobs. DPBalance is the first work that proposes to study this balance.

Weaknesses: What are the main reasons NOT to accept the paper? Again, think about the importance of the problems addressed, the novelty of the proposed solutions, the technical depth, and potential impact. Your overall rating should be supported by your review.
--It’s not clear how DPBalance would work in practice, especially since parts of the utility function seem difficult to know in advance. For example, the training loss is generally not known until after the training is complete. Moreover, the training loss will also depend on the privacy allocation, so taking it to be a fixed weight on the privacy dominant share is not technically correct. It’s not clear how these losses were estimated in the numerical simulations, or how they would be used in practice.

--The current formulation appears to ignore the data heterogeneity across clients, which may cause certain blocks of data to be more useful to the overall training of certain tasks than others. The training demands are not defined clearly, but they seem to consist of simply the number of devices for each federated learning pipeline, whereas one of the key challenges of federated learning is that which device is used in the training can matter a lot.

--The privacy threat model is not well-defined. Although a separate section discusses the threat model, it’s not clear why the privacy is defined separately for each data block, as the blocks from the same devices are (presumably) drawn from the same or similar distributions. Moreover, it’s not clear if the privacy budget is defined for each data analyst or for the platform as a whole. In other words, which entity is the data being kept private from?

Quality of Writing: What is the presentation quality of this paper? Your overall rating should take this into consideration.
The paper has several odd phrasings, though they do not impede readability. For example, “sophisticatedly” on page 1 and “We prove Theorem 3 by testifying” on page 7 below Theorem 3.

Overall Rating: Your overall rating (based on strengths, weaknesses, and quality of writing).
likely reject - I lean towards rejecting this paper, but am willing to be convinced otherwise. (2)

Feedback to Authors: Detailed comments that you would like to provide to the authors. Please do not repeat what you stated above.
The paper introduces several notations that can be hard to track, e.g., the index I is used for both devices and data analysis.

The numerical simulations don’t seem to use any federated learning jobs, so it’s difficult to tell how realistic the results are. Federated learning generally introduces quite a bit of noise in the process, so the simulated fairness and efficiency may not be accurate.

The utility definition is not well justified, since it simply multiplies the dominant share, training loss, and a decreasing function of the training delay. Why should these be multiplied together (their product doesn’t seem to have a physical meaning)? Shouldn’t the training loss be the training accuracy, since the utility is being maximized? What if some delay matters more in some pipelines than others? Why isn’t the test loss being included, as that is a better judge of the “usefulness” of this data than the training loss? This formulation also doesn’t take into account the fact that training loss will naturally decrease as the training progresses.

The paper states that (alpha, epsilon)-RDP satisfies both parallel and additive composition properties, but it wasn’t clear to me how it could satisfy both. Moreover, the definitions of parallel and additive consumption are just definitions of what these terms mean; it’s not clear that they are properties that a privacy measure could satisfy.
