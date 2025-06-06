# Bridgerton in DBpedia


  [Home]()
  [Selected Topic Description]()
  [Gap, General Methodology and Tools]()
  [Methodological Steps]()
  [Challenges and LLMs Differences]()


## Abstract

    In this project, we explored and enriched a knowledge graph (KG) about the TV series Bridgerton by combining SPARQL querying techniques with the assistance of large language models (LLMs), specifically ChatGPT (OpenAI) and Gemini (Google). Our goal was to model and assess whether certain concepts (e.g., general information and knowledge, themes, soundtrack) are represented in the graph, and where necessary, propose new triples.

## Project by

*Alessia Gavelli, Elisa Mainardi & Gaia Pestelli*


## Selected Topic Description

For our project, we have chosen to focus on the television series Bridgerton, a production that has gained widespread popularity and cultural relevance in recent years.This decision was made collectively, as the series is well-known, widely discussed, and familiar to all members of the group. Bridgerton includes multiple **interconnected storylines** and social dynamics, making it ideal for building a semantic graph (e.g. DBpedia) where entities and links reflect both explicit and inferred connections. This allows us to apply advanced querying techniques (e.g. Yasgui) to explore patterns, relationships, and hierarchies within the fictional world.

Bridgerton is a historical romance television series created by Chris Van Dusen and produced by Shondaland, based on the bestselling novels by Julia Quinn. The show is set in **Regency-era London** (early 19th century), a period characterized by rigid social structures, elaborate courtship rituals, and intense pressure to marry advantageously. As of 2025, Bridgerton has released three seasons; additionally, the series has been renewed for Seasons 5 and 6, ensuring the continuation of the Bridgerton family's stories

The narrative primarily follows an affluent family whose members are each introduced to the social season, where finding a suitable marriage partner is both a personal and familial priority. Each season centers on the romantic and emotional development of a different family member, exploring how **individual desires often clash with societal expectations**. The stories are marked by themes of **longing, personal growth**, and the delicate balance between **public image and private truth**. A key narrative device is the presence of an anonymous gossip columnist whose scandalous reports influence public perception and add intrigue to the unfolding events. A companion series to Bridgerton expands the universe by focusing on the early life of a prominent royal figure featured in the main show. "Queen Charlotte: A Bridgerton story" is set in the same alternate version of Regency society, this prequel explores themes such as **power, societal change, personal sacrifice, and the pressures of leadership**.
Thematically, Bridgerton explores the tension between **love and societal obligation, gender roles, and the importance of reputation** within the aristocracy. It also addresses female agency, particularly through its female characters who seek autonomy in a patriarchal world. While not historically accurate, the show embraces a diverse and **inclusive casting**, presenting a reimagined Regency society in which race does not impede social mobility—thus blending historical drama with modern values.
Visually, Bridgerton is known for its opulent production design, featuring grand estates, extravagant costumes, and stylized reinterpretations of period customs. Despite its historical setting, the series often incorporates **contemporary music (in classical arrangements) and **modern storytelling techniques**, creating a fresh, hybrid aesthetic.
.

## Gap, General Methodology and Tools
**HOW THE GAP WAS IDENTIFIED**
After having identified the entity we wanted to take into account, we decided to execute a first general query to find anything that was labelled as “Bridgerton” in DBpedia,  https://www.dbpedia.org/resources/ontology/. So we asked two LLMs (ChatGPT and Gemini),to produce a query following the example included in the guidelines presentation, involving few-shot prompting.
These were the results:

