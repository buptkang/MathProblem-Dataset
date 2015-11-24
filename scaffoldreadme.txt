The scaffold JSON file is set up as follows:
A list of Scaffold objects (currently only contains one)

Each scaffold has the following attributes:
"problem-id": //corresponds to the ID of the problem being scaffolded, as found in Problems.json
	--This will be very useful in the future, as it provides a very convenient way to match problems with scaffolds.
"problem-text": //corresponds with the text of the problem being scaffolded, as found in Problems.json
	--While at first this may seem redundant, but this serves a three-fold purpose.
		1) This can be used during the problem-scaffold matching algorithm as a validation check
		2) Throughout the steps (described later), "root" is referenced. This refers to information given from the problem itself,
			and will allow the scaffold object to create a full map from problem text to solution.
		3) With this scaffold data-architecture, I believe it will be very feasible to write a function that one might call
			"problemFromScaffold(Scaffold Scaffold, String Category, String Style)" which will return a Problems.json style Problem object, complete,
			using this dataset alone. This will potentially increase data-annotation rates.
"steps": //This is a list of records of a type I am calling "step" (although the actual name of the object type is implicit due to JSON nature)

	Each step corresponds to one step in a problem's scaffold.
	Each step has the following fields:
	"id": //A unique identifier for each step. I have numbered the steps in the example to correspond with my scaffold of problem C001.
	"type": //this corresponds to what would be in the parentheses at the beginning of the scaffold step. I have modified this as follows, for reasons described later
		-- Type -> "summary" | "meta" | "scaffold" | "solution"
			--Summary, meta, and scaffold are all seen in previous problem scaffolds that have been submitted.
			--Solution is a new type that I am introducing. This is the "final step" so to speak; its text field must contain the raw solution to the problem
	"text": //This is a little self explanatory, this is the text that should be displayed for each scaffolding step. For any "solution" step, it must include nothing other than the solution. (This will be useful for a scaffold-to-problem generator)
	"dependencies": //This is a list of lists.
		-- Each list contains the set of steps that must be completed before this step can be reached. 
		-- I could write a full article about the potential things that could be done with this set-up, but that will be done later. For now I will keep it brief.
		--If the type is "meta", each list should contain a set of steps that must be completed for this 'hint' to display (List of lists helps here for reused meta-scaffolds)
		--If the type is "summary", dependency will simply be [ [ "root"]]. This will have to be coded into the system, but this "root" reference seems to be the best way I can find to denote that it is referring to "problem-text" and not another step's ID
		--If the type is "scaffold" or "solution", each list will contain a unique set of step IDs that can be combined to use this step. Note that this means these steps must have been completed before this step is reached.
			--The reason that this is a list of lists, even though in the example only one list is used for each, is so that we can encompass multiple "paths-to-solution" using different sets.
				--For example, in my scaffold I substitute h and g in the same step. These could be added separately in new steps (016,017), and then step 006's dependencies would become [ ["003","005"],["003","016","017"]]
	"concepts-used": //corresponds with concepts in Topic.json; these are the math skills implemented in each step of the scaffold.
		--For solution steps, this should correspond with the "Topic" field of the problem in Problem.json

Although this is a rather large datatype, due to the nature of a scaffold, I feel it has to be.
I also believe this to be a very robust solution to the data-storage of scaffolds, for these reasons:
	--Allows multiple independent and/or semidependent scaffolds to coexist in the same object.
	--The dependency tree will allow an exhaustive constrained search to map all possible routes to solution for all solutions
	--The structure of dependencies will allow for program to give hints beyond the level of metascaffolds to user if they seem very stuck (i.e. "feeling stuck? Maybe look back at what you did in these steps")
	--By tracking concepts-used at each step, this will aid in the production of a framework that learns what individual students have trouble with / excel at

Anyway, that's an overview/introduction to my proposed Scaffolds.json data-structure format.
If there are any questions/concerns/suggestions/critiques/etc, please notify me.	