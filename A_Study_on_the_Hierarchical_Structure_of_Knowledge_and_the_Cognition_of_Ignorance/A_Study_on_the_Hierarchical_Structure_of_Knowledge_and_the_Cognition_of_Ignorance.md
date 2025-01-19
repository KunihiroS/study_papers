# A Study on the Hierarchical Structure of Knowledge and the Cognition of Ignorance

*Kunihiro Sugiyama*  
kunihiros@gmail.com

## Introduction

Human knowledge possesses a multi-layered structure, and the ability to recognize one's own ignorance (metacognition) is crucial for learning and decision-making. This study proposes a continuous model of knowledge and ignorance based on four elements: "Existence," "State," "Cognition," and "Conceptual Understanding." This model integrates insights from **metacognition**, **knowledge representation models**, **research on the ambiguity of knowledge**, and **epistemology**. It aims to comprehensively capture three aspects that have not been sufficiently addressed in existing research: the **discrepancy between the subjectivity and objectivity of knowledge**, the **hierarchical structure of intrinsic knowledge**, and the **continuous gradation of knowledge**. By presenting a model that integrates these elements, this study seeks to deepen our understanding of the structure of knowledge and the cognitive mechanisms of ignorance.

## Distinguishing Existence and Subjective Knowledge

In this study, "**Existence**" is defined as follows:

* **Existence**: A state where the subject's knowledge about an object is **objectively verifiable**.
  * Existence is independent of the subject's intrinsic knowledge or perception and is verifiable by a third party.

### The Position of Existence and Related Research

This study is based on the discussion of **the separation between the subjective and the objective** in epistemology, and clearly distinguishes between "Existence," the objective existence of knowledge, and subjective knowledge or perception. In his *Critique of Pure Reason*, Kant distinguished between phenomena (subjective experience) and the thing-in-itself (objective reality), and argued that humans cannot know the thing-in-itself (Kant, 1781). The "Existence" in this study is a concept similar to Kant's "thing-in-itself" and is considered to exist independently of the subject's perception. This distinction is an essential premise for considering the **discrepancy between the subjectivity and objectivity of knowledge**.

## The Three-Stage Model of Knowledge

The cognitive structure of knowledge is modeled in the following three stages. This model is based on research findings on **metacognition** and aims to express the **hierarchical structure of intrinsic knowledge**.

### State (First Layer)

* **Definition**: The state of knowledge or misunderstanding that a subject intrinsically possesses (independent of perception or consciousness).
* **Expression**: $$K(x) \in [-1, 1]$$
  * $$1$$: The subject has correct knowledge.
  * $$0$$: The subject knows nothing (ignorance).
  * $$-1$$: The subject has incorrect knowledge.

### Cognition (Second Layer)

* **Definition**: How accurately the subject recognizes their own state (First Layer).
* **Expression**: $$K(K(x)) \in [-1, 1]$$
  * $$1$$: The subject correctly recognizes their own knowledge (awareness of ignorance).
  * $$0$$: The subject is unaware of their own knowledge (ignorance of ignorance).
  * $$-1$$: The subject mistakenly believes incorrect knowledge to be correct.

### Conceptual Understanding (Third Layer)

* **Definition**: How much the subject understands the cognitive structure of the Second Layer itself.
* **Expression**: $$K(K(K(x))) \in [-1, 1]$$
  * $$1$$: The subject correctly understands the cognitive structure.
  * $$0$$: The subject is unaware of their conceptual understanding (ignorance of ignorance of ignorance).
  * $$-1$$: The subject believes in an incorrect cognitive structure.

Flavell (1979) defined metacognition as "the ability to monitor and control one's own cognitive activities." The "Cognition" and "Conceptual Understanding" layers in this study are based on this concept of metacognition. Additionally, Dunning and Kruger (1999) demonstrated the tendency of individuals with low competence to overestimate their abilities (the Dunning-Kruger effect). This phenomenon corresponds to the discrepancy between "State" and "Cognition" in this study, particularly in the state where incorrect assessments are made at the Cognition layer. While many existing metacognition studies focus on verifying the role of metacognition in self-learning and problem-solving processes, this study is novel in that it treats metacognition as a part of the hierarchical structure of knowledge and models the mechanisms for evaluating the accuracy of one's own knowledge.

