**Using the NLP on the fly API**

Gupshup has created an API called \'NLP on the fly\' that can be used to
process natural language queries. This API combines semantic search
intent extraction and entity extraction capabilities into one
easy-to-use API. The key differentiator between \'NLP on the fly\' and
other NLP tools available is that there is no necessity to train the NLP
model before implementing it. Hence the name \'NLP on the fly\'.

The API works on the basis of the variations for each intent that the
developer specifies. The developer creates a JSON that contains few
variations of all the intents along with their corresponding entities.
For instance if your chatbot has 5 possible intents and 10 variations
for each, the JSON will contain 50 variations in total. This JSON will
remain the same for any statement the user types out while using the
bot. The JSON should also contain the user input.

At any point of time, the API finds the closest match between the user
input and each of the variations specified by the developer. This match
is denoted by a parameter called \'maxIntentScore\'. Once a match is
made, the API also extracts the entities of the user statement. The
entites and maxIntentScore form part of the API response.

This guide illustrates how you can use this API with an example.

**NLP on the fly API**

**POST** http://api.gupshup.io/sm/api/v1/nlp/nlponthefly

Headers: \
\
--header \'apikey: \[apikey\]\' \
\
--header \'cache-control: no-cache\' \
\
--header \'content-type: application/x-www-form-urlencoded\' 

Data:

{

\"queries\": \[\"I want to travel to San Francisco\"\],

\"intents\": \[{

\"intent\": \"1\",

\"variations\": \[{

\"variation\": \"Travel to London\",

\"entities\": \[{

\"name\": \"location\",

\"entity\": \"London\"

}\]

}\]

}, {

\"intent\": \"2\",

\"variations\": \[{

\"variation\": \"I will pay using Credit card\"

}\]

}, {

\"intent\": \"3\",

\"variations\": \[{

\"variation\": \"I want a flight\"

}\]

}\]

}

Postman link for the
API [[here]{.underline}](https://www.getpostman.com/collections/dc147bd5a9fe051375d0)

Here, we have used the example of a travel chatbot that has 3 possible
intents

-   Travel to a city

-   Payment mode

-   Flight lookup

Of these 3 intents, only the first - travelling to a city, has an entity
associated with it.

We have constructed a JSON that captures all these intents and
variations and also specifies the corresponding entities. The
\'queries\' parameter in the JSON denotes the user input. Every time a
user types something, the input is added as the \'query\' parameter and
the rest of the JSON remains the same. The API compares what the user
has said and finds the closest match. In this instance the user
statement is \'Travel to San Francisco\' so the API matches it to
\'Travel to London\'. Since \'London\' is defined as an entity, the API
returns the entity as \'San Francisco\'.

**Sample Response:**

\[

{

\"intentWithMaxScore\": \"1\",

\"topIntents\": \[

{

\"score\": 0.3748233881723722,

\"intent\": \"1\",

\"variation\": \"Travel to London\"

}

\],

\"entities\": {

\"location\": \[

\"San Francisco\"

\]

},

\"query\": \"I want to travel to San Francisco\",

\"intentVariation\": \"Travel to London\",

\"maxIntentScore\": 0.3748233881723722

}

\]

As you can see in the sample response, the field \'topIntents\' contains
the intent that matches the user query. The API also has extracted the
entity in the \'entities\' field. The field \'maxIntentScore\' is a
score between 0 and 1 that denotes the closeness of an intent-match.

Thus you can use this API to perform natural language processing tasks
on the fly.

Do note that the API works for upto 200 variations only.

Here is a video that illustrates how to use the NLP on the fly API:
