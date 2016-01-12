# Math Problem Dataset
<p align="justify">
This is a geometry math problem dataset that focus on the quantitaive reasoning (stand upon the Descartes's mind to measure geometry). It can be used for different research fields: student modeling, natural language processing, scaffolding synthesis.
</p>

**Three dimensions of data**:

1. Math problems: Problems.json

2. Math concepts: Topics.json + Concepts.json

3. Math scaffolding per problem: Scaffoldings.json (preliminary structure)
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
