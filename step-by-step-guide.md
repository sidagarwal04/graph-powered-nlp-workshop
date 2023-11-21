# Step-by-Step Guide to run this workshop


## Part 1: Create and load a Neo4j Instance
Step 1. Go to [Neo4j Aura website](https://neo4j.com/aura) and click on "**Start Free**" Button

![Screenshot 2023-11-21 at 3 21 07 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/67ba92fb-db3f-457c-b869-ed4b78ebf6e9)

Step 2. Create an account - login with an email address or Continue with Google and accept terms & conditions

![Screenshot 2023-11-21 at 3 22 44 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/f71ebc8f-3183-48af-bdce-8103d18ff1ad)

Step 3. Click on "**New Instance**" and then "**Create Free Instance**" to create a lifetime free instance which allows you to have 200K Nodes and 400K Relationships

![Screenshot 2023-11-21 at 3 24 23 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/f6f62de6-e11b-49f6-8e74-2a0263cadcaa)

![Screenshot 2023-11-21 at 3 24 35 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/a8873589-67cb-48ba-b4c5-b12a080c466f)

Step 4. Download the password file and keep it safe as you would be needing it later to connect to the database. Wait until your instance is created and then click on "**Query**" button to open the Neo4j Workspace

![Screenshot 2023-11-21 at 3 26 39 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/a82f2d99-482a-440a-a7a2-2a428e2b209b)

![Screenshot 2023-11-21 at 3 28 23 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/48d6840c-a8cc-4928-8474-bb0bba016e45)

Step 5. Next enter the password mentioned in the text password file you downloaded in previous step (Step 4) and click on "**Connect**" button to connect to the Neo4j Database

![Screenshot 2023-11-21 at 3 29 43 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/29a4600c-9555-43b4-a124-41e670207806)

Step 6. Copy the contents of [movies-db-setup.cypher](movies-db-setup.cypher) file in this repo (Cypher code) and paste in the first prompt of the Neo4j Database and click on the "**Play**" button to load the database with Movies dataset.

![Screenshot 2023-11-21 at 3 33 36 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/5311f58d-30e4-4aa7-932e-e30079e1159e)

![Screenshot 2023-11-21 at 3 32 38 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/65899c18-3eb0-49e7-aec0-e874cd1805b2)

Step 7. Once the cypher code is successfully executed, the Neo4j database will be loaded with Movies dataset containing 171 Nodes (Persona and Movies) and 253 Relationships (ACTED_IN, DIRECTED, FOLLOWS, PRODUCED, REVIEWED, WROTE).

![Screenshot 2023-11-21 at 3 36 55 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/d6180484-d894-4ba8-87f3-03dd4548cb40)

Step 8. You can additionally type following Cypher code "**MATCH (n) RETURN n**" to view the entire visualization of loaded dataset in Neo4j
    
![Screenshot 2023-11-21 at 3 49 10 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/e312b30c-68a8-4481-ad01-e84b50d628eb)




## Part 2: Create Google MakerSuite account, train & test prompt in Google MakerSuite and get Google PaLM 2 API-Key
Step 1. Go to [Google MakerSuite website](https://developers.generativeai.google/products/makersuite), click on "**Go to MakerSuite**" and login via your Gmail account (if you are using business email-id and your administrator has not enabled early-access to applications, then switch to your personal account for this workshop to generate API Key in later steps)

![Screenshot 2023-11-21 at 4 06 00 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/f1b90ece-f44d-48e3-b83c-2a27bc1eadb3)

Step 2. On the MakerSuite homepage, click on "**Create**" under Text Prompt on the homepage

![Screenshot 2023-11-21 at 3 53 26 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/ea52d925-33a0-427b-9d6d-f82a4e5e32c6)

Step 3. Copy the contents of sample prompt to generate Neo4j Cypher Code available in [Neo4j_Cypher_Query_Generator_Prompt.txt](Neo4j_Cypher_Query_Generator_Prompt.txt) file in the repo, paste in the Google MakerSuite and click "**Run**" button.

![Screenshot 2023-11-21 at 4 54 17 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/8b393d04-c8db-4b66-8c81-0104664f50fb)

![Screenshot 2023-11-21 at 4 55 28 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/f760756f-4f5c-42b7-94d9-728643e33417)

Step 4. Google MakerSuite has now trained a model based on sample prompts. You can test the model by clicking on curly brackets ({}) next to "Insert", enter the test input as "**Who is the director for the movie V for Vendetta**" and click "**Run**" to generate cypher code based on the test input

![Screenshot 2023-11-21 at 4 57 17 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/38e399ce-ebf5-4a8b-a58c-39aa3a69d38f)

Step 5. Click on "**Get Code**" and then click "**Copy Code**" to copy the generated prompt to be called from the PaLM API in our python notebook later on in Part #3. As next step, click on "**Create your API Key**". Make sure to save your prompt before leaving the window

![Screenshot 2023-11-21 at 5 07 54 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/50bb9a02-a821-483a-a475-c1dc873ddaa5)

![Screenshot 2023-11-21 at 5 08 00 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/2cfee0b3-5091-441d-abdb-c61fe87c0be7)

Step 6. On the "API Keys" page click on "**Create API key in new project**" to generate the API key and then click on "**Copy**" to copy the key to embedded in the code later in Part #3

![Screenshot 2023-11-21 at 5 16 19 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/4cfe0c5e-c601-405d-9261-034a40791582)

![Screenshot 2023-11-21 at 5 17 09 PM](https://github.com/sidagarwal04/graph-powered-nlp-workshop/assets/2035658/548daed4-c60c-40fb-9e1f-18e14bcd06e2)




## Part 3: Build things together in Python with Google Colab
