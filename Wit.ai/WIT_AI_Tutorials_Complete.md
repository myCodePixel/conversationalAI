Understand

Natural Language Processing (NLP) allows you to understand the meaning
of a user input. You may need it as a stand-alone layer to parse text or
speech into structure data\
You will also need NLP to build a conversational app to understand the
user query and extract meaningful information out of it.

Categorize the user intent

Problem

You want to understand what your end-user wants to perform. **For
example:**

-   Ask about the weather

-   Book a restaurant

-   Open the garage door

The problem is that there a millions of different ways to express a
given intent. For instance, all the following expressions should be
mapped to the same intent:

"What is the weather in Paris?"\
"Give me the current weather in Paris"\
"Is it sunny or rainy in Paris now?"

Recipe

1.  Go to the Understanding tab in the Console

2.  In the Try out an expression field, type a sentence followed by
    > Enter, for example

3.  \> What is the weather?

4.  The Add a new entity dropdown will open. Type "intent" and Enter
    > (twice)

5.  Click on Value and type "weather", then Enter. It is called a trait
    > entity when the sentence as a whole means intent=weather instead
    > of one particular word ([[See
    > more]{.underline}](https://wit.ai/docs/recipes#categorize-the-user-intent)).

6.  Click the green checkmark to validate

7.  Now let's teach Wit another expression for the same intent. Repeat
    > step 2, for example with

8.  \> How is the weather?

> Wit may or may not get your "weather" intent. If it does not, select
> "intent" in the dropdown. Validate.

Of course it's not really useful to extract an intent if there is only
one possible value. You can repeat the same process for a "restaurant"
intent for example. **The more expressions you validate for each value,
the better it will work**.

![https://wit.ai/docs/images/recipes/u-intent-0d5e2d66.gif](media/image1.gif){width="10.583333333333334in"
height="6.260416666666667in"}

Extract date and time

Problem

You want to get a normalized date/time value from a raw message. For
example, the following inputs:

"What is the weather tomorrow?"\
"what is the weather on Wednesday?"\
"What is the weather on April 6?"

should all provide a datetime value of 2016-04-07T00:00:00 that you can
use in your app.

Recipe

1.  Go to the Understanding tab in the Console

2.  In the Try out an expression field, type a sentence containing some
    > kind of date/time, for example

3.  \> What is the weather tomorrow?

4.  The Add a new entity dropdown will open. Click on wit/datetime.

5.  Click Validate

Now your Wit app will try to extract and normalize date/time values from
messages.

![https://wit.ai/docs/images/recipes/u-datetime-8de33b79.gif](media/image2.gif){width="10.583333333333334in"
height="6.260416666666667in"}

 Protip

wit/datetime is a built-in entity. Like some built-in entities, it
uses [[Duckling]{.underline}](https://duckling.wit.ai/), our
open-sourced linguistic parser. Don't hesitate to have a look and
contribute if you have time.

Extract location

Problem

You want to get a location from a raw message. For example, the
following inputs:

"What is the weather here?"\
"what is the weather in Palo Alto?"\
"What is the weather at 1 Hacker Way, Menlo Park CA?"

should all provide a location entity with respective values here, Palo
Alto, and 1 Hacker Way, Menlo Park CA.

Recipe

Follow the [[Extract date and
time]{.underline}](https://wit.ai/docs/recipes#extract-date-and-time) recipe
above, with wit/location instead of wit/datetime.

 Protip

Inspired by the magicallity of Wit, you may think Wit is capable of
"resolving" the location and return a full address. This is not yet
possible and you will have to look up the address on your side.\
In other words, Wit will be able to extract a string that may be a
location, but you will have to double check on your side. More
info [[here]{.underline}](https://wit.ai/docs/complete-guide#--resolving-entities-link)

Extract a *keyword* entity

Problem

The user can order different types of pizza cheese, margherita,
or calzone and you need to get which kind they want.

Recipe

1.  Go to the Understanding tab in the Console

2.  In the Try out an expression field, type a sentence containing one
    > of the keywords you want to extract, for example

3.  \> cheese pizza

4.  With your mouse, highlight "cheese"

5.  In Add a new entity, type "pizza", then Enter

6.  Click the green checkmark. A new Entity has been created

7.  Uncheck the free-text lookup strategy in your entity (you should
    > only have the keyword selected)

8.  Click the "pizza" Entity to add the other 2 values:\`margherita" and
    > "calzone"

9.  In the Try out an expression field, type a sentence containing one
    > of the keywords, it will extract it. But it won't if this is
    > different value like "pepperoni"

![https://wit.ai/docs/images/recipes/u-keywords-8c7c171c.gif](media/image3.gif){width="13.010416666666666in"
height="7.385416666666667in"}

Related recipes

-   [[Which entity should I
    use?]{.underline}](https://wit.ai/docs/recipes#which-entity-should-i-use)

-   [[Extract an entity that generally takes a value in a predefined
    list (open
    enum)]{.underline}](https://wit.ai/docs/recipes#extract-an-entity-that-generally-takes-a-value-in-a-predefined-list-open-enum-but-you-are-open-to-new-values)

-   [[Extract an entity that is a substring of the
    message]{.underline}](https://wit.ai/docs/recipes#extract-an-entity-that-is-a-substring-of-the-message)

Extract an entity that generally takes a value in a predefined list
(*open enum*), but you are open to new values

Problem

The user can order a pizza Margherita, Napoletana, or Calzone and you
need to get which kind they want. But if they say Quatro Fromaggi and
you don't have that in your list, you still want to get this entity
value in order to either search for the closest value, propose an
alternative, or explain that you don't have that kind of pizza.

Recipe

1.  Go to the Understanding tab in the Console

2.  In the Try out an expression field, type a sentence containing one
    > of the keywords you want to extract, for example

3.  \> cheese pizza

4.  With your mouse, highlight "cheese"

5.  In Add a new entity, type "pizza", then Enter

6.  Click the green checkmark. A new Entity has been created

7.  Make sure the free-text and keyword lookup strategies are checked in
    > your entity

8.  Click the "pizza" Entity to add the other 2 values:\`margherita" and
    > "calzone"

9.  In the Try out an expression field, type a sentence containing
    > another type like:

10. \> pepperoni pizza

![https://wit.ai/docs/images/recipes/u-open-keywords-4e852487.gif](media/image4.gif){width="13.010416666666666in"
height="7.385416666666667in"}

Related recipes

-   [[Which entity should I
    use?]{.underline}](https://wit.ai/docs/recipes#which-entity-should-i-use)

-   [[Extract a keyword
    entity]{.underline}](https://wit.ai/docs/recipes#extract-a-keyword-entity)

-   [[Extract an entity that is a substring of the
    message]{.underline}](https://wit.ai/docs/recipes#extract-an-entity-that-is-a-substring-of-the-message)

Extract an entity that is a substring of the message

Problem

The user can write:

"Tell Jordan that **I will be home in ten minutes**"

and you need to extract the I will be home in ten minutes in order to be
able to send a message (to Jordan) with this body.

Recipe

1.  Go to the Understanding tab in the Console

2.  In the Try out an expression field, type the sentence:

3.  \> Tell Jordan that I will be home in ten minutes

4.  With your mouse, highlight "I will be home in ten minutes"

5.  In Add a new entity, type "message", then Enter

6.  Click the Validate button. A new Entity has been created

7.  Make sure the free-text and keyword lookup strategies are checked in
    > your entity

8.  In the Try out an expression field, type a sentence containing a new
    > message. It will be highighted now!

9.  \> Tell Alex that I will be really late

![https://wit.ai/docs/images/recipes/u-free-text-073721e4.gif](media/image5.gif){width="13.010416666666666in"
height="7.385416666666667in"}

Related recipes

-   [[Which entity should I
    use?]{.underline}](https://wit.ai/docs/recipes#which-entity-should-i-use)

-   [[Extract a keyword
    entity]{.underline}](https://wit.ai/docs/recipes#extract-a-keyword-entity)

-   [[Extract an entity that generally takes a value in a predefined
    list (open
    enum)]{.underline}](https://wit.ai/docs/recipes#extract-an-entity-that-generally-takes-a-value-in-a-predefined-list-open-enum-but-you-are-open-to-new-values)

Which entity should I use?

Built-in entities

You'll often need to extract temporal expressions, numbers, locations,
temperatures, etc. To make your developer life easier, we have
predefined these entities. They are trained across all our dataset, so
they are supposed to perform very well.\
Whenever it's possible, use these built-in entities as opposed to your
own custom entities. If you are not sure, or if you think there is a
very common entity that should be built-in, just let us know!\
All built-in entities are prefixed by wit/. You can find the full list
of built-in
entities [[here]{.underline}](https://wit.ai/docs/complete-guide#built-in-entities-link).

Your own entities

If the entity you need is not built-in, you can create your own. You'll
have to choose a Lookup Strategy for your entity:

  **Lookup Strategy**                    **Use Case**                                                                                                                                                                                                                                                      **Examples**                    **Recipe**
  -------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------- ------------------------------------------------------------------------------------------------------------------------------
  Trait (previously known as Spanless)   When the entity value is not inferred from a keyword or specific phrase in the sentence. There is no obvious association between certain words in the sentence and the value of the entity, but rather you need the sentence as a whole to determine the value.   Intent, Sentiment, Politeness   [[Extract a trait entity/intent]{.underline}](https://wit.ai/docs/recipes#categorize-the-user-intent)
  Free Text                              When you need to extract a substring of the message, and this substring does not belong to a predefined list of possible values.                                                                                                                                  Message Body, Contact Name      [[Extract a free-text entity]{.underline}](https://wit.ai/docs/recipes#extract-an-entity-that-is-a-substring-of-the-message)
  Keywords                               When the entity value belongs to a predefined list, and you just need substring matching to look it up in the sentence.                                                                                                                                           Country, Burger, Room           [[Extract a keyword entity]{.underline}](https://wit.ai/docs/recipes#extract-a-keyword-entity)

Differentiate several entities according to their role in the message

Consider the following examples:

I want a 3 bedroom condo with 2 bathrooms\
I need to book a flight from SFO to Seatle\
Remind me to buy milk, cheese and bread

In the first example, you would want to know the number of bedrooms and
the number of bathrooms to complete your condo search. Of course one
could say "I'm looking for a 3 bathrooms and 4BR condo", so you just
can't trust the position of the entity in the expression.

The same situation arrises in the second example. You would want to
capture the destination and origin as 2 distinct locations.

![https://wit.ai/docs/images/recipes/roles-1-1e913521.png](media/image6.png){width="10.052083333333334in"
height="2.7604166666666665in"}

Recipe

1.  Go to the Understanding tab in the Console

2.  In the Try out an expression field, and type out your expression as
    > normal

> I want to go from NY to SF

3.  Create a wit/location entity for both SF and NY

4.  Click on the circle icon on the left of the entity, and click on
    > "Set a role".

5.  Type a name for your role, and press Enter.

6.  Click the green checkmark to validate

To help wit train, make sure to validate a few more examples.

![https://wit.ai/docs/images/recipes/roles-use-e0e4a15f.gif](media/image7.gif){width="10.0625in"
height="3.3333333333333335in"}

 Protip

In the third example, the different grocery items do not have any
specific roles. Sometimes, you will see occasions where you would want
to capture the position of the entity even it there is no specific
roles. In the third example you may think it could be good to know that
"milk" was mentioned first. As a result, you would end up with
a grocery\_item:first, grocery\_item:second... This is not a scalable
approach and we highly discourage you to do that. Roles are not meant
for this

So to recap, use Roles when you want to **recognize 2 entities of the
same type but that have a different roles** in user request.

Do sentiment analysis

Problem

You want to know if the sentiment of messages (or any other dimension,
like politeness, mood, etc.) is positive or negative.

Recipe

Follow the recipe to extract the user intent, but this time:\
- Name the entity "sentiment" instead of "intent"\
- Define two values "positive" and "negative"

 Protip

1.  Make sure that your "sentiment" entity, or any entity that depends
    on the expression as a whole (as opposed to a particular word or
    sequence of words appearing in the sentence), is of Strategy
    Search trait. You can check this in the Understanding tab.

2.  Your "sentiment" entity is trained by and for you. The good news is,
    it will be completely customized to your case. The bad one is, you
    need to provide several examples for each value :)

Which confidence threshold should I use?

Problem

You want to know what is the best confidence threshold for your app.

Along with each extracted entity, Wit returns a confidence level - a
value that shows how sure Wit is that it extracted the entity
correctly.\
When the confidence is too low, you might want to handle the extracted
entity differently (or ignore it altogether).\
For example, you could manage uncertainty for the intent entity [[as
described
here]{.underline}](https://github.com/wit-ai/wit-api-only-tutorial#manage-uncertainty).

But what is "too low" exactly? How does it affect the app?

Recipe

1.  Go to your entity page.

2.  Look at the Insights section. It may be empty if you haven't
    validated 50 examples for this entity yet.

3.  Look at the Precision/Recall at confidence levels graph.

This graph shows two curves for a range of confidence levels:\
- How often is Wit correct when it thinks it detected this entity in the
sentence? (precision)\
- How often does Wit detect this entity when it is actually in the
sentence? (recall)

Ideally, you want high precision and high recall.\
If it is really important for your use case to be always correct, you
need a high precision. Usually the cost of a high precision is to miss
some entities that were correct.\
If you care about extracting entities as often as possible, you need a
high recall. Usually the cost of a high recall is to have sometimes
incorrect entities (or entity values).

Let's go over an example.

Looking at a confidence of 0 shows how the model is doing when there's
no entity filtering at all.\
Here the model has a precision score of 0.9314 and a recall score
of 0.95. This is really good already.\
This is also the maximum value for the recall.

The maximum value for the precision is 1.0, which you can get for a
recall of 0.8905 (confidence level of 0.79).\
If this is what you need, extracted entities having a confidence
under 0.79 should be handled differently.

![https://wit.ai/docs/images/recipes/pr\_curves-b311119f.png](media/image8.png){width="19.645833333333332in"
height="10.125in"}

Integrate Wit everywhere

Now that your conversational app works on Wit.ai, you need to integrate
it on the platform(s) of your choice.

Integrate into my app

Problem

I want to integrate Wit to my app.

Recipe

You can integrate Wit to your app using one of our official clients or
the HTTP API:\
- [[Node.js client]{.underline}](https://github.com/wit-ai/node-wit)\
- [[Python client]{.underline}](https://github.com/wit-ai/pywit)\
- [[Ruby client]{.underline}](https://github.com/wit-ai/wit-ruby)\
- [[other (HTTP API)]{.underline}](https://wit.ai/docs/http/latest)

Don't hesitate to check out unofficial clients for your favorite
language on GitHub!

Integrate with Facebook Messenger

Problem

I want to use Wit in my Facebook Messenger bot.

Recipe

We recommend that you use [[Built-in
NLP]{.underline}](https://developers.facebook.com/docs/messenger-platform/built-in-nlp) to
receive NLP output along with the text your users send to your Messenger
bot.

Integrate into my website

Problem

I want to integrate Wit into my website.

Recipe

You can use Wit from your website. You will have to use JSONP as shown
in the
example [[here]{.underline}](https://wit.ai/docs/http/20170307#cross-domain-link).

Manage Wit apps

Copy/Export/Version my app

Problem

I would like to version my app so that I can work on the next version
while still having a production version.\
I would like to copy a public app to reuse someone else's work as the
starting point for your own app and not start from scratch.

Recipe

You can export your app in the Settings tab under "Export your data".
This will download an archive file with your app's data (entities,
values, expressions, etc.)

![https://wit.ai/docs/images/recipes/export-1d487e69.png](media/image9.png){width="10.166666666666666in"
height="1.2083333333333333in"}

**Important**\
If you modify the exported files, please use the zip command in the
app.json file to respect the zip ordering. Here is an example:

{

\"version\" : 20160513,

\"zip-command\" : \"zip SimpleApp\_SimpleExample.zip
SimpleApp\_SimpleExample/app.json
SimpleApp\_SimpleExample/entities/\*.json
SimpleApp\_SimpleExample/actions.json
SimpleApp\_SimpleExample/stories.json
SimpleApp\_SimpleExample/expressions.json\",

\"data\" : {

\"name\" : \"SimpleApp\_SimpleExample\",

\"description\" : \"Example\",

\"lang\" : \"en\"

}

}

When creating a new app, you can select the zip to import an existing
app.

![https://wit.ai/docs/images/recipes/import-37111393.png](media/image10.png){width="10.385416666666666in"
height="5.46875in"}

Share my app

Problem

I would like to invite other developers in my team to contribute to my
app.

Recipe

Whether your app is open or private, you can share it and give "write
access" to your friends and colleagues.

Go to the Settings tab of your app. Under the "Share this app" you can
enter either your friend's Wit.ai username (either Github id or Facebook
id) or just type their email. Then click enter. It will send your friend
an email with a link to your Wit app.

If your friend is already a Wit user, they will find the share app in
the list of the apps on the Wit console. If not, they will have to sign
in first in order to get access to your app. You can start working
together on the Wit app.

![https://wit.ai/docs/images/recipes/share-app-ec26d550.png](media/image11.png){width="10.145833333333334in"
height="2.78125in"}

Transfer my app

Problem

I would like to transfer the ownership of my app to another developer in
my team.

Recipe

Whether your app is open or private, you can transfer it to another Wit
user.

Go to the Settings tab of your app. Under the "Transfer ownership", you
will see the list of users that have already access to your app. Select
the wit user you want to transfer your app. If the list is empty or you
can't find the user, you will need to [[share your
app]{.underline}](https://wit.ai/docs/recipes#share-my-app) with that
user first.

![https://wit.ai/docs/images/recipes/transfer-app-3249013d.png](media/image12.png){width="10.25in"
height="2.75in"}

Delete my app

Problem

I want like to delete my app since I'm no longer use it or because it
was just a test.

Recipe

Go to the Settings tab of your app. Under the "Danger Zone" you can
delete your app. It may be good to export it before in case you need it
in the future.

![https://wit.ai/docs/images/recipes/delete-app-105da406.png](media/image13.png){width="10.166666666666666in"
height="1.7395833333333333in"}

Make my app private

Problem

I want to make my app private. Or I want to open my app to the
community.

Recipe

-   A **private app** is only visible by its owner, and the users listed
    in the "Shared with" section of the app settings.

-   A **open app** can be browsed and later forked by anybody. Only the
    Understanding page is visible, but read-only. In particular, the
    Inbox and Logs sections are not visible.

We believe that like open source code, the community will benefit from
open apps. New developers can start by importing your app so they don't
have to start from scratch and reinvent the wheel. In turn, your open
app will be able to reuse the data from the community to become smarter.
Only use private apps when you have privacy constraints. As we develop
new community-oriented features, open apps will have more benefits than
private apps.

Go to the Settings tab of your app. Under the "Danger Zone" you can make
your app private or open it to the community.
