**Introduction to Flow Bot Builder**

**About**

The Flow Bot Builder is a graphical tool to build bots. You can a fully
functional chatbot without writing complex code. This tool also offers
support for structured messages and NLP.

Here are few highlights of this tool: 

 Build bots within a few minutes! 

 No programming knowledge required. 

 Tree view for your complete bot flow. 

 Seamlessly Integrated with Gupshup NLP framework. 

 Built in testing tool. 

 One click deploy on the server. 

 Publish to the supported messaging channels. 

 Built on the powerful IDE for developers to build custom JS modules
and functions, if required.

 

**Overview**

The Flow Bot Builder comprises of 4 sections: 

![Image1](media/image1.jpeg){width="9.947916666666666in"
height="4.875in"}

1.    ***Script Designer:*** In this section you have to write the
script of the bot. There are two important buttons

1.  Bot Says: which lets you define the bot response to the user

2.  User Says: which lets you define the user query to the bot.

You can also add buttons and carousel to the bot response to the user.

2.    ***Tree viewer:*** This section is the flow diagram of your
script. Each node is created when you add a bot response or user query.
Selecting a node will display the respective script in the Script
Designer.

3.    ***Talk to your bot:*** This is the chat widget which allows you
to test your script before even deploying it on the server.

4.    ***Menu items:*** This section contains various buttons for
various tasks.

a.    ***Dashboard:*** Takes you to your developer dashboard.

b.    ***Switch to IDE:*** Generates the IDE Bot Builder code for the
bot script that you have created.

c.    ***Deploy:*** Deploys the bot on production server.

d.    ***Test on Facebook:*** Takes you to the Gupshup Proxy Bot for
testing your bot script.

e.    ***Publish your Bot:*** Takes you to the publishing tab where you
can publish your bot to all the supported channels.

f.    ***Bot Configuration:*** Allows you to set NLP threshold, enable
logs & analytics and also setup fallback message.

g.    ***Tutorials:*** Gives you a basic tour of the Flow Bot Builder

h.    ***Documentation:*** Opens the documentation for the Flow Bot
Builder.

Getting started
===============