ChatGPT
![QUERY 1](https://i.imgur.com/5HuAiJ2.png)
![QUERY 1](https://i.imgur.com/bJbrr2S.png)

GEMINI
![QUERY 1](https://i.imgur.com/COdnf85.png)
![QUERY 1](https://i.imgur.com/gbjfinA.png)

Both LLMs gave us the same outcome, to which we added LIMIT 100 to have a reasonable outcome.Then
we executed the query and we obtained a series of results, between which we individuated the knowledge graph we wanted to amplify (n. 30), traceable with the IRI: https://dbpedia.org/page/Bridgerton . 

![QUERY 1](https://i.imgur.com/DvKTVa6.png)
![QUERY 1](https://i.imgur.com/uZhTrn5.png) 

This knowledge graph classifies “Bridgerton” as an entity of type: Television show. From there we decided to execute other two very general queries to individuate the classes and properties already related to the dbr:Bridgerton, so to have a general idea of what we were working with.

CLASSES:

ChatGPT
![QUERY CLASSES](https://i.imgur.com/w4K1yda.png)
![QUERY CLASSES](https://i.imgur.com/LfOL1kx.png)
![QUERY CLASSES](https://i.imgur.com/p7AeWJL.png)
![QUERY CLASSES](https://i.imgur.com/UnvBert.png)

GEMINI
![QUERY CLASSES](https://i.imgur.com/vtzqTXf.png)
![QUERY CLASSES](https://i.imgur.com/G1YYySy.png)
![QUERY CLASSES](https://i.imgur.com/xeTaNzB.png)
![QUERY CLASSES](https://i.imgur.com/i3aFYYb.png)

PROPERTIES:

ChatGPT
![QUERY PROPERTIES](https://i.imgur.com/Hb7AOxG.png)
![QUERY PROPERTIES](https://i.imgur.com/4hqSvps.png)
![QUERY PROPERTIES](https://i.imgur.com/mVfqVtJ.png)
![QUERY PROPERTIES](https://i.imgur.com/MUtNcKs.png)

GEMINI
![QUERY PROPERTIES](https://i.imgur.com/IkmaZAt.png)
![QUERY PROPERTIES](https://i.imgur.com/IeNxMBK.png)
![QUERY PROPERTIES](https://i.imgur.com/3Mt0g2I.png)
![QUERY PROPERTIES](https://i.imgur.com/JWiPxa0.png)

The two LLMs gave the same result, but Gemini added and ORDER BY to range the results in alphabetical order.

After having explored the vocabulary related to our knowledge graph, we decided to have a look at it and we noticed instantly that some information was **wrong** and needed to be **modified**
that some classes and properties needed to be **integrated** and that some information could be **added integrally**. So we developed a general methodology to address all this instances. 

**GENERAL METHODOLOGY**
In this project, we explored and enriched a knowledge graph (KG) about the TV series Bridgerton by combining SPARQL querying techniques with the assistance of large language models (LLMs), specifically ChatGPT (OpenAI) https://chatgpt.com/c/683f081c-f3ec-8008-a318-4d672e5370ae,  and Gemini (Google), https://gemini.google.com/app/85a27a3bdc80935d?hl=it.
Our goal was to model and assess whether certain concepts (e.g., general information and knowledge about themes and the soundtrack) are represented in the graph, and where necessary, propose new triples.

At first, we explored DBpedia KG’s vocabulary/ontology and identified classes and properties that can be used to model certain concepts, or to propose new concepts to enrich the vocabulary. Therefore, we studied the DBpedia ontology (dbo, dbr, dbc, rdfs) to identify how concepts like themes, subjects, and categories are currently modeled. We explored the ontologies and identified the concepts (classes and properties) to build queries.
Then we used the LLMs (ChatGPT and Gemini) as information retrieval/question answering tools to find relevant knowledge to enrich the KG. 
After having identified the areas that we wanted to explore more in depth, we wrote several SPARQL queries targeting the DBpedia resource for Bridgerton. 
In doing so, we applied multiple SPARQL keywords to extract or validate thematic information:
•	FILTER + REGEX to detect the presence of specific keywords in abstracts
•	OPTIONAL to be able to have queries that allow information to be added to the solution where the information is available, but do not reject the solution because some part of the query pattern does not match
•	DISTINCT and LIMIT to refine and control results
•	ORDER BY to sort output (used in debugging and display queries)
•	UNION to combine multiple theme patterns in a single query (e.g., "desire" OR "struggle").

When existing links were missing or were incorrect, we proposed new conceptual connections using RDF triples. We designed custom RDF triples using SPARQL CONSTRUCT queries to represent new knowledge. So, used ChatGPT and GEMINI to generate these triples, model their structure, and validate whether the vocabulary aligned with DBpedia. We also explored how LLMs can help when formal vocabulary is lacking.
We used three prompting strategies:
-	Zero-shot: Direct requests (“Can you give me a complete and detailed list of the themes in the Bridgerton TV series?”)
-	Few-shot: Providing examples like the personal desire and the emotional struggles triples before asking for a new one on taboos.
-	Chain-of-thought: Asking the LLM to think step-by-step before generating a triple (e.g., “Think step-by-step how to model a triple connecting Bridgerton to the concept of emotional struggle”).

We critically evaluated LLM outputs by checking query correctness using a SPARQL endpoint (e.g., DBpedia SPARQL interface).
We noticed that both ChatGPT and GEMINI had strong understanding of RDF, RDFS, OWL, SPARQL, and semantic modeling practices. They are familiar with Linked Data vocabularies (e.g., DBpedia, FOAF, etc.) and understand how to model new triples or propose schema extensions using correct RDF syntax.
When given examples they corrected and trained themselves to give the following tasks in the already corrected form. The same thing happened when they were asked to think step by step. While at first, they gave more concise and direct answers, after asking them to do chain-of-thought they repeated this process also in the following tasks. 
They both remembered and chained context, which helps when we asked: "Now create a triple for 'taboos' like you did for 'emotional struggles'". They can track previous ontology examples and maintain vocabulary consistency.
This project demonstrated how SPARQL and LLMs can work in synergy to enrich and interrogate a cultural knowledge graph. From querying existing data to proposing new semantic connections, we applied best practices in prompt engineering, ontology alignment, and RDF modeling, all while evaluating the reliability and expressiveness of different language models.

**TOOLS**
1.	LLMs: 	*ChatGPT* (OpenAI) and  *Gemini* (Google): 
-	Purpose: Used as a language model assistant for generating SPARQL queries, proposing RDF triples, modeling ontological relationships, and supporting prompt engineering.
-	Strengths: Strong performance in structured reasoning, syntax generation, and adherence to ontological standards when prompted effectively.
-	Use Cases:
o	Creating SPARQL queries (SELECT, CONSTRUCT).
o	Rewriting prompts using few-shot or chain-of-thought methods.
o	Evaluating and refining RDF vocabulary usage.

2.	YASGUI https://yasgui.org/ 
•	Purpose: A web-based SPARQL query interface used to write, test, and run SPARQL queries on DBpedia and other endpoints.
•	Benefits:
o	Syntax highlighting and prefix auto-completion.
o	Easy visualization of results.
o	Support for custom SPARQL endpoints.

3.	 Prefix. cc	 https://prefix.cc/ 
•	Purpose: A lookup service for common RDF and SPARQL prefixes.
•	Use in Project:
o	Quickly finding standard prefixes (e.g., dbo, rdfs, foaf) to ensure correct namespace usage in queries.
o	Ensuring vocabulary alignment and avoiding errors in prefix declaration.

4.	Github https://github.com 
GitHub is a web-based platform for version control and collaboration. It lets developers store and manage code using Git, track changes, and work together on software projects..

## Methodological Steps
In this section we present the steps taken to enrich the KG dbr:Bridgerton, https://www.dbpedia.org/resources/ontology/. This process began after establishing the groundwork and defining the overall methodology to be followed.
*Step 1: Immediate queries*
The initial queries are aimed at correcting inaccuracies related to the dbo:numberOfSeasons and dbo:numberOfEpisodes. In the current version of the KG, both categories are wrongly represented:the number of seasons is listed as xsd:2, whereas it should be 3; and the number of episodes is listed as xsd:16, when it should be 24. 
Furthermore there are equivalent properties, dbp:numSeasons and dbp:numEpisodes, which are also incorrect.
Given the identical nature of these issues, the same procedure was applied to both instances.

Episodes:
First of all the actual dbo:numberOfEpisodes value was checked through an initial query. A zero-shot prompt was proposed to both LLMs as follows. Here are the results:
![QUERY EPISODES](https://i.imgur.com/XcxtieO.png) 
ChatGPT
![QUERY EPISODES](https://i.imgur.com/sbnODQ6.png)
![QUERY EPISODES](https://i.imgur.com/V4PQq1a.png)
GEMINI
![QUERY EPISODES](https://i.imgur.com/tXEYWrI.png)






## Challenges and LLMs Differences

Discussione sulle sfide incontrate e differenze tra i modelli di linguaggio.
