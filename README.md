# Math Problem Dataset
<p align="justify">
This is a math problem dataset that covers algebra and geometry topics. This data set can be served for different research purposes: math problem natural language process, adaptive scaffolding analysis and interactive learning system development.
</p>

The scope of knowledge components in this data set covers:
Arithmetic Manipulation, Algebraic Manipulation, Analytical Geometry and Coordinate Geometry. (Update required) 

There are **three dimensions of data**:

1. Math problems: Problems.json

2. Math concepts: Topics.json

3. Math instructions (scaffoldings) per problem: Instructions.json

___

Format of Problems.json:

| Column Name  | Column Type  |         Column Explanation       |
| -------------|--------------|----------------------------------|
|      id      |    string    |       GUID                       |
|     problem  |    string    |     Text Problem                 |
|    concept   |    array     |   Embed Concept in the problem   |
|     topic    |    array     |   Embed Questions of the problem |
|    category  |  enumeration |   Geometry, Arithmetic, Algebra  |
|      style   |  enumeration |   mathematic, hybrid, word       |
|     solution |    array     |   maps to number of topic column |

___

Format of Topics.json:
(Josh TODO)

___

Format of Scaffolds.json:
| Column Name  | Column Type   |         Column Explanation       |
| -------------|---------------|----------------------------------|
|  problem-id  |    string     |corresponds to ID in problems.json|
| problem-text |    string     |      question being asked        |
|    steps     |list of records|  step in scaffold (see below)    |

"step" record:
| Column Name  | Column Type   |         Column Explanation         |
| -------------|---------------|------------------------------------|
|   id         |    string     |       unique identifier            |
|   type       |    string     |   summary,meta,scaffold,solution   |
|   text       |    string     |   embed text of scaffold step      |
| dependencies | list of list  | map all potential dependency* sets |
|concepts-used |list of strings| embed all topics employed by step  |


*| dependency   | list of strings  | embed combination of step-ids that must are used in this set (i.e. must have already been completed for this step to take place) |


___

Reference:

https://pslcdatashop.web.cmu.edu/DatasetInfo?datasetId=76