To get started you need to go to
the [dashboard](https://www.gupshup.io/developer/dashboard) and create a
new bot by clicking the + sign and then select the option of "Flow Bot
Builder" under the "Code-free bot building". Once created, you will be
able to open the Flow Bot builder.

Once the Flow Bot Builder loads this is the screen you will see

![imageofdefaultscript](media/image2.jpeg){width="9.34375in"
height="3.6875in"}

This contains the default script. Each node in the tree view represents
either the bot state or the user state. You can select each node to view
the corresponding script in the "Script Designer" section.

***Things to remember***

1.   "Bot Says" corresponds to the bot state. Using the "Bot Says"
button you can create the message from the bot to the user.

2.   "User Says" corresponds to the user state. Using the "User Says"
button you can define the user\'s message(intent) to the bot.

3.   A bot state can be followed by either a user state or another bot
state but a user state can only be followed by a bot state.

Let\'s build a "Hello world" bot but first, we need to delete the
default script. To edit a node read the "Edit the Script" section of
this document (link to manage your script).

Once deleted follow these steps to build the "hello world" bot.

***Step 1\>*** **Welcome message:** In the script designer section, you
will see a Bot message "Hello I am a bot". This is the first bot message
that gets sent to the users when they click on "Get started" on facebook
messenger or open the chat widget on a website. You can change it as
required but for our example we will leave it as it is.

***Step 2\>*** **Adding user\'s message:** Since the welcome message is
sent by the bot you can choose to either add a bot state ("Bot Says") OR
a user state ("User says") as the next step. \
For our "Hello world bot" let\'s add a user state where a user will say
"Hi" to the bot. \
Click on "User says" and type "Hi" then select "Done".

This is how your script and tree view should look like

![Image of Hi script](media/image3.jpeg){width="9.197916666666666in"
height="2.6875in"}

This means that after the Bot\'s welcome message, the bot will be
expecting the user to enter "Hi".

***Step 3\>*** **Adding bot\'s response:** The bot has to respond to
user\'s "Hi" with a "Hello world!" message. For this, we need to add a
bot state. Click on "Bot Says" and type "Hello world!? then select
"Done". This is how your script and tree view should look like

![image of helloworld](media/image4.jpeg){width="9.197916666666666in"
height="2.9583333333333335in"}

Voila! Your Hello world bot is ready. To quickly, test your bot click on
"Talk to your bot" icon on the bottom right.

![testingHelloworld](media/image5.jpeg){width="4.260416666666667in"
height="4.1875in"}

For testing this on Facebook messenger or any other messaging channel
supported by Gupshup please check out
this [guide](https://www.gupshup.io/developer/docs/bot-platform/guide/getting-started-flow-builder).

**Adding Structured Messages**

With the Flow Bot Builder, you can also send carousels and quick
replies. In this section, we\'ll look at how you can send carousel and
quick replies from your bot.

1.  [Carousel](https://www.gupshup.io/developer/docs/bot-platform/guide/structured-messages-flow-builder#carousel)

2.  [Quick
    > Reply](https://www.gupshup.io/developer/docs/bot-platform/guide/structured-messages-flow-builder#qr)

**Carousel**

Carousels are the horizontal scrollable elements with image, title and
buttons for users to trigger an action. To send a carousel, click on
"Bot Says" and then, click on the carousel icon 

![carouselicon](media/image6.jpeg){width="0.59375in" height="0.59375in"}

You should find this screen

![carouselmainscreen](media/image7.jpeg){width="6.833333333333333in"
height="5.583333333333333in"}

You can enter a title, an image, a subtitle and up to 3 buttons. You can
also add up to 10 more carousel items by clicking the plus sign.

In the example below, we have added 2 carousel items with 2 buttons each

![carouselexample](media/image8.jpeg){width="6.833333333333333in"
height="6.010416666666667in"}

the tree view for the above example will looks like this

![treeviewcarousel](media/image9.jpeg){width="6.114583333333333in"
height="5.5in"}

***NOTE:*** There are 4 user states created for the carousel in our
example. These 4 user states are for the 4 buttons that were created (2
buttons for each carousel item).

***Button types in Carousel***

Carousel supports three types of buttons:

1.  Text message

2.  URL

3.  Phone number

![carouselbutton](media/image10.jpeg){width="3.53125in"
height="0.5729166666666666in"}

You can choose one of these types depending upon your requirement. \
 

**Quick Reply**

Quick reply consists of a query text and array of buttons as suggested
responses. These buttons will disappear once the user selects the
response. To add a Quick reply, click on "Bot Says" and then click on
this icon

![quickreplyicon](media/image11.jpeg){width="0.5833333333333334in"
height="0.5729166666666666in"}

You will find this screen 

![quickreplymain](media/image12.jpeg){width="6.71875in"
height="4.0625in"}

You can enter a query text and add the suggested response as the button
name. You can also add up to 11 buttons by clicking on the plus sign.

In the example below, we have created a quick reply with two buttons 

![quickreplyexample](media/image13.jpeg){width="6.854166666666667in"
height="2.5625in"}

the tree view for above example will look like this 

![quickreplytree](media/image14.jpeg){width="2.7916666666666665in"
height="3.2708333333333335in"}

You will notice that there are 2 user states created for our example.
These 2 user states are for the 2 buttons that we have created.

**Managing your script**

With the Flow Bot Builder, you have the option to view, add and edit the
script of your bot. In this guide we will look at how can you

1.  [View the
    > script](https://www.gupshup.io/developer/docs/bot-platform/guide/managing-your-script-flow-builder#view)

2.  [Add to the
    > script](https://www.gupshup.io/developer/docs/bot-platform/guide/managing-your-script-flow-builder#add)

3.  [Edit the
    > script](https://www.gupshup.io/developer/docs/bot-platform/guide/managing-your-script-flow-builder#edit)

4.  [Adding
    > variations](https://www.gupshup.io/developer/docs/bot-platform/guide/managing-your-script-flow-builder#variation)

5.  [Bot
    > Flows](https://www.gupshup.io/developer/docs/bot-platform/guide/managing-your-script-flow-builder#flow)

**View the script**

In order to view the script, you need to click on the desired node in
the "Tree View" section and the associated script will be displayed in
the "Script Designer" section on the right. The Script Designer will
show the script of the selected node as well as the nodes above in that
flow.

For example:

In the image below the last node is selected and the complete script of
that flow is being displayed.

![view\_script](media/image15.jpeg){width="9.385416666666666in"
height="4.427083333333333in"}

 

**Add to the script**

You can add either a bot state or a user state depending upon the node
you choose. To do so, select a node and then in the "Script Designer"
click on either "Bot Says" or "User Says" to add. This will then appear
as a new node in the "Tree view" section.

***NOTE:***

1.  For a bot state node, you will see both the options of "Bot Says"
    > and "User Says".

2.  For a user state node, you will only see the option of "Bot Says".

 

While improving your script you may want to \
1.  Add more to the end of the flow.

OR

2.  Add more in the middle of the flow.

 

***Adding to the end of the flow:***

Let\'s say you have a quick reply in the script like below

![add\_script](media/image16.jpeg){width="9.34375in"
height="4.489583333333333in"}

Now you want to add the bot responses to the button selection of the
quick reply. You can select the user state node and then click on "Bot
Says" to add the bot response.

![add\_script\_2](media/image17.jpeg){width="9.083333333333334in"
height="4.291666666666667in"}

The final result will be like

![add\_script\_3](media/image18.jpeg){width="9.322916666666666in"
height="3.8229166666666665in"}

Similarly, you can click on the other user state and add a bot state to
it and so on.

  \
 

***Adding in the middle of the flow:***

Let\'s say you have a script like this one

![drag\_drop1](media/image19.jpeg){width="13.15625in"
height="6.416666666666667in"}

clicking on "Watches" will send a quick reply asking for the brand but
let\'s say you want to add one more quick reply asking for the gender
before sending the quick reply for the brand.

To do so, you can simply:

1.  drag the brand quick reply to another node

2.  add the quick reply for gender

3.  drag back the brand quick reply

 

***to drag away***: click on the node and drag your mouse. You will see
various nodes highlighted using the dotted box.

![drag\_drop2](media/image20.jpeg){width="13.114583333333334in"
height="5.697916666666667in"}

These are the nodes to which you can drag and drop the selected node.

 

***to add***: simply follow the example on the top to add a quick reply
for asking the gender. 

![drag\_drop3](media/image21.jpeg){width="13.177083333333334in"
height="6.34375in"}

 

***to drag back***: just select the node that you had moved and drag it
back below the response of the gender quick reply

![drag\_drop4](media/image22.jpeg){width="13.21875in"
height="6.447916666666667in"}

thus by using drag and drop feature, you can add to the middle of the
flow.

 

**Edit the script**

You can also edit the script at any given point. In the "Tree View"
click on the node to edit. Now, in the "Script Designer" section hover
or click on the down arrow button of the corresponding state. It will
display options to

1.  Edit the label

2.  Edit the message

3.  Delete the message

4.  Add the fallback matcher(checkbox)

![editscript](media/image23.jpeg){width="6.78125in"
height="2.2395833333333335in"}

***NOTE:***

1.  The fallback matcher is displayed only for bot states that have user
    > states as children. Like a quick reply. To know more about the
    > fallback matcher do read this guide.

2.  You cannot change the type of a bot state i.e. if a bot message is
    > of type text, you cannot change it to a quick reply or a carousel.
    > You will have to delete that message and create a new one.

Sample of the edit screen for a quick reply

![editscript](media/image24.jpeg){width="4.75in" height="4.125in"}

 

**Adding variations**

You can add variations to the intents from the users or to the responses
from the bot which are of type text.

***Adding variations to user intents***

All the nodes that you have scripted as "User says" are treated as the
user intents by the script and the NLP engine. There could be a case
where you would like to add some variations to those intents. You can do
so by adding them in the variation section

![user\_variations](media/image25.jpeg){width="4.958333333333333in"
height="3.46875in"}

Thus the NLP engine will pick that state by comparing the main intent
and the variations.

 

***Adding variations to bot responses***

You can randomise the responses sent by the bot to the user.

![bot\_variations](media/image26.jpeg){width="5.0625in"
height="3.5416666666666665in"}

Just add the variations in the section and system will pick one of the
provided responses

 

**Bot Flows**

Using Flow Bot Builder to create an extensive conversational bot with
multiple flows can quickly become complicated. Take a look at below tree
structure of a bot with multiple flows 

![big flow](media/image27.jpeg){width="14.0625in"
height="5.510416666666667in"}

In the above image there multiple flows a user can go to and to manage
all these in a single window becomes difficult. Hence we have introduced
bot flows.

***Few benefits of Bot flows:***

1.  You can modularize your bot making it easy to maintain.

2.  Testing and debugging an issue becomes easy.

3.  Editing the bot like adding new content or editing existing one
    > becomes easy.

 

***How to create a flow:***

You can create a new flow by expanding the Bot flows icon and clicking
on the "Create a flow" button present on the menu items on the left-hand
side of the screen. 

![create\_bot\_flow](media/image28.jpeg){width="5.177083333333333in"
height="2.7708333333333335in"}

Once you have entered a name for the flow you will be taken to edit the
script of that flow. You can then add/edit/delete the content of the
flow using the usual steps of the Flow Bot Builder.

Name of the flow should be alphanumeric and should not contain any space
or special character.

Example:

I have a bot that has 6 different options(flows) for the user. 

![bot\_flow\_create1](media/image29.jpeg){width="13.28125in"
height="3.65625in"}

Now, I can go ahead and create 6 different flows for each of these
options. 

![bot\_flow\_create2](media/image30.jpeg){width="14.020833333333334in"
height="4.166666666666667in"}

"main" is the default flow and is the starting point for the bot. Also,
the flow that is being edited is shown as active using the green dot.

 

***How to link a flow***

Select the node in the tree view that should call a flow. Then click on
the "Link" icon. You should see the option as "Call another flow" 

![call\_another\_flow](media/image31.jpeg){width="7.03125in"
height="5.3125in"}

Once you click on the "Call another flow" you will be presented with an
option to select the flow that the bot should go to

![call\_another\_flow\_2](media/image32.jpeg){width="6.854166666666667in"
height="5.020833333333333in"}

after the selection, the tree view will be updated with a sign
representing that the node is calling another flow.

![call\_another\_flow\_3](media/image33.jpeg){width="13.208333333333334in"
height="4.541666666666667in"}

 

***How to test a flow***

The web widget for testing will display a drop down to select the flow
you want to test

![bot\_flow\_testing2](media/image34.jpeg){width="3.3125in"
height="2.0208333333333335in"}

and then you can click on the "GO" button.

![bot\_flow\_testing2](media/image35.jpeg){width="3.3541666666666665in"
height="0.9479166666666666in"}

You can even select to test the complete bot.

**Linking, Fallback Matcher, and Branching**

Along with managing the script you can also link two different states or
add an exception handler or add branches to a defined flow to your
script on Flow Bot Builder. Let\'s look at each one of them.

1.  [[Linking]{.underline}](https://www.gupshup.io/developer/docs/bot-platform/guide/linking-fallback-branching-flow-builder#link)

2.  [[Fallback
    > Matcher]{.underline}](https://www.gupshup.io/developer/docs/bot-platform/guide/linking-fallback-branching-flow-builder#fall)

3.  [[Branching]{.underline}](https://www.gupshup.io/developer/docs/bot-platform/guide/linking-fallback-branching-flow-builder#branch)

**Linking**

You can link two different states using the link button. Say, you want
to send the same bot response for different user states then you can
link all those user states. The link between two states is depicted by a
dotted line connecting them.

There are few pointers to remember while using the linking feature.

1.    You should always create the link with a state above the state
that needs to be executed.

Example: In the image below, for one of the options of the quick reply
we want to send the bot response of the carousel. Hence we linked the
user state of the quick reply to the state above that bot response. 

![imageoflinking2](media/image36.jpeg){width="3.2916666666666665in"
height="4.697916666666667in"}

1.      You should only link a user state to a bot state like in the
    > example above.

2.      You can link a bot state to either a bot start or a user state.

To create a link, select the node from the tree view and then select the
"Link" button 

![linking](media/image37.jpeg){width="4.34375in" height="1.5in"}

then select the node above the state that you want to be executed by
clicking on the "Select Node" button. 

![linking3](media/image38.jpeg){width="4.395833333333333in"
height="1.9479166666666667in"}

Once created you should see the dotted blue line between the two linked
nodes. This is only visible if you select the node for which the link is
created.

 

**Fallback Matcher**

The concept of the fallback matcher is similar to the concept of
"Exception handling" in the [[Bot Scripting
tool]{.underline}](https://www.gupshup.io/developer/docs/bot-platform/guide/state-exception-bot-scripting).
The fallback matcher can be added to a state with multiple
branches(child nodes) like a quick reply or a carousel. You need to
check the checkbox shown below to activate fallback matcher feature. 

![fallback1](media/image39.jpeg){width="7.03125in" height="2.28125in"}

This is a very useful feature. Let\'s you have a quick reply with 2
options which then have their own branches like in the image below. 

![fallback2](media/image40.jpeg){width="6.552083333333333in"
height="3.09375in"}

Now, lets user selects "shoes" at the start and the carousel is
displayed to the user. But now the user enters "watches" instead of
selecting any shoes from the carousel. By default, the bot will try to
search for "watches" in the nodes of the carousel and if it\'s not found
the bot will throw the default fallback message{need to add a link to
another doc.} to the user.

To avoid this you need to check the fallback matcher option for the
quick reply on the top. By doing so you will force the bot to go to the
state where the fallback matcher is checked and search again.

Hence look at the screenshot below, when the user types "watch" after
going into the flow of "shoes" the bot is able to go back to the top and
initiate the "watches" flow.

![fallback3](media/image41.jpeg){width="2.1041666666666665in"
height="3.21875in"}

 

**Branching**

You can create additional user states for both the quick reply and the
carousel. These will not be part of the options displayed to the user.
This is useful in handling user queries that are not part of the options
of the structured messages.

For example: Let\'s take the same scenario that we discussed in the
fallback matcher above. After selecting the "Shoes" at the start user
might say "start over" to restart the flow. Now even with fallback
matcher, this will throw the default fallback message because there is
no such state at the top most quick reply.

To solve this problem you can create a new branch in the quick reply.
Select the quick reply and then click on "User Says" in the script
designer section. Then add the user message as "start over" and click
"Done". This will create a new branch called "start over". 

![branching1](media/image42.jpeg){width="4.583333333333333in"
height="2.7708333333333335in"}

Once you have created the branch you can then link this to the same
quick reply so that the user gets the first message of the flow. 

![branching2](media/image43.jpeg){width="6.15625in"
height="3.0208333333333335in"}

Thus the end result will be like: 

![branching3](media/image44.jpeg){width="2.3125in"
height="3.5520833333333335in"}

Adding Small talk and Bot configurations
----------------------------------------

Using the Flow Bot Builder you can add small talk module and also tweak
few configurations for the bot like the fallback message or NLP
threshold etc. Let\'s look at these in this guide.

1.  [Small
    > talk](https://www.gupshup.io/developer/docs/bot-platform/guide/small-talk-n-bot-config-flow-builder#small)

2.  [Bot
    > configurations](https://www.gupshup.io/developer/docs/bot-platform/guide/small-talk-n-bot-config-flow-builder#config)

Small talk
----------

Typically, small talk questions such as greetings and access-to-help
menus can be configured using the small talk module in the Flow Bot
Builder. A powerful feature of the small talk is that you do not have to
worry about the user state in the flow. Small talks are stateless hence
the bot will respond to the user irrespective of where the user is at in
the flow. Also, making small talk will not change the current state of
the user.

To add a small talk module you need to click on the small talk icon from
the menu on the left. 

![smalltalk1](media/image45.jpeg){width="0.7604166666666666in"
height="0.7708333333333334in"}

You will get this screen to add the small talk module. 

![smalltalk2](media/image46.jpeg){width="7.572916666666667in"
height="3.15625in"}

You can add the expected user query(user intent) on the left and the bot
response to that query on right. You can also add variations to the user
query or the bot response by clicking "Add variations".

***NOTE:***

1.    Adding variations to the user query means that the bot should
consider them all as the same query from the user and send the
appropriate bot response back.

2.    Adding variations to the bot responses means that the bot can send
any one of those responses randomly to the user.

You can also add more small talks by clicking on the "+ Add More"
button. Once you have added all the small talks you can click on "Done"
to save the small talk module. 

![smalltalk3](media/image47.jpeg){width="7.5625in"
height="4.010416666666667in"}

 

### Turning off Small talk

When you add small talk to your bot, Gupshup\'s NLP is called every time
to match the intents from the user. This might cause your bot to break
in cases where you are expecting an open-ended response from the user.

For example:

In a specific flow of your bot, you want users to enter their email
address. Now an email address is different for different users. With
Small talk added to the bot Gupshup\'s NLP will be called and since the
email address will not match the example entered by you in the bot
script, your bot will send out the default failure message.

There is a way to stop this from happening. You can turn off the Small
talk for that specific flow, so that the NLP engine is not called and
bot accepts any input from the user.

 

***Rule for Turning off Small talk***

1.  You can only turn this off for a bot state with a single child state
    > associated.

2.  You can only do this for a bot state with message type as text.

 

***How to turn Small talk off***

Select the bot state before the user state from the tree view for which
small talk has to be turned off. Then in the script designer hover or
click on the down arrow button. You should see options as displayed in
the screenshot below

![smalltalk](media/image48.png){width="14.854166666666666in"
height="1.78125in"}

click on the chat like option beside the edit button and you are done.

 

Bot configurations
------------------

There are 4 different bot configurations that you can tweak. To access
the bot configuration click on this icon from the menu on the left. 

![botconfig1](media/image49.jpeg){width="1.125in"
height="0.7708333333333334in"}

***Threshold***: 

![botconfig2](media/image50.jpeg){width="4.15625in"
height="2.4479166666666665in"}

As the Flow Bot Builder is powered by Gupshup\'s NLP framework, this
threshold is a way to configure the acceptable maxintent score for the
user intents(user says). \
The default value is set to 0.2 but you can change this to any value
between 0-1 as per your need.

 

***Fallback message***

![botconfig3](media/image51.jpeg){width="3.96875in" height="1.78125in"}

This message is triggered when the bot is not able to map any intent in
the flow. You can configure this as per your need. You can also
add [structured
messages](https://www.gupshup.io/developer/docs/bot-platform/guide/structured-messages) into
this fallback message by adding the corresponding JSON.

 

***Google Analytics*** 

![botconfig4](media/image52.jpeg){width="4.052083333333333in"
height="1.8854166666666667in"}

You can enable Google\'s analytics by toggling the on/off switch and
adding the Tracking ID of the Google analytics.

 

***Debugger*** 

![botconfig5](media/image53.jpeg){width="3.8645833333333335in"
height="1.59375in"}

By default, the "Logs" tab on
the [dashboard](https://www.gupshup.io/developer/dashboard) for your bot
with Flow Bot Builder will not generate any logs. You can turn on the
logs for debugging by toggling the on/off switch.

**Test, Deploy and Publish**

Once you are finished with your bot script you can test, deploy and then
publish your bot on different channels that are supported by Gupshup.

1.  [Testing your
    > bot](https://www.gupshup.io/developer/docs/bot-platform/guide/test-deploy-publish-flow-builder#test)

2.  [Deploying your
    > bot](https://www.gupshup.io/developer/docs/bot-platform/guide/test-deploy-publish-flow-builder#deploy)

3.  [Publishing your
    > bot](https://www.gupshup.io/developer/docs/bot-platform/guide/test-deploy-publish-flow-builder#publish)

**Testing your bot**

There are two ways to test your bot :

1.    ***Testing using the chat widget:*** The chat widget is embedded
right into the Flow Bot Builder. When you open the "Talk to your bot"
tab on the bottom right, it starts a local server and deploys the script
locally to start the bot. You can then go ahead and test out all the
flows in the script. This is really helpful because you are able to test
your bot without even deploying your script on the production server.

Sample: 

![webwidgetsc](media/image54.jpeg){width="3.59375in"
height="3.4479166666666665in"}

2.   ***Testing using the Gupshup proxy bot:*** You can also test your
script on almost all the supported messaging channels using the Gupshup
proxy bot. To test using the Gupshup proxy bot on Facebook Messenger you
can just click the "Test on Facebook" button from the menu items on the
right. For any other messaging channel you need to go to the
corresponding Gupshup proxy bot and then map your bot using "Proxy
{botname}". For more information check our
this [document](https://www.gupshup.io/developer/gupshupproxybot).

***NOTE:*** To test using the proxy bot you need to deploy your bot
first.

**Deploying your bot**

In order to deploy your bot, you need to click on the deploy button from
the menu items on the right.

![deploy](media/image55.jpeg){width="2.65625in"
height="0.7291666666666666in"}

This will deploy your bot on the production server.

**Publishing your bot**

Once your bot is deployed and tested you can publish it on all the
supported messaging channels which include Facebook Messenger, slack,
Viber etc and also your website.

![publish](media/image56.jpeg){width="2.5833333333333335in"
height="0.5729166666666666in"}

You can go check out the publishing requirement once you click on the
"Publish" button for the corresponding channel.

***NOTE:*** Flow builder automatically publishes your bot on the web
widget of Gupshup. Hence you can click on the edit button in the publish
tab and generate the script to add it to your website.

![publish](media/image57.jpeg){width="9.6875in" height="3.0625in"}

Return to main bot flow
=======================

It often happens that your bot users can be in different states or
flows. However, It is important to allow users to return to your default
/ primary bot flow. Ideally, the default state is where you want your
users to be in, after they finish a flow.

When [sending flows using our marketing
tools](https://www.gupshup.io/developer/docs/bot-platform/guide/bot-flows),
you will need to have a Return state set, such that your users can
return to the default bot state, after the flow is complete. This is
the **Return to origin Flow** feature on the Flow bot builder.

Let\'s say you have created a bot using the Flow Bot builder. Following
screen shows a sample bot flow created using flow bot builder.

![https://s3.amazonaws.com/gs-bot-images/Guides+image/return-to-main-bot-flow/1.JPG](media/image58.jpeg){width="14.125in"
height="6.875in"}

Now to return to original flow, you need to select node from which you
want to return then you need to click on "Link" button and select
"**Return to origin Flow**". That\'s it!

![https://s3.amazonaws.com/gs-bot-images/Guides+image/return-to-main-bot-flow/2.JPG](media/image59.jpeg){width="14.03125in"
height="6.875in"}

When adding the Return, you\'re allowed to add an optional message that
the user will see. After this message is triggered, your users will exit
the current flow. You can add messages like \'Thanks for participating\'
if you sent out a survey or \'Hope you like our offers\' for a offers
campaign, or even a simple \'Thanks for the info\' in case of lead
captures or feedback.

![https://s3.amazonaws.com/gs-bot-images/Guides+image/return-to-main-bot-flow/3.JPG](media/image60.jpeg){width="14.208333333333334in"
height="6.947916666666667in"}

In the Tree view, this is indicated with a red colored symbol which
indicates the point from which the current flow will return to main
flow. In the script designer, the Link button will show \'Returned\'

![https://s3.amazonaws.com/gs-bot-images/Guides+image/return-to-main-bot-flow/4.JPG](media/image61.jpeg){width="14.177083333333334in"
height="6.895833333333333in"}

For developers, who are using our scripting tool to create a bot, you
can achieve the same thing by adding {"action":"flowReturn"} in the
default.scr script file, at the state from which you want to return to
original flow.

![https://s3.amazonaws.com/gs-bot-images/Guides+image/return-to-main-bot-flow/5.JPG](media/image62.jpeg){width="14.052083333333334in"
height="3.46875in"}

Flow as a service
=================

You can now send bot flows along with your marketing campaigns. This
means, using our [Facebook broadcast Campaign
tool](https://www.gupshup.io/developer/mycampaigns) and [Growth
tools](http://www.gupshup.io/growthtool/), you can link a specific bot,
created on our platform, to the buttons on your card message.

Until now, you could broadcast or create a growth link for a specific
text message or a single card message. With flows, a complete bot flow,
with rich messages, carousels, quick replies etc., can be initiated at a
click of a button. Your messenger page can now be even more engaging and
pertinent to your users. This newly initiated bot flow will run
seamlessly on your messenger page, so you users will not realize that
they are in a new bot flow. This flow could be for lead captures,
special offers, surveys, new product launches etc.

Initiating bot flows is very easy. Firstly, creating bot flows is
essentially creating a bot. So you can continue to use our platform to
build your bots. As always, all your bot flows will be listed in your
Mybots sections. Before going into how to link flows to card buttons,
there are 2 important aspects to keep in mind:

a\) To send a bot flow, the bot should be deployed. So please ensure to
deploy your bot, else it cannot be used as a flow. \
b) Each bot flow should have a return state, at the end of the flow. If
return isn\'t set, your users will be stuck in that bot flow. You always
want your users to exit your bot flow and return to the main bot state
i.e. the default bot tied to tha t page. Even if there isn?t a bot tied
to your page, the return state must be present. This way, you users will
always be able to enter new campaign flows, when sent to them. Read up
on [how to set a Return
state.](https://www.gupshup.io/developer/docs/bot-platform/guide/return-to-main-bot-flow)

Linking flows to card buttons
-----------------------------

When configuring a card message in either the Broadcast or the Growth
tool, you will see an option called Flow.

![enterDetails](media/image63.png){width="3.2708333333333335in"
height="3.6145833333333335in"}

When you select Flow, you will need to select a bot from the list below
and done!

You will only be able to see your bots that are deployed and that are
not published to the Facebook page tied to that campaign or growth tool.
This means, you cannot use a bot that is already published to that page
for which you\'re running a campaign. You can send bot flows only via
buttons on card messages & up to 3 bot flows can be sent with a card
message but we recommend by sending one flow per campaign when starting
off with Flows.
