# Math Problem Dataset
<p align="justify">
This is a math problem dataset that covers algebra and geometry topics. This data set can be served for different research purposes: math problem natural language process, adaptive scaffolding analysis and interactive learning system development.
</p>

Math problems are designed to elicit math concepts. Math concept can be described as a function, a structure, a behavior or a relations with other concepts, there can be different narrative math problems to reinforce the same math concept learning.

The scope of knowledge components in this data set covers:
Arithmetic Manipulation, Algebraic Manipulation, Analytical Geometry and Coordinate Geometry. (Update required)

There are **three dimensions of data**:

1. Math problems: Problems.json

2. Math concepts: Topics.json + Concepts.json + ErrorConcepts.json

3. Math instructions (scaffoldings) per problem: Instructions.json

___

***Dimension 1***: 

Format of Problems.json:

| Column Name  | Column Type  |                       Column Explanation                        |
| -------------|--------------|-----------------------------------------------------------------|
|      id      |    string    |                           GUID                                  |
|     problem  |    string    |                         Text Problem                            |
|     semantic |    array     |     Annotated Math Semantic of natural language math problem    |
|    concept   |    array     |       Annotated Concepts covered in the problem (Concepts.json) |
|     topic    |    string    |       Annotated Math Problem Topic (Topics.json)                |
|     solution |    array     |                   Annotate problem solution                     |

___

***Dimension 2***:

Format of Topics.json:

| Column Name  | Column Type  |                   Column Explanation                            |
| -------------|--------------|-----------------------------------------------------------------|
|   topic      |    string    |                     Topic Name                                  |
| dependencies |    array     |                   Dependent Topics                              |


Format of Concepts.json:

| Column Name  | Column Type  |                   Column Explanation                            |
| -------------|--------------|-----------------------------------------------------------------|
|   concept    |    string    |                     Concept Name                                |
|   topic      |    string    |                     Topic Name                                  |
| dependencies |    array     |                   Dependent Concepts                            |


Format of ErrorConcepts.json:

| Column Name     | Column Type  |                   Column Explanation                            |
| ----------------|--------------|-----------------------------------------------------------------|
|   error-concept |    string    |                     Topic Name                                  |
|   concept       |    string    |                     Concept Name                                |

___

***Dimension 3***:

Format of Scaffolds.json:

| Column Name  |  Column Type    |          Column Explanation        |
| -------------|-----------------|------------------------------------|
|  problem-id  |     string      | corresponds to ID in problems.json |
| problem-text |     string      |       question being asked         |
|    steps     | list of records |   step in scaffold (see below)     |

"step" record:

| Column Name  | Column Type   |         Column Explanation                                      |
| -------------|---------------|---------------------------------------------------------------- |
|   id         |    string     |       unique identifier                                         |
|   type       |    string     |   summary,meta,concept-scaffold, procedural-scaffold,solution   |
|   text       |    string     |   embed text of scaffold step                                   |
| dependencies | list of list  | map all potential dependency step                               |
|concepts-used |list of strings| embed all topics employed by step                               |
|  procedurals |list of steps  | recursively add steps into the current step                     |


___

Reference:

https://pslcdatashop.web.cmu.edu/DatasetInfo?datasetId=76
