# Math Problem Dataset
This is a <a href="https://en.wikipedia.org/wiki/Word_problem_(mathematics_education)">math problem</a> dataset that covers algebra and geometry topics.

<p align="justify">
In comparison to well-researched arithmetic word problem or <a href="http://groups.csail.mit.edu/rbg/code/wordprobs/">algebra word problem</a>, this data set (math problems) contains geometry oriented math word problem which use algebraic
knowledge to solve (Coordinate Geometry or Analytical Geometry)
</p>

<p align="justify">
There are three dimensions of data which is collected here.
Dimension 1 is math problems: Problems.json
Dimension 2 is math concepts: Topics.json
Dimension 3 is math instructions(scaffoldings) per problem: Instructions.json
</p>


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
