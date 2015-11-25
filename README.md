# Math Problem Dataset
This is a math problem dataset that covers algebra and geometry topics. The reason for this dataset is to provides better data support to design and implement a math interactive learning system.

The scope of knowledge components in this data set covers:
Arithmetic Manipulation, Algebraic Manipulation, Analytical Geometry and Coordinate Geometry. (Update required) 

There are **three dimensions of data**:
1. math problems: Problems.json
2. math concepts: Topics.json
3. math instructions(scaffoldings) per problem: Instructions.json

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

Format of Topics.json:

Format of Instructions.json:
(Josh TODO)


