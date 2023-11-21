# Graph Powered NLP Workshop

Are you ready to dive into the world of graph databases, harness the power of natural language processing (NLP), and build intelligent applications that understand and respond to human queries? Follow this [**step-by-step guide**](step-by-step-guide.md) to embark on a thrilling journey that combines the strength of [Google PaLM 2](https://ai.google/discover/palm2/) (within [Google MakerSuite](https://developers.generativeai.google/products/makersuite)), [Neo4j](https://neo4j.com/), and Python and build an intelligent Gen-AI powered Q&A Chatbot. For this workshop, we will be using Movies dataset with **PERSON** and **MOVIE** as nodes and **ACTED_IN**, **DIRECTED**, **FOLLOWS**, **PRODUCED**, **REVIEWED**, **WROTE** as Relationships. Refer to the [slide deck](https://github.com/sidagarwal04/graph-powered-nlp-workshop/blob/main/Graph%20Powered%20NLP%20using%20Google%20PaLM%202%2C%20Neo4j%20and%20Python.pdf) for additonal reference.

**Duration:** 180 minutes
**Level:** Beginner to Intermediate

## Gen-AI and LLMs
Generative AI (Gen-AI) refers to a subset of artificial intelligence technologies that can generate new content, including text, images, music, and code, after learning from a vast dataset. These models can create original outputs that have never been seen before, as opposed to simply analyzing or classifying data.

Large Language Models (LLMs) are a specific type of Gen-AI that are particularly adept at understanding and generating human language. LLMs are trained on a massive corpus of text data, which enables them to perform a variety of language tasks, such as translation, question-answering, summarization, and content creation. They work by predicting the next word in a sequence of words, making them capable of generating coherent and contextually relevant text passages.

LLMs have revolutionized the field of natural language processing (NLP) due to their ability to handle complex language tasks that were previously challenging for machines. They have become foundational to a number of AI-driven applications, providing the backend intelligence for chatbots, writing assistants, and more. However, their capabilities also raise important considerations regarding ethics, biases in training data, and the potential for misuse, which are areas of ongoing research and discussion in the AI community.

![0dfd20dd-next-gen-ai-blog-image1-scaled](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/a2685bda-d9b6-4eb9-bdc7-4ab8ab745557)

## Google PaLM2
PaLM-2, which stands for "Pathways Language Model 2," is Google's second-generation large language model that underscores the company's commitment to responsible AI development and deployment. All versions of PaLM-2 undergo rigorous evaluations to assess potential harms, biases, capabilities, and their suitability for both research and practical applications ([Source](https://ai.google/discover/palm2#:~:text=PaLM%202%20is%20grounded%20in,PaLM))​​.

This model represents a significant advancement with enhanced multilingual, reasoning, and coding capabilities. It has been heavily trained on multilingual text, covering over 100 languages, which allows for improved performance on tasks across different languages​​ ([Source](https://blog.google/technology/ai/google-palm-2-ai-large-language-model/#:~:text=PaLM%202%20is%20a%20state,spanning%20more%20than%20100%20languages)).

PaLM-2 is a part of Google's lineage of breakthrough research in machine learning. It plays a crucial role in powering generative AI features and tools developed by Google, such as the Bard chatbot and the PaLM API, which are used for creating AI-driven applications​​ ([Source](https://ai.google/#:~:text=PaLM%202%20is%20our%20next,Our%20quantum%20error%20correction%20milestone)).

Importantly, PaLM-2 has been integrated into nearly 25 Google products, demonstrating its extensive utility and the trust Google places in its performance and reliability. Its applications span a wide range of Google's services, including Gmail and Google Docs, indicating its pervasive influence across the company's product suite​​ ([Source](https://www.cnet.com/tech/computing/palm-2-is-a-major-ai-update-built-into-25-google-products/#:~:text=PaLM%202%20is%20a%20second,Bard%20chatbot%2C%20Gmail%2C%20Google%20Docs)).

![palm_api_(1)](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/6fd097f3-8d9a-41f0-8af4-259bd2f7e2d8)

## Google MakerSuite
Google MakerSuite is a tool designed to facilitate the building of generative AI applications. It provides an efficient user interface (UI) for interacting with some of Google's latest AI models, allowing for the easy translation of prompts into production-ready code that can be integrated into applications​​ ([Source](https://developers.googleblog.com/2023/09/make-with-makersuite-part1-introduction.html#:~:text=What%20is%20MakerSuite%3F%20MakerSuite%20is,can%20integrate%20into%20your%20applications)). MakerSuite is browser-based and functions as an integrated development environment (IDE) specifically for prototyping with generative language models. It supports rapid experimentation with different prompts and models, and once a developer is satisfied with their creation, the tool enables easy exportation of the project to Python code. This code can then interact with the same models via the PaLM API​​ ([Source](https://developers.generativeai.google/tutorials/makersuite_quickstart#:~:text=MakerSuite%20is%20a%20browser,Which%20prompt)).

The aim of MakerSuite is to democratize the creation of AI-powered applications, making it accessible to any individual with a Google account. It simplifies the process of building with the PaLM API, which is a platform for machine learning and natural language processing tasks. By utilizing MakerSuite, developers can rapidly prototype and test configurations used in conjunction with the PaLM API, thereby streamlining the development of products and services that leverage Google's generative AI capabilities​​ ([Source](https://www.packtpub.com/article-hub/getting-started-with-google-makersuite#:~:text=Getting%20Started%20with%20Google%20MakerSuite,interacting%20with%20the%20PaLM%20API)).

Furthermore, Google has expanded the reach of MakerSuite to cover 179 countries and territories, making it available to anyone who has a Google Workspace account. This expansion is part of Google's initiative to help users from various backgrounds become AI makers and create innovative applications using their generative models​​ ([Source](https://developers.googleblog.com/2023/08/makersuite-expands-adds-new-features-for-ai-makers.html#:~:text=With%20MakerSuite%20we%20want%20to,with%20a%20Google%20Workspace%20account)).

![G4D-Makersuite-Expands-Social-v2](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/77314bb0-140b-4778-af7e-98bd6fdfb997)


## Neo4j AuraDB
Neo4j AuraDB is a cloud-based graph database service offered by Neo4j. It's designed to provide users with a fully managed graph database as a service (DBaaS), enabling rapid and efficient queries that facilitate real-time analytics and insights ([Source](https://neo4j.com/cloud/platform/aura-graph-database/faq/#:~:text=General%20What%20is%20Neo4j%20AuraDB%3F,time%20analytics%20and%20insights))​​. The service is built to be highly available and self-healing, ensuring that it can scale on demand without any loss of service. It includes enterprise-class security features, such as role-based access control in the enterprise tier ([Source](https://aura.support.neo4j.com/hc/en-us/articles/17081071326739-Neo4j-AuraDB-and-Neo4j-AuraDS-products#:~:text=AuraDB%2C%20is%20the%20Neo4j%20graph,with%20the%20enterprise%20tier%20level))​​.

AuraDB is known for its lightning-fast performance and scalability, which are crucial for graph analytics applications. It allows users to start for free and makes it easy to integrate with various languages and frameworks. The service also offers prebuilt datasets to help users get started quickly​​ ([Source](https://neo4j.com/cloud/aura-free/#:~:text=Neo4j%20AuraDB%20is%20a%20fully,your%20favorite%20languages%20and%20frameworks)).

Furthermore, Neo4j AuraDB is tailored to leverage the relationships in data, which is a core advantage of graph databases. This purpose-built service enables users to execute complex queries and gain insights with high speed, which is especially beneficial for applications that require real-time data analysis ([Source](https://neo4j.com/docs/aura/auradb/#:~:text=Neo4j%20AuraDB%20is%20a%20cloud,support%20in%20this%20overview%20page))​​.

![Screenshot 2023-11-21 at 8 40 06 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/72a40e90-9fb2-441d-bd6b-691c42074859)
