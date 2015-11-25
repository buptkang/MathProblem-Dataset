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

Format of Instructions.json:
(Josh TODO)