## The Gradation Model of Knowledge and Ignorance

In this study, knowledge and ignorance are modeled as a **continuous value** rather than as a dichotomy. This approach is based on research findings on the **ambiguity of knowledge** and aims to express the **continuous gradation of knowledge**.

### Definition of the Model

* **Range**: $$[-1, 1]$$
  * $$1$$: Complete correct knowledge.
  * $$0$$: Ignorance.
  * $$-1$$: Complete misunderstanding.

### Connection with Related Research

The perspective that knowledge is not always clear and complete but includes ambiguity and uncertainty is crucial for modeling knowledge as a continuous value. Zadeh's (1965) fuzzy theory provides a framework for mathematically handling ambiguous concepts, and Pearl's (1988) probabilistic reasoning provides a model for handling uncertain knowledge. These studies suggest that the continuous value model in this study is a valid approach for capturing the ambiguity of knowledge. While existing knowledge representation studies attempt to represent knowledge with clear symbols and combinations of concepts, this study is novel in that it numerically models the ambiguity and uncertainty of knowledge.

## The Discrepancy between Subjectivity and Existence

When subjective knowledge does not align with existence (objective facts), this discrepancy can lead to ignorance or misunderstanding. In this study, this discrepancy is viewed as the **discrepancy between the subjectivity and objectivity of knowledge** and analyzed from the following three aspects:

### Discrepancy between Existence and State
* **Definition**: The discrepancy between existence (objective facts) and the subject's state (subjective knowledge).
* **Equation**: $$|E(x) - K(x)|$$

### Discrepancy between State and Cognition
* **Definition**: The discrepancy between the subject's state (knowledge) and their recognition of that state.
* **Equation**: $$|K(x) - K(K(x))|$$

### Discrepancy between Cognition and Conceptual Understanding
* **Definition**: The discrepancy between the subject's cognition and their metacognition.
* **Equation**: $$|K(K(x)) - K(K(K(x)))|$$

## Conclusion and Future Challenges

This study constructed a four-layer model of "Existence," "State," "Cognition," and "Conceptual Understanding" based on the hierarchical structure of knowledge. Integrating research findings on **metacognition**, **knowledge representation models**, and the **ambiguity of knowledge**, we attempted to comprehensively capture three aspects: the **discrepancy between the subjectivity and objectivity of knowledge**, the **hierarchical structure of intrinsic knowledge**, and the **continuous gradation of knowledge**.

### Main Results

1. We proposed a continuous value model of knowledge and demonstrated the potential for numerically modeling the ambiguity of knowledge.
2. We separated subjective perception from objective existence and provided a framework for analyzing the discrepancies between the two.
3. We proposed a hierarchical structure of knowledge based on metacognition, making it possible to understand the process of recognizing one's own ignorance in a multi-layered manner.

### Future Challenges

1. Empirical verification of the proposed model (collection and analysis of experimental data).
2. Evaluation of the impact of social factors (culture and gender) on the structure of knowledge.
3. Modeling of specific knowledge structures based on knowledge representation models.
4. Examination of how to apply the conceptual framework raised in this study to specific educational and decision-making situations.

## References

1. Kant, I. (1781). *Critique of Pure Reason*.
2. Flavell, J. H. (1979). Metacognition and cognitive monitoring: A new area of cognitive-developmental inquiry. *American psychologist*, *34*(10), 906.
3. Dunning, D., & Kruger, J. (1999). Unskilled and unaware of it: How difficulties in recognizing one's own incompetence lead to inflated self-assessments. *Journal of personality and social psychology*, *77*(6), 1121.
4. Zadeh, L. A. (1965). Fuzzy sets. *Information and control*, *8*(3), 338-353.
5. Pearl, J. (1988). *Probabilistic reasoning in intelligent systems: networks of plausible inference*. Morgan Kaufmann.