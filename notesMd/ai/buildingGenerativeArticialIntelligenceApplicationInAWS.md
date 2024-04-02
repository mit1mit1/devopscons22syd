# Building Generative AI Applications in AWS

_Heads up: in this session, there'll be a focus on Agents and Retrieval Augmented Generation (RAG)_

## Definitions and categories

**Artificial Intelligence (AI):** Any time a computer is behaving like a mind in some way. Could be a simple algorithm, could be a chess bot, could be image generation, ...

**Machine Learning (ML):** A subset of AI. An automated search for patterns in data to build logic models.

Three non-exhaustive subsets of ML are:

**Classification AI:** Recognizes data patterns and uses it to identify something (e.g. image recognition);

**Predictive AI:** Identifies statistical patterns in data to predict future trends (e.g. health assessments);

**Generative AI:** Create new content and ideas based on existing content. It is non-deterministic and non-explainable (due to the > 200 billion input parameters, statistical randomization, and billions petaFLOPS of calculation);

### Model choices

**Open source models:**

 - Model weights are publicly available;
 - Varying size from relatively small to relatively large;
 - Varying performance;
 - Easier to fine tune and/or self deploy;
 - Can be hosted on Bedrock;

**Proprietary Models:**

- Model weights aren't available;
- Generally large;
- Generally lead in performance;
- Hard to fine tune;
  - Hence, might not be as accurate as a smaller open-source model once you fine-tune it;
- Can be expensive for extensive usage;

_Aside: the newer models are learning to cope with a larger context window. Typically, LLMs have [missed the middle](https://arxiv.org/abs/2307.03172) of large pieces of text, but there is focus and improvement on this area at present._

## How to get a Generative AI to work with my custom documents?

In increasing order of expense:

1. Train your own model with your large store of custom data;
2. Do unsupervised fine tuning;
3. Do supervised fine turning;
4. RAG;

## Retrieval Augmented Generation (RAG)

RAG works by:

1. Prior to a user query, index some documents that you want to supplement and make them available to the LLM;

2. When a user queries the LLM, perform a semantic search on the indexed docs to find semantically related parts (e.g. if the user searches for "facts about New York" and the docs contain the phrase "Big Apple", that paragraph might appear);

3. Ask the LLM to consume and summarise those paragraphs and use it to answer the user's query.

For a nice introduction to RAG, check out [research.ibm.com/blog/RAG](https://research.ibm.com/blog/retrieval-augmented-generation-RAG).

### Retrieval types

- Rules bases, e.g. perform a key word search in unstructured data, e.g. a document;
- Transactional, e.g. retrieval from a database or API;
- Semantic search, i.e. get relevant documents based on text encodings;
  - Works really well because it gives structured related data to an LLM built to consume it;
  - Works of vectorising plain English (or whatever natural language you are using); 

## AWS Marketing speal

Doesn't really need to be included, I'm sure you can just google "AWS AI solutions" and you'll get all the info.

## Use case analysis when selecting a model

### Broad considerations

- Criticality (how tolerant are you to mistakes?);
- Scale (do you have a targeted or broad audience?);
- Task type (is this an open-ended or fixed purpose bot?);
- Eloquence (does the LLM need high levels of jargon fluency?);
- What's your Return on Investment?

### Detailed considerations

A plethora of things to consider including:

Number of params, licence, speed, fine-tunability, cost, alignment to company style and brand, monitoring for bias....

### Limits of LLMs

In general, you can have a combination of quality, cost, and speed, but you can't the best of all three.

To evaluate cost and speed is trivially automated.

To evaluate quality, you can use either algorithmic or human evaluation. AWS bedrock supports both.

There's a variety of metrics you can measure (accuracy, tone, ...), and a variety of assessment methods (tick/cross, rate on a scale, ...).

## Agents

LLMs are cool, but do you know what would be cooler? If you could hook them up to external stuff so they can _do_ things as well as say things.

Enter the agent.

Now, it's a complex thing to hook an LLM up to some external services. AWS agents make it pretty simple by having the LLM on the same platform as an AWS Lambda.

Essentially, you set up a lambda function - this can process things itself, talk to an external API, even talk to another LLM.

Then you provide an OpenAPI spec for the lambda.

Finally you create an AWS Agent, tell it what it's purpose is, tell it what to use the lambda function for, and point it to the OpenAPI spec so it knows how to use it.

Importantly, you have to be verbose in natural language when telling the agent what to do, and what to use the lambda for. This is because the Agent is just an LLM deciding what to do, and LLMs take natural language as their input.

The cool part is the Agent will also output it's "decision process" - a plain language description of the steps it is taking and why it is taking them.

Note that you can also pick which LLM the Agent uses.

## What is responsible AI?

Things to consider:

- Fairness: how a system impacts different subpopulations of users;
- Explain-ability: mechanics to understand and evaluate the outputs (and make sure it isn't hallucinating);
- Robustness: mechanism to ensure the system operates reliability;
- Privacy and Security: make sure the data is protected from theft and exposure, make sure PII is protected;
- Governance: processes to define and enforce responsible practices with ai in your organisation;
- Transparency: making sure your end users (and all other stakeholders) know what you're doing and what AI you're using.

### What makes Bedrock responsible?

- Data used with bedrock doesn't improve the service, and isn't shared with third party model providers;
- Private connectivity between Bedrock and your Virtual Private Cloud is available;
- Data is encrypted at rest and in transit;
- You can customize your own FMs to control how your data is used;

Model provider has AWS service team managed accounts per region. Models are deployed on behalf of you. Even finely tuned models are kept in the service account. Isolated so no other customer can access it. No input or output is logged by AWS - you need to do logging yourself in your own customer account. PII detection is available in CloudWatch logs by the way.