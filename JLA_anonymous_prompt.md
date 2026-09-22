# Knowledge-graph extraction prompt

The prompt below is reproduced from the manuscript supplement. Double-braced variables are filled with the study-specific entity list, relationship list, JSON schema, and discussion text at runtime.

```text
You are tasked with analyzing a student's post and their interactions within a discussion thread to build a knowledge graph centered around the top-level student poster. This task aims to understand how the student's knowledge interacts with others in the discussion. This knowledge graph will be represented as a list of triplets. Your goal is to extract relevant information from the discussions and structure it according to the provided schema.

First, here are the allowed entities and relationships you should use:

<allowed_entities>

{{ALLOWED_ENTITIES}}

</allowed_entities>

<allowed_relationships>

{{ALLOWED_RELATIONSHIPS}}

</allowed_relationships>

The output should follow this JSON schema:

<json_schema>

{{JSON_SCHEMA}}

</json_schema>

Now, I will provide you with the student discussions. Your task is to analyze these discussions and extract meaningful triplets that represent the knowledge graph. Here are the discussions:

<student_discussions>

{{STUDENT_DISCUSSIONS}}

</student_discussions>

Analyze the student's knowledge and how it interacts with others in the discussion. Follow these steps:

1. Identify the main concepts and ideas presented by the top-level student poster.

2. Analyze how these concepts are expanded upon, challenged, or supported by other participants in the discussion.

3. Note any new information or perspectives introduced by other participants that relate to the student's original post.

4. Observe how the student's understanding may have evolved through interactions with others, if applicable.

To create the knowledge graph:

1. Read through the discussions carefully. Each discussion can involve multiple roles, including students who initiate posts (labeled as “s:”), peers who provide replies (“p:”), and paid tutors who contribute instructional support (“e:”).

2. Identify key concepts, problems, solutions, and relationships between them.

3. For each relevant piece of information, create a triplet in the form of (subject, predicate, object), where:

- subject and object are entities from the allowed entities list

- predicate is a relationship from the allowed relationships list

Present your analysis and knowledge graph description in the following format:

<analysis>

1. Main concepts presented by the student:

[List the main concepts]

2. Interactions with other participants:

[Describe how each concept interacts with others' contributions]

3. Evolution of student's understanding:

[If applicable, describe how the student's knowledge may have changed]

4. Knowledge graph description:

[Provide a textual description of the knowledge graph, including nodes and connections]

</analysis>

1. Continue this process for all relevant information in the discussions.

2. After creating all triplets, format your output according to the provided JSON schema. Make sure to include all the required fields and follow the correct structure.

3. Present your final output within <knowledge_graph> tags.

Remember to focus on Algebra I concepts and ensure that all entities and relationships used are from the allowed lists. If you encounter any ambiguities or uncertainties, explain your interpretation and decision-making process in a <analysis> tag before creating the related triplet.
```
