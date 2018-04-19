Principles of bot design

The Bot Framework enables developers to create compelling bot
experiences that solve a variety of business problems. By learning the
concepts described in this section, you\'ll become equipped to design a
bot that aligns with best practices and capitalizes on lessons learned
thus far in this relatively new arena.

**Designing a bot**
-------------------

If you are building a bot, it is safe to assume that you are expecting
users to use it. It is also safe to assume that you are hoping that
users will prefer the bot experience over alternative experiences like
apps, websites, phone calls, and other means of addressing their
particular needs. In other words, your bot is competing for users\' time
against things like apps and websites. So, how can you maximize the odds
that your bot will achieve its ultimate goal of attracting and keeping
users? It\'s simply a matter of prioritizing the right factors when
designing your bot.

**Factors that do not guarantee a bot\'s success**
--------------------------------------------------

When designing your bot, be aware that none of the following factors
necessarily guarantee a bot\'s success:

-   **How "smart" the bot is**: In most cases, it is unlikely that
    > making your bot smarter will guarantee happy users and adoption of
    > your platform. In reality, many bots have little advanced machine
    > learning or natural language capabilities. Of course, a bot may
    > include those capabilities if they\'re necessary to solve the
    > problems that it\'s designed to address. However, you should not
    > assume any correlation between a bot\'s intelligence and user
    > adoption of the bot.

-   **How much natural language the bot supports**: Your bot can be
    > great at conversations. It can have a vast vocabulary and can even
    > make great jokes. But unless it addresses the problems that your
    > users need to solve, these capabilities may contribute very little
    > to making your bot successful. In fact, some bots have no
    > conversational capability at all. And in many cases, that\'s
    > perfectly fine.

-   **Voice**: It isn't always the case that enabling bots for speech
    > will lead to great user experiences. Often, forcing users to use
    > voice can result in a frustrating user experience. As you design
    > your bot, always consider whether voice is the appropriate channel
    > for the given problem. Is there going to be a noisy environment?
    > Will voice convey the information that needs to be shared with the
    > user?

**Factors that do influence a bot\'s success**
----------------------------------------------

Most successful apps or websites have at least one thing in common: a
great user experience. Bots are no different in that regard. Therefore,
ensuring a great user experience should be your number one priority when
designing a bot. Some key considerations include:

-   Does the bot easily solve the user's problem with the minimum number
    > of steps?

-   Does the bot solve the user's problem better/easier/faster than any
    > of the alternative experiences?

-   Does the bot run on the devices and platforms the user cares about?

-   Is the bot discoverable? Do the users naturally know what to do when
    > using it?

Note that none of these questions directly relates to factors such as
how smart the bot is, how much natural language capability it has,
whether it uses machine learning, or which programming language was used
to create it. Users are unlikely to care about any of these things if
the bot solves the problem that they need to address and delivers a
great user experience. A great bot user experience does not require
users to type too much, talk too much, repeat themselves several times,
or explain things that the bot should automatically know.

Tip

Regardless of the type of application you\'re creating (bot, website, or
app), make user experience a top priority.

The process of designing a bot is like the process of designing an app
or website, so the lessons learned from decades of building UI and
delivering UX for apps and websites still apply when it comes to
designing bots. Whenever you are unsure about the right design approach
for your bot, step back and ask yourself the following question: how
would you solve that problem in an app or a website? Chances are, the
same answer can be applied to bot design.

Design a bot\'s first user interaction
======================================

**First impressions matter**
----------------------------

The very first interaction between the user and bot is critical to the
user experience. When designing your bot, keep in mind that there is
more to that first message than just saying \"hi.\" When you build an
app, you design the first screen to provide important navigation cues.
Users should intuitively understand things such as where the menu is
located and how it works, where to go for help, what the privacy policy
is, and so on. When you design a bot, the user\'s first interaction with
the bot should provide that same type of information. In other words,
just saying \"hi\" won't be enough.

**Language versus menus**
-------------------------

Consider the following two designs:

### **Design 1**

![bot](media/image1.png){width="7.103472222222222in"
height="1.6548611111111111in"}

### **Design 2**

![bot](media/image2.png){width="7.103472222222222in"
height="4.034722222222222in"}

Starting the bot with an open-ended question such as \"How can I help
you?\" is generally not recommended. If your bot has a hundred different
things it can do, chances are users won't be able to guess most of them.
Your bot didn't tell them what it can do, so how can they possibly know?

Menus provide a simple solution to that problem. First, by listing the
available options, your bot is conveying its capabilities to the user.
Second, menus spare the user from having to type too much. They can
simply click. Finally, the use of menus can significantly simplify your
natural language models by narrowing the scope of input that the bot
could receive from the user.

Tip

Menus are a valuable tool when designing bots for a great user
experience. Don't dismiss them as not being \"smart enough.\" You may
design your bot to use menus while still supporting free form input. If
a user responds to the initial menu by typing rather than by selecting a
menu option, your bot could attempt to parse the user\'s text input.

**Other considerations**
------------------------

In addition to providing an intuitive and easily navigated first
interaction, a well-designed bot provides the user with access to
information about its privacy policy and terms of use.

Tip

If your bot collects personal data from the user, it\'s important to
convey that and to describe what will be done with the data.

Design and control conversation flow
====================================

In a traditional application, the user interface (UI) is a series of
screens. A single app or website can use one or more screens as needed
to exchange information with the user. Most applications start with a
main screen where users initially land and provide navigation that leads
to other screens for various functions like starting a new order,
browsing products, or looking for help.

Like apps and websites, bots have a UI, but it is made up
of **dialogs**, rather than screens. Dialogs enable the bot developer to
logically separate various areas of bot functionality and guide
conversational flow. For example, you may design one dialog to contain
the logic that helps the user browse for products and a separate dialog
to contain the logic that helps the user create a new order.

Dialogs may or may not have graphical interfaces. They may contain
buttons, text, and other elements, or be entirely speech-based. Dialogs
also contain actions to perform tasks such as invoking other dialogs or
processing user input.

**Using dialogs to manage conversation flow**
---------------------------------------------

This diagram shows the screen flow of a traditional application compared
to the dialog flow of a bot.

![bot](media/image3.png){width="8.327777777777778in"
height="3.672222222222222in"}

In a traditional application, everything begins with the **main
screen**. The **main screen** invokes the **new order screen**.
The **new order screen** remains in control until it either closes or
invokes other screens. If the **new order screen** closes, the user is
returned to the **main screen**.

In a bot, everything begins with the **root dialog**. The **root
dialog** invokes the **new order dialog**. At that point, the **new
order dialog** takes control of the conversation and remains in control
until it either closes or invokes other dialogs. If the **new order
dialog** closes, control of the conversation is returned back to
the **root dialog**.

For a detailed walkthrough of managing conversation flow using dialogs
and the Bot Builder SDK, see:

-   [Manage conversation flow with dialogs
    > (.NET)](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-manage-conversation-flow)

-   [Manage conversation flow with dialogs
    > (Node.js)](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-manage-conversation-flow)

**Dialog stack**
----------------

When one dialog invokes another, the Bot Builder adds the new dialog to
the top of the dialog stack. The dialog that is on top of the stack is
in control of the conversation. Every new message sent by the user will
be subject to processing by that dialog until it either closes or
redirects to another dialog. When a dialog closes, it\'s removed from
the stack, and the previous dialog in the stack assumes control of the
conversation.

Important

Understanding the concept of how the dialog stack is constructed and
deconstructed by the Bot Builder as dialogs invoke one another, close,
and so on is critical to being able to effectively design the
conversation flow of a bot.

**Dialogs, stacks and humans**
------------------------------

It may be tempting to assume that users will navigate across dialogs,
creating a dialog stack, and at some point will navigate back in the
direction they came from, unstacking the dialogs one by one in a neat
and orderly way. For example, the user will start at root dialog, invoke
the new order dialog from there, and then invoke the product search
dialog. Then the user will select a product and confirm, exiting the
product search dialog, complete the order, exiting the new order dialog,
and arrive back at the root dialog.

Although it would be great if users always traveled such a linear,
logical path, it seldom occurs. Humans do not communicate in \"stacks.\"
They tend to frequently change their minds. Consider the following
example:

![bot](media/image4.png){width="6.6722222222222225in"
height="2.879166666666667in"}

While your bot may have logically constructed a stack of dialogs, the
user may decide to do something entirely different or ask a question
that may be unrelated to the current topic. In the example, the user
asks a question rather than providing the yes/no response that the
dialog expects. How should your dialog respond?

-   Insist that the user answer the question first.

-   Disregard everything that the user had done previously, reset the
    > whole dialog stack, and start from the beginning by attempting to
    > answer the user\'s question.

-   Attempt to answer the user\'s question and then return to that
    > yes/no question and try to resume from there.

There is no *right* answer to this question, as the best solution will
depend upon the specifics of your scenario and how the user would
reasonably expect the bot to respond.

Design bot navigation
=====================

Users can navigate websites using breadcrumbs, apps using menus, and web
browsers using buttons like **forward** and **back**. However, none of
these well-established navigation techniques entirely address navigation
requirements within a bot. As
discussed [previously](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-conversation-flow#dialogs-stacks-and-humans),
users often interact with bots in a non-linear fashion, making it
challenging to design bot navigation that consistently delivers a great
user experience. Consider the following dilemmas:

-   How do you ensure that a user doesn\'t get lost in a conversation
    > with a bot?

-   Can a user navigate \"back\" in a conversation with a bot?

-   How does a user navigate to the \"main menu\" during a conversation
    > with a bot?

-   How does a user \"cancel\" an operation during a conversation with a
    > bot?

The specifics of your bot\'s navigation design will depend largely upon
the features and functionality that your bot supports. However,
regardless of the type of bot you\'re developing, you\'ll want to avoid
the common pitfalls of poorly designed conversational interfaces. This
article describes these pitfalls in terms of five personalities: the
\"stubborn bot\", the \"clueless bot\", the \"mysterious bot\", the
\"captain obvious bot\", and the \"bot that can\'t forget.\"

**The \"stubborn bot\"**
------------------------

The stubborn bot insists upon maintaining the current course of
conversation, even when the user attempts to steer things in a different
direction. Consider the following scenario:

![bot](media/image5.png){width="7.06875in" height="5.051388888888889in"}

Users often change their minds. They can decide to cancel. Sometimes
they want to start over altogether.

Tip

**Do**: Design your bot to consider that a user might attempt to change
the course of the conversation at any time.

**Don\'t**: Design your bot to ignore user input and keep repeating the
same question in an endless loop.

There are many methods of avoiding this pitfall, but perhaps the easiest
way to prevent a bot from asking the same question endlessly is to
simply specify a maximum number of retry attempts for each question. If
designed in this manner, the bot is not doing anything \"smart\" to
understand the user\'s input and respond appropriately but will at least
avoid asking the same question in an endless loop.

**The \"clueless bot\"**
------------------------

The clueless bot responds in a nonsensical manner when it doesn\'t
understand a user\'s attempt to access certain functionality. A user may
try common keyword commands like \"help\" or \"cancel\" with reasonable
expectations that the bot will respond appropriately.

Consider the following scenario:

![bot](media/image6.png){width="7.120833333333334in"
height="2.6381944444444443in"}

Although you may be tempted to design every dialog within your bot to
listen for, and respond appropriately to, certain keywords, this
approach is not recommended.

Tip

**Do**: Implement global message handlers
(using [.NET](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-global-handlers) or [Node.js](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-dialog-actions))
that will examine user input for the keywords that you specify (ex:
\"help\", \"cancel\", \"start over\", etc.) and respond appropriately.

**Don\'t**: Design every dialog to examine user input for a list of
keywords.

By defining the logic in **global message handlers**, you\'re making it
accessible to all dialogs. Using this approach, individual dialogs and
prompts can be made to safely ignore the keywords, if necessary.

**The \"mysterious bot\"**
--------------------------

The mysterious bot fails to immediately acknowledge the user\'s input in
any way. Consider the following scenario:

![bot](media/image7.png){width="7.06875in"
height="3.2583333333333333in"}

In some cases, this situation might be an indication that the bot is
having an outage. However, it could just be that the bot is busy
processing the user\'s input and hasn\'t yet finished compiling its
response.

Tip

**Do**: Design your bot to immediately acknowledge user input, even in
cases where the bot may take some time to compile its response.

**Don\'t**: Design your bot to postpone acknowledgement of user input
until the bot finishes compiling its response.

By immediately acknowledging the user\'s input, you eliminate any
potential for confusion as to the state of the bot.

**The \"captain obvious bot\"**
-------------------------------

The captain obvious bot provides unsolicited information that is
completely obvious and therefore useless to the user. Consider the
following scenario:

Tip

**Do**: Design your bot to provide information that will be useful to
the user.

**Don\'t**: Design your bot to provide unsolicited information that is
unlikely to be useful to the user.

By designing your bot to provide useful information, you\'re increasing
the odds that the user will engage with your bot.

**The \"bot that can\'t forget\"**
----------------------------------

The bot that can\'t forget inappropriately integrates information from
past conversations into the current conversation.

Consider the following scenario:

![bot](media/image8.png){width="7.051388888888889in"
height="3.6381944444444443in"}

Tip

**Do**: Design your bot to maintain the current topic of conversation,
unless/until the user expresses a desire to revisit a prior topic.

**Don\'t**: Design your bot to interject information from past
conversations when it is not relevant to the current conversation.

By maintaining the current topic of conversation, you reduce the
potential for confusion and frustration and increase the odds that the
user will continue to engage with your bot.

Design the user experience
==========================

Bots typically use some combination of **rich user controls**, **text
and natural language**, and **speech** to exchange information with
users.

**Rich user controls**
----------------------

**Rich user controls** are common UI controls such as buttons, images,
carousels, and menus that the bot presents to the user and the user
engages with to communicate choice and intent. A bot can use a
collection of UI controls to mimic an app or can even run embedded
within an app. When a bot is embedded within an app or website, it can
represent virtually any UI control by leveraging the capabilities of the
app that is hosting it.

For decades, application and website developers have relied on UI
controls to enable users to interact with their applications. These same
UI controls can also be very effective in bots. For example, buttons are
a great way to present the user with a simple choice. Allowing the user
to communicate \"Hotels\" by clicking a button labeled **Hotels** is
easier and quicker than forcing the user to type \"Hotels.\" This
especially holds true on mobile devices, where clicking is greatly
preferred over typing.

When designing your bot, do not automatically dismiss common UI elements
as not being \"smart enough.\" As
discussed [previously](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-principles#designing-a-bot),
your bot should be designed to solve the user\'s problem in the
best/quickest/easiest manner possible. Avoid the temptation to start by
incorporating natural language understanding, as it is often unnecessary
and just introduces unjustified complexity.

Tip

Start by using the minimum UI controls that enable the bot to solve the
user\'s problem, and add other elements later if those controls are no
longer sufficient.

**Text and natural language understanding**
-------------------------------------------

A bot can accept **text** input from users and attempt to parse that
input using regular expression matching or **natural language
understanding** APIs such as [LUIS](https://www.luis.ai/). There are
many different types of text input that a bot might expect from a user.
Depending on the type of input that the user provides, natural language
understanding may or may not be a good solution.

In some cases, a user may be **answering a very specific question**. For
example, if the bot asks, \"What is your name?\", the user may answer
with text that specifies only the name, \"John\", or with a sentence,
\"My name is John\". Asking specific questions reduces the scope of
potential responses that the bot might reasonably receive, which
decreases the complexity of the logic necessary to parse and understand
the response. For example, consider the following broad, open-ended
question: \"How are you feeling?\". Understanding the many possible
permutations of potential answers to such a question is a very complex
task. In contrast, specific questions such as \"Are you feeling pain?
yes/no\" and \"Where are you feeling pain? chest/head/arm/leg\" would
likely prompt more specific answers that a bot can parse and understand
without needing to implement natural language understanding.

Tip

Whenever possible, ask specific questions that will not require natural
language understanding capabilities to parse the response.

In other cases, a user may be **typing a specific command**. For
example, a DevOps bot that enables developers to manage virtual machines
could be designed to accept specific commands such as \"/STOP VM XYZ\"
or \"/START VM XYZ.\" Designing a bot to accept specific commands like
this makes for a good user experience, as the syntax is easy to learn
and the expected outcome of each command is clear. Additionally, the bot
will not require natural language understanding capabilities, since the
user\'s input can be easily parsed using regular expressions.

Tip

Designing a bot to require specific commands from the user can often
provide a good user experience while also eliminating the need for
natural language understanding capability.

In the case of a *knowledge base* bot or *questions and answers* bot, a
user may be **asking general questions**. For example, imagine a bot
that can answer questions based on the contents of thousands of
documents. QnA Maker and [Azure
Search](https://azure.microsoft.com/en-us/services/search/) are both
technologies which are designed specifically for this type of scenario.
For more information, see [Design knowledge
bots](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-knowledge-base).

Tip

If you are designing a bot that will answer questions based on
structured or unstructured data from databases, web pages, or documents,
consider using technologies that are designed specifically to address
this scenario rather than attempting to solve the problem with natural
language understanding.

In other scenarios, a user may be **typing simple requests based on
natural language**. For example, a user may type \"I want a pepperoni
pizza\" or \"Are there any vegetarian restaurants within 3 miles from my
house open now?\". Natural language understanding APIs such
as [LUIS.ai](https://www.luis.ai/)are a great fit for scenarios like
this. Using the APIs, your bot can extract the key components of the
user\'s text to identify the user\'s intent. When implementing natural
language understanding capabilities in your bot, set realistic
expectations for the level of detail that users are likely to provide in
their input.

![how users talk](media/image9.png){width="10.120833333333334in"
height="2.6381944444444443in"}

Tip

When building natural language models, do not assume that users will
provide all the required information in their initial query. Design your
bot to specifically request the information it requires, guiding the
user to provide that information by asking a series of questions, if
necessary.

**Speech**
----------

A bot can use **speech** input and/or output to communicate with users.
In cases where a bot is designed to support devices that have no
keyboard or monitor, speech is the only means of communicating with the
user.

**Choosing between rich user controls, text and natural language, and speech**
------------------------------------------------------------------------------

Just like people communicate with each other using a combination of
gestures, voice, and symbols, bots can communicate with users using a
combination of rich user controls, text (sometimes including natural
language), and speech. You do not need to choose one over another. For
example, imagine a \"cooking bot\" that helps users with recipes. The
bot may provide instructions by playing a video or displaying a series
of pictures to explain what needs to be done. Some users may prefer to
flip pages of the recipe or ask the bot questions using speech while
they are assembling a recipe. Others may prefer to touch the screen of a
device instead of interacting with the bot via speech. When designing
your bot, incorporate the UX elements that support the ways in which
users will likely prefer to interact with your bot, given the specific
use cases that it is intended support.

Create task automation bots
===========================

A task automation bot enables the user to complete a specific task or
set of tasks without any assistance from a human. This type of bot often
closely resembles a typical app or website, communicating with the user
primarily via rich user controls and text. It may have natural language
understanding capabilities to enrich conversations with users.

**Example use case: password-reset**
------------------------------------

To better understand the nature of a task bot, consider an example use
case: password-reset. The Contoso company receives several help desk
calls each day from employees who need to reset their passwords. Contoso
wants to automate the simple, repeatable task of resetting a employee\'s
password so that help desk agents can devote their time to addressing
more complex issues.

John, an experienced developer from Contoso, decides to create a bot to
automate the password-reset task. He begins by writing a design
specification for the bot, just as he would do if he were creating a new
app or website.

### **Navigation model**

The specification defines the navigation model:

![Dialog Structure](media/image10.png){width="8.034722222222221in"
height="6.879166666666666in"}

The user begins at the RootDialog. When they request a password reset,
they\
will be directed to the ResetPasswordDialog. With
the ResetPasswordDialog, the bot will prompt the user for two pieces of
information: phone number and birth date.

Important

The bot design described in this article is intended for example
purposes only. In real-world scenarios, a password-reset bot would
likely implement a more robust identity verification process.

### **Dialogs**

Next, the specification describes the appearance and functionality of
each dialog.

#### **Root dialog**

The root dialog provides the user with two options:

1.  **Change Password** is for scenarios where the user knows their
    > current password and simply wants to change it.

2.  **Reset Password** is for scenarios where the user has forgotten or
    > misplaced their password and needs to generate a new one.

Note

For simplicity, this article describes only the **reset password** flow.

The specification describes the root dialog as shown in the following
screenshot.

![Dialog Structure](media/image11.png){width="11.91388888888889in"
height="13.206944444444444in"}

#### **ResetPassword dialog**

When the user chooses **Reset Password** from the root dialog,
the ResetPassword dialog is invoked. The ResetPassword dialog then
invokes two other dialogs. First, it invokes
the PromptStringRegex dialog to collect the user\'s phone number. Then
it invokes the PromptDatedialog to collect the user\'s date of birth.

Note

In this example, John chose to implement the logic for collecting the
user\'s phone number and date of birth by using two separate dialogs.
The approach not only simplifies the code required for each dialog, but
also increases the odds of these dialogs being usable by other scenarios
in the future.

The specification describes the ResetPassword dialog.

![Dialog Structure](media/image12.png){width="12.034722222222221in"
height="10.620833333333334in"}

#### **PromptStringRegex dialog**

The PromptStringRegex dialog prompts the user to enter their phone
number, and verifies that the phone number that the user provides
matches the expected format. It also accounts for the scenario where the
user repeatedly provides invalid input. The spec describes
the PromptStringRegex dialog.

![Dialog Structure](media/image13.png){width="11.810416666666667in"
height="14.810416666666667in"}

### **Prototype**

Finally, the spec provides an example of a user communicating with the
bot to successfully complete the password-reset task.

![Dialog Structure](media/image14.png){width="6.586111111111111in"
height="11.48263888888889in"}

**Bot, app, or website?**
-------------------------

You may be wondering, if a task automation bot closely resembles an app
or website, why not just build an app or website instead? Depending on
your particular scenario, building an app or website instead of a bot
may be an entirely reasonable choice. You may even choose to embed your
bot into an app, by using the [Bot Framework Direct Line
API](https://docs.botframework.com/en-us/restapi/directline3/#navtitle) or [Web
Chat control](https://github.com/Microsoft/BotFramework-WebChat).
Implementing your bot within the context of an app provides the best of
both worlds: a rich app experience and a conversational experience, all
in one place.

In many cases, however, building an app or website can be significantly
more complex and more expensive than building a bot. An app or website
often needs to support multiple clients and platforms, packaging and
deploying can be tedious and time-consuming processes, and the user
experience of having to download and install an app is not necessarily
ideal. For these reasons, a bot may often provide a much simpler way of
solving the problem at hand.

Additionally, bots provide the freedom to easily expand and extend. For
example, a developer may choose to add natural language and speech
capabilities to the password-reset bot so that it can be accessed via
audio call, or she may add support for text messages. The company may
setup kiosks throughout the building and embed the password-reset bot
into that experience.

**Sample code**
---------------

For a complete sample that shows how to implement simple task automation
using the Bot Builder SDK for .NET, see the [Simple Task Automation
sample](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/capability-SimpleTaskAutomation) in
GitHub.

For a complete sample that shows how to implement simple task automation
using the Bot Builder SDK for Node.js, see the [Simple Task Automation
sample](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/capability-SimpleTaskAutomation) in
GitHub.

Design knowledge bots
=====================

A knowledge bot can be designed to provide information about virtually
any topic. For example, one knowledge bot might answer questions about
events such as, \"What bot events are there at this conference?\",
\"When is the next Reggae show?\", or \"Who is Tame Impala?\" Another
might answer IT-related questions such as \"How do I update my operating
system?\" or \"Where do I go to reset my password?\" Yet another might
answer questions about contacts such as \"Who is John Doe?\" or \"What
is Jane Doe\'s email address?\"

Regardless of the use case for which a knowledge bot is designed, its
basic objective is always the same: find and return the information that
the user has requested by leveraging a body of data, such as relational
data in a SQL database, JSON data in a non-relational store, or PDFs in
a document store.

**Search**
----------

Search functionality can be a valuable tool within a bot.

First, \"fuzzy search\" enables a bot to return information that\'s
likely to be relevant to the user\'s question, without requiring that
the user provide precise input. For example, if the user asks a music
knowledge bot for information about \"impala\" (instead of \"Tame
Impala\"), the bot can respond with information that\'s most likely to
be relevant to that input.

![Dialog Structure](media/image15.png){width="4.465277777777778in"
height="2.9138888888888888in"}

Search scores indicate the level of confidence for the results of a
specific search, enabling a bot to order its results accordingly, or
even tailor its communication based upon confidence level. For example,
if confidence level is high, the bot may respond with \"Here is the
event that best matches your search:\".

![Dialog Structure](media/image16.png){width="5.293055555555555in"
height="2.827777777777778in"}

If confidence level is low, the bot may respond with \"Hmm\... were you
looking for any of these events?\"

![Dialog Structure](media/image17.png){width="4.965277777777778in"
height="2.827777777777778in"}

### **Using Search to Guide a Conversation**

If your motivation for building a bot is to enable basic search engine
functionality, then you may not need a bot at all. What does a
conversational interface offer that users can\'t get from a typical
search engine in a web browser?

Knowledge bots are generally most effective when they are designed to
guide the conversation. A conversation is composed of a back-and-forth
exchange between user and bot, which presents the bot with opportunities
to ask clarifying questions, present options, and validate outcomes in a
way that a basic search is incapable of doing. For example, the
following bot guides a user through a conversation that facets and
filters a dataset until it locates the information that the user is
seeking.

![Dialog Structure](media/image18.png){width="4.051388888888889in"
height="1.5in"}

![Dialog Structure](media/image19.png){width="4.017361111111111in"
height="1.4826388888888888in"}

![Dialog Structure](media/image20.png){width="3.9652777777777777in"
height="1.4652777777777777in"}

![Dialog Structure](media/image21.png){width="8.361805555555556in"
height="3.56875in"}

By processing the user\'s input in each step and presenting the relevant
options, the bot guides the user to the information that they\'re
seeking. Once the bot delivers that information, it can even provide
guidance about more efficient ways to find similar information in the
future.

![Dialog Structure](media/image22.png){width="7.7756944444444445in"
height="1.051388888888889in"}

### **Azure Search**

By using [Azure
Search](https://azure.microsoft.com/en-us/services/search/), you can
create an efficient search index that a bot can easily search, facet,
and filter. Consider a search index that is created using the Azure
portal.

![Dialog Structure](media/image23.png){width="14.0in"
height="8.06875in"}

You want to be able to access all properties of the data store, so you
set each property as \"retrievable.\" You want to be able to find
musicians by name, so you set the **Name** property as \"searchable.\"
Finally, you want to be able to facet filter over musicians\' eras, so
you mark the **Eras**property as both \"facetable\" and \"filterable.\"

Faceting determines the values that exist in the data store for a given
property, along with the magnitude of each value. For example, this
screenshot shows that there are 5 distinct eras in the data store:

![Dialog Structure](media/image24.png){width="7.138194444444444in"
height="2.5347222222222223in"}

Filtering, in turn, selects only the specified instances of a certain
property. For example, you could filter the result set above to contain
only items where **Era** is equal to \"Romantic.\"

Note

See [a sample bot](https://github.com/ryanvolum/AzureSearchBot) for a
complete example of a knowledge bot that is created using Azure Document
DB, Azure Search, and the Microsoft Bot Framework.

For the sake of simplicity, the example above shows a search index that
is created using the Azure portal. Indices can also be created
programatically.

**QnA Maker**
-------------

Some knowledge bots may simply aim to answer frequently asked questions
(FAQs). QnA Makeris a powerful tool that\'s designed specifically for
this use case. QnA Maker has the built-in ability to scrape questions
and answers from an existing FAQ site. It also allows you to manually
configure your own custom list of questions and answers. QnA Maker has
natural language processing (NLP) abilities, enabling it to even provide
answers to questions that are worded slightly differently than expected.
However, it does not have semantic language understanding abilities. It
cannot determine that a puppy is a type of dog, for example.

Using the QnA Maker web interface, you can configure a knowledge base
with three question and answer pairs:

![Dialog Structure](media/image25.png){width="6.534722222222222in"
height="3.56875in"}

Then, you can test it by asking a series of questions:

![Dialog Structure](media/image26.png){width="11.56875in"
height="4.793055555555555in"}

The bot correctly answers the questions that directly map to the ones
that were configured in the knowledge base. However, it incorrectly
responds to the question \"can I bring my rum?\". Because this question
is most similar in structure to the question \"can I bring my dog?\" and
because QnA Maker does not inherently understand the meaning of words,
i.e., it does not know that \"rum\" is a type of liquor, it answers
\"Dogs are not allowed.\"

Tip

Create your QnA pairs and then test and re-train your bot by using the
menu on the left side of the conversation to select an alternative
answer for each incorrect answer that is given.

**LUIS**
--------

Some knowledge bots require natural language processing (NLP)
capabilities so that they can analyze a user\'s messages to determine
the user\'s intent. Language Understanding (LUIS) provides a fast and
effective means of adding NLP capabilities to bots. LUIS enables you to
use existing, pre-built models from Bing and Cortana whenever they meet
your needs. It also allows you to create specialized models of your own.

When working with huge datasets, it\'s not necessarily feasible to train
an NLP model with every variation of an entity. In a music playing bot,
for example, a user might message \"Play Reggae\", \"Play Bob Marley\",
or \"Play One Love\". Although a bot could map each of these messages to
the intent \"playMusic\", without being trained with every artist, genre
and song name, an NLP model would not be able to identify whether the
entity is a genre, artist or song. By using an NLP model to identify the
generic entity of type \"music\", the bot could search its data store
for that entity, and proceed from there.

**Combining Search, QnA Maker, and/or LUIS**
--------------------------------------------

Search, QnA Maker and LUIS are each powerful tools in their own right,
but they can also be combined to build knowledge bots that possess more
than one of those capabilities.

### **LUIS and Search**

In the music festival bot example [covered
earlier](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-knowledge-base#search),
the bot guides the conversation by showing buttons that represent the
lineup. However, this bot could also incorporate natural language
understanding by using LUIS to determine intent and entities within
questions such as \"what kind of music does Romit Girdhar play?\". Then
the bot could search against an Azure Search index using musician name.

It would not be feasible to train the model with every possible musician
name since there are so many potential values, but you could provide
enough representative examples for LUIS to properly identify the entity
at hand. For example, consider that you train your model by providing
examples of musicians:

![Dialog Structure](media/image27.png){width="6.56875in"
height="1.8104166666666666in"} ![Dialog
Structure](media/image28.png){width="6.7756944444444445in"
height="1.8104166666666666in"}

When you test this model with new utterances like, \"what kind of music
do the beatles play?\", LUIS successfully determines the intent
\"answerGenre\" and the identifies entity \"the beatles.\" However, if
you submit a longer question such as \"what kind of music does the devil
makes three play?\", LUIS identifies \"the devil\" as the entity.

![Dialog Structure](media/image29.png){width="3.5861111111111112in"
height="2.345138888888889in"}

By training the model with example entities that are representative of
the underlying dataset, you can increase the accuracy of your bot\'s
language understanding.

Tip

In general, it is better for the model to err by identifying excess
words in its entity recognition, e.g., identify \"John Smith please\"
from the utterance \"Call John Smith please\", rather than identify too
few words, e.g., identify \"John\" from the utterance \"Call John Smith
please\". The search index will ignore irrelevant words such as
\"please\" in the phrase \"John Smith please\".

### **LUIS and QnA Maker**

Some knowledge bots might use QnA Maker to answer basic questions in
combination with LUIS to determine intents, extract entities and invoke
more elaborate dialogs. For example, consider a simple IT Help Desk bot.
This bot may use QnA Maker to answer basic questions about Windows or
Outlook, but it might also need to facilitate scenarios like password
reset, which require intent recognition and back-and-forth communication
between user and bot. There are a few ways that a bot may implement a
hybrid of LUIS and QnA Maker:

1.  Call both QnA Maker and LUIS at the same time, and respond to the
    > user by using information from the first one that returns a score
    > of a specific threshold.

2.  Call LUIS first, and if no intent meets a specific threshold score,
    > i.e., \"None\" intent is triggered, then call QnA Maker.
    > Alternatively, create a LUIS intent for QnA Maker, feeding your
    > LUIS model with example QnA questions that map to \"QnAIntent.\"

3.  Call QnA Maker first, and if no answer meets a specific threshold
    > score, then call LUIS.

The Bot Builder SDK for Node.js and the Bot Builder SDK for C\# provide
built-in support for LUIS and QnA Maker. This enables you to trigger
dialogs or automatically answer questions using LUIS and/or QnA Maker
without having to implement custom calls to either tool. For example, if
LUIS has enabled you to determine intent, you could trigger
a [BasicQnAMakerDialog](https://docs.botframework.com/en-us/azure-bot-service/templates/qnamaker/#navtitle) to
initiate the process of answering the user\'s question.

Tip

When implementing a combination of LUIS, QnA Maker, and/or Azure Search,
test inputs with each of the tools to determine the threshold score for
each of your models. LUIS, QnA Maker, and Azure Search each generate
scores by using a different scoring criteria, so the scores generated
across these tools are not directly comparable. Additionally, LUIS and
QnA Maker normalize scores. A certain score may be considered \'good\'
in one LUIS model but not so in another model.

**Sample code**
---------------

-   For a sample that shows how to create a basic knowledge bot using
    > the Bot Builder SDK for .NET, see the [Knowledge Bot
    > sample](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/sample-KnowledgeBot) in
    > GitHub.

-   For a sample that shows how to create more complex knowledge bots
    > using the Bot Builder SDK for .NET, see the [Search-powered Bots
    > sample](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/demo-Search) in
    > GitHub.

Integrate your bot with a web browser
=====================================

Some scenarios require more than just a bot to fulfill a requirement. A
bot may need to send the user to a web browser to complete a task and
then resume the conversation with the user after the task has been
completed.

**Authentication and authorization**
------------------------------------

If a bot wants the ability to read the user\'s calendar in Office 365,
or perhaps even create appointments on behalf of that user, the user
must first authenticate with Microsoft Azure Active Directory and
authorize the bot to access the user\'s calendar data. The bot will
redirect the user to a web browser to complete the authentication and
authorization tasks, and then will subsequently resume the conversation
with the user.

**Security and compliance**
---------------------------

Security and compliance requirements often restrict the type of
information that a bot can exchange with a user. In some cases, it may
be necessary for the user to send/receive data outside of the current
conversation. For example, if a user wants to execute a payment using a
third-party payment provider, a credit card number should not be
specified within the context of the conversation. Instead, the bot will
direct the user to a web browser to complete the payment process, and
then will subsequently resume the conversation with the user.

This article explores the process of facilitating a user\'s transition
from bot to web browser, and back again.

Note

Transitioning from chat to web browser and back is not ideal, as
switching between applications can easily confuse a user. To provide a
better experience, many channels offer built-in HTML windows that a bot
can use to present applications would otherwise appear in a web browser.
This technique allows the user to remain within the conversation while
still accessing external resources. This approach is conceptually
similar to mobile applications managing authorization flows using OAuth
within embedded web views.

**Bot to web browser, and back again**
--------------------------------------

This diagram shows the high-level flow for integration between bot and
web browser.

![Bot to web
interaction](media/image30.png){width="12.154861111111112in"
height="5.361805555555556in"}

Consider each step of the flow:

1.  The bot generates and displays a hyperlink that will redirect the
    > user to a website. The hyperlink typically includes data via
    > querystring parameters on the target URL that specify information
    > about the context of the current conversation, such as
    > conversation ID, channel ID, and user ID in the channel.

2.  The user clicks the hyperlink and is redirected to the target URL
    > within a web browser.

3.  The bot enters a state awaiting communication from the website to
    > indicate that the website flow is complete.

> Tip
>
> Design this flow so that the bot will not permanently remain in the
> \'waiting\' state if the user never completes the website flow. In
> other words, if the user abandons the web browser and starts
> communicating with the bot again, the bot should acknowledge,
> not [ignore](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-navigation#the-mysterious-bot) that
> input.

4.  The user completes the necessary task(s) via the web browser. This
    > could be an OAuth flow or any sequence of events required by the
    > scenario at hand.

5.  When the user completes the website flow, the website generates a
    > \'[magic
    > number](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-integrate-browser#verify-identity)\'
    > and instructs the user to copy the value and paste it back into
    > the conversation with the bot.

6.  The website [signals to the
    > bot](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-integrate-browser#website-signal-to-bot) that
    > the user has completed the website flow. It communicates the
    > \'magic number\' to the bot and provides any other relevant data.
    > For example, in the case of an OAuth flow, the website would
    > provide an access token to the bot.

7.  The user returns to the bot and pastes the \'magic number\' into the
    > chat. The bot validates that \'magic number\' provided by the user
    > matches the expected value, verifying that the current user is the
    > same user who previously clicked the hyperlink to initiate the
    > website flow.

### **Verifying user identity using the \'magic number\'**

The generation of a \'magic number\' during the bot-to-website flow
([step
5](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-integrate-browser#generate-magic-number) above)
enables the bot to subsequently verify that the user who initiated the
website flow is indeed the user for whom it was intended. For example,
if a bot is conducting a group chat with multiple users, any one of them
could have clicked the hyperlink to initiate the website flow. Without
the \'magic number\' validation process, the bot has no way of knowing
which user completed the flow. One user could authenticate and inject
access tokens in another user\'s session.

Warning

This isn\'t just a risk within group chats. Without the \'magic number\'
validation process, anyone who obtains the hyperlink to launch the
website flow can spoof a user\'s identity.

The magic number should be a random number generated using a strong
cryptography library. For an example of the generation process in C\#,
see [this
code](https://github.com/MicrosoftDX/AuthBot/blob/master/AuthBot/Controllers/OAuthCallbackController.cs#L138) within
the AuthBot library. AuthBot enables bots that are built in Microsoft
Bot Framework to implement the bot-to-website flow to authenticate a
user in a website and then to subsequently use the access token that was
generated from the authentication process. Since AuthBot does not make
any assumptions about the channel\'s capabilities, such flows should
function well with most channels.

Note

The need for the \'magic number\' validation process should be
deprecated as channels build their own embedded web views.

### **How does the website \'signal\' the bot?**

When the bot [generates the
hyperlink](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-integrate-browser#generate-hyperlink) that
the user will click to initiate the website flow, it includes
information via querystring parameters in the target URL about the
context of the current conversation, such as conversation ID, channel
ID, and user ID in the channel. The website can subsequently use this
information to read and write state variables for that user or
conversation using the Bot Builder SDK or REST APIs. See [step
6](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-integrate-browser#signal-to-bot) above
for an example of how the website \'signals\' to the bot that the
website flow is complete.

**Sample code**
---------------

As described in this article, the AuthBot library enables OAuth flows to
be bound to bots that are built using .NET in the Microsoft Bot
Framework. The BotAuth library enables OAuth flows to be bound to bots
that are built using Node.js in the Microsoft Bot Framework.

Transition conversations from bot to human
==========================================

Regardless of how much artificial intelligence a bot possesses, there
may still be times when it needs to hand off the conversation to a human
being. The bot should recognize when it needs to hand off and provide
the user with a clear, smooth transition.

**Scenarios that require human involvement**
--------------------------------------------

A wide variety of scenarios may require that a bot transition control of
the conversation to a human. A few of those scenarios
are *triage*, *escalation*, and *supervision*.

### **Triage**

A typical help desk call starts with some very basic questions that can
easily be answered by a bot. As the first responder to inbound requests
from users, a bot could collect the user\'s name, address, and
description of the problem and then transition control of the
conversation to an agent. Using a bot to triage incoming requests allows
agents to devote their time to solving the problem instead of collecting
information.

### **Escalation**

In the help desk scenario, a bot may be able to answer basic questions
and resolve simple issues in addition to collecting information. For
example, bots are commonly used to reset a user\'s password. However, if
a conversation indicates that a user\'s issue is complex enough to
require human involvement, the bot will need to escalate the issue to a
human agent. To implement this type of scenario, a bot must be capable
of differentiating between issues it can resolve independently and
issues that must be escalated to a human. There are many ways that a bot
may determine that it needs to transfer control of the conversation to a
human, including:

#### **User-driven menus**

Perhaps the simplest way for a bot to handle this dilemma is to present
the user with a menu of options. Tasks that the bot can handle
independently appear in the menu above a link labeled \"Chat with an
agent.\" This type of implementation requires no advanced machine
learning or natural language understanding. The bot simply transfers
control of the conversation to a human agent when the user selects the
\"Chat with an agent\" option.

#### **Scenario-driven**

The bot may decide whether or not to transfer control based upon whether
or not it determines that it is capable of handling the scenario at
hand. The bot collects some information about the user\'s request and
then queries its internal list of capabilities to determine if it is
capable of addressing that request. If the bot determines that it is
capable of addressing the request, it does so. However, if the bot
determines that the request is beyond the scope of issues it can
resolve, it transfers control of the conversation to a human agent.

#### **Natural language**

Natural language understanding and sentiment analysis help the bot
decide when to transfer control of the conversation to a human agent.
This is particularly valuable when attempting to determine when the user
is frustrated or wants to speak with a human agent.

The bot analyzes the content of the user\'s messages by using the [Text
Analytics
API](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api) to
infer sentiment or by using the [LUIS API](https://www.luis.ai/).

Tip

Natural language understanding may not always be the best method for
determining when a bot should transfer conversation control to a human
being. Bots, like humans, don\'t always guess correctly, and invalid
responses will frustrate the user. If the user selects from a menu of
valid choices, however, the bot will always respond appropriately to
that input.

### **Supervision**

In some cases, the human agent will want to monitor the conversation
instead of taking control.

For example, consider a help desk scenario where a bot is communicating
with a user to diagnose computer problems. A machine learning model
helps the bot determine the most likely cause of the issue. Before
advising the user to take a specific course of action, the bot can
privately confirm the diagnosis and remedy with the human agent and
request authorization to proceed. The agent clicks a button, the bot
presents the solution to the user, and the problem is solved. The bot is
still performing the majority of the work, but the agent retains control
the final decision.

**Transitioning control of the conversation**
---------------------------------------------

When a bot decides to transfer control of a conversation to a human, it
can inform the user that she is being transferred and put the
conversation into a \'waiting\' state until it confirms that an agent is
available.

When the bot is waiting for a human, it may automatically answer all
incoming user messages with a default response such as \"waiting in
queue\". Furthermore, you could have the bot remove the conversation
from the \'waiting\' state if the user sent certain messages such as
\"never mind\" or \"cancel\".

You specify how agents will be assigned to waiting users when you design
your bot. For example, the bot may implement a simple queue system:
first in, first out. More complex logic would assign users to agents
based upon geography, language, or some other factor. The bot could also
present some type of UI to the agent that they can use to select a user.
When an agent becomes available, she connects to the bot and joins the
conversation.

Important

Even after an agent is engaged, the bot remains the behind-the-scenes
facilitator of the conversation. The user and agent never communicate
directly with each other; they just route messages through the bot.

**Routing messages between user and agent**
-------------------------------------------

After the agent connects to the bot, the bot begins to route messages
between user and agent. Although it may appear to the user and the agent
that they are chatting directly with each other, they are exchanging
messages via the bot. The bot receives messages from the user and sends
those messages to the agent. Likewise, it receives messages from the
agent and sends those messages to the user.

Note

In more advanced scenarios, the bot can assume responsibility beyond
merely routing messages between user and agent. For example, the bot may
decide which response is appropriate and simply ask the agent for
confirmation to proceed.

**Sample code**
---------------

For a complete sample that shows how to hand off conversations from bot
to human using the Bot Builder SDK for Node.js, see the [Bot-HandOff
sample](https://github.com/palindromed/Bot-HandOff) in GitHub.

Embed a bot in an app
=====================

Although bots most commonly exist outside of apps, they can also be
integrated with apps. For example, you could embed a [knowledge
bot](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-knowledge-base) within
an app to help users find information that might otherwise be
challenging to locate within complex app structures. You could embed a
bot within a help desk app to act as the first responder to incoming
user requests. The bot could independently resolve simple issues
and [hand
off](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-handoff-human) more
complex issues to a human agent.

**Integrating bot with app**
----------------------------

The way to integrate a bot with an app varies depending on the type of
app.

### **Native mobile app**

An app that is created in native code can communicate with the Bot
Framework by using the [Direct Line
API](https://docs.botframework.com/en-us/restapi/directline3/#navtitle),
either via REST or websockets.

### **Web-based mobile app**

A mobile app that is built by using web language and frameworks such
as [Cordova](https://cordova.apache.org/) may communicate with the Bot
Framework by using the same components that a [bot embedded within a
website](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-embed-web-site) would
use, just encapsulated within a native app\'s shell.

### **IoT app**

An IoT app can communicate with the Bot Framework by using the [Direct
Line
API](https://docs.botframework.com/en-us/restapi/directline3/#navtitle).
In some scenarios, it may also use [Microsoft Cognitive
Services](https://www.microsoft.com/cognitive-services/) to enable
capabilities such as image recognition and speech.

### **Other types of apps and games**

Other types of apps and games can communicate with the Bot Framework by
using the [Direct Line
API](https://docs.botframework.com/en-us/restapi/directline3/#navtitle).

**Creating a cross-platform mobile app that runs a bot**
--------------------------------------------------------

This example of creating a mobile app that runs a bot
uses [Xamarin](https://www.xamarin.com/), a popular tool for building
cross-platform mobile applications.

First, create a simple web view component and use it to host a [web chat
control](https://github.com/Microsoft/BotFramework-WebChat). Then, using
the Bot Framework Portal, [connect the
bot](https://docs.microsoft.com/en-us/bot-framework/bot-service-manage-channels) to
the Web Chat channel.

![Bot configuration
settings](media/image31.png){width="8.051388888888889in"
height="5.2756944444444445in"}

Next, specify the registered web chat URL as the source for the web view
control in the Xamarin app:

C\#Copy

public class WebPage : ContentPage

{

public WebPage()

{

var browser = new WebView();

browser.Source = \"https://webchat.botframework.com/embed/\<YOUR SECRET
KEY HERE\>\";

this.Content = browser;

}

}

Using this process, you can create a cross-platform mobile application
that renders the embedded web view with the web chat control.

![Back-channel](media/image32.png){width="12.275551181102362in"
height="5.708963254593176in"}

**Sample code**
---------------

For a complete sample that shows how to create a cross-platform mobile
app that runs a bot (as described in this article), see the [Bot in Apps
sample](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/capability-BotInApps) in
GitHub.

Embed a bot in a website
========================

Although bots commonly exist outside of websites, they can also be
embedded within a website. For example, you may embed a [knowledge
bot](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-knowledge-base) within
a website to enable users to quickly find information that might
otherwise be challenging to locate within complex website structures. Or
you might embed a bot within a help desk website to act as the first
responder to incoming user requests. The bot could independently resolve
simple issues
and [handoff](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-handoff-human) more
complex issues to a human agent.

This article explores integrating bots with websites and the process of
using the *backchannel*mechanism to facilitate private communication
between a web page and a bot.

Microsoft provides two different ways to integrate a bot in a website:
the Skype web control and an open source web control.

**Skype web control**
---------------------

The Skype web control is essentially a Skype client in a web-enabled
control. Built-in Skype authentication enables the bot to authenticate
and recogize users, without requiring the developer to write any custom
code. Skype will automatically recognize Microsoft Accounts used in its
web client.

Because the Skype web control simply acts as a front-end for Skype, the
user\'s Skype client automatically has access to the full context of any
conversation that the web control facilitates. Even after the web
browser is closed, the user may continue to interact with the bot using
the Skype client.

**Open source web control**
---------------------------

The [open source web chat
control](https://github.com/Microsoft/BotFramework-WebChat) is based
upon ReactJS and uses the [Direct Line
API](https://docs.botframework.com/en-us/restapi/directline3/#navtitle) to
communicate with the Bot Framework. The web chat control provides a
blank canvas for implementing the web chat, giving you full control over
its behaviors and the user experience that it delivers.

The *backchannel* mechanism enables the web page that is hosting the
control to communicate directly with the bot in a manner that is
entirely invisible to the user. This capability enables a number of
useful scenarios:

-   The web page can send relevant data to the bot (e.g., GPS location).

-   The web page can advise the bot about user actions (e.g., \"user
    > just selected Option A from the dropdown\").

-   The web page can send the bot the auth token for a logged-in user.

-   The bot can send relevant data to the web page (e.g., current value
    > of user\'s portfolio).

-   The bot can send \"commands\" to the web page (e.g., change
    > background color).

**Using the backchannel mechanism**
-----------------------------------

The [open source web chat
control](https://github.com/Microsoft/BotFramework-WebChat) communicates
with bots by using the [Direct Line
API](https://docs.botframework.com/en-us/restapi/directline3/#navtitle),
which allows activities to be sent back and forth between client and
bot. The most common type of activity is message, but there are other
types as well. For example, the activity type typingindicates that a
user is typing or that the bot is working to compile a response.

You can use the backchannel mechanism to exchange information between
client and bot without presenting it to the user by setting the activity
type to event. The web chat control will automatically ignore any
activities where type=\"event\".

**Sample code**
---------------

The [open source web chat
control](https://github.com/Microsoft/BotFramework-WebChat) is available
via GitHub. For details about how you can implement the backchannel
mechanism using the open source web chat control and the Bot Builder SDK
for Node.js, see [Use the backchannel
mechanism](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-backchannel).

Manage a bot
============

This topic explains how to manage a bot using the Azure portal.

**Bot settings overview**
-------------------------

![Bot settings overview](media/image33.png){width="2.2756944444444445in"
height="1.6548611111111111in"}

In the **Overview** blade, you can find high level information about
your bot. For example, you can see your bot\'s **Subscription
ID**, **pricing tier**, and **Messaging endpoint**.

**Bot management**
------------------

You can find most of your bot\'s management options under the **BOT
MANAGEMENT** section. Below is a list of options to help you manage your
bot.

![Bot management](media/image34.png){width="2.2243055555555555in"
height="2.93125in"}

  Option                    Description
  ------------------------- -------------------------------------------------------------------------------------------------------------------------------
  **Build**                 The Build tab provides options for making changes to your bot. This option is not available for **Registration Only Bot**.
  **Test in Web Chat**      Use the integrated Web Chat control to help you quickly test your bot.
  **Analytics**             If analytics is turned on for your bot, you can view the analytics data that Application Insights has collected for your bot.
  **Channels**              Configure the channels your bot uses to communicate with users.
  **Settings**              Manage various bot profile settings such as display name, analytics, and messaging endpoint.
  **Speech priming**        Manage the connections between your LUIS app and the Bing Speech service..
  **Bot Service pricing**   Manage the pricing tier for the bot service.

**App service settings**
------------------------

![App Service Settings](media/image35.png){width="2.327777777777778in"
height="1.1895833333333334in"}

The **Application Settings** blade contains detailed information about
your bot, such as the bot\'s environment, ID, Application Insights key,
Microsoft App ID, and Microsoft App password.

### **MicrosoftAppID and MicrosoftAppPassword**

You can find the **MicrosoftAppID** and **MicrosoftAppPassword** for
your bot in the **Application Settings** blade.

![Microsoft AppID and
Password](media/image36.png){width="6.3277777777777775in"
height="4.258333333333334in"}

Note

The **Bot Channels Registration** bot service comes with
a *MicrosoftAppID* but because there is no app service associated with
this type of service, there is no **Application Settings** blade for you
to look up the *MicrosoftAppPassword*. To get the password, you must go
generate one. To generate the password for a **Bot Channels
Registration**, see [Bot Channels Registration
password](https://docs.microsoft.com/en-us/bot-framework/bot-service-quickstart-registration#bot-channels-registration-password)

Edit a bot with online code editor
==================================

You can use the online code editor to build your bot without needing an
IDE. This topic will show you how to open your bot code in the online
code editor.

**Edit bot source code in online code editor**
----------------------------------------------

To edit a bot\'s source code in the online code editor, do the following
for the specific type of type you have.

### **Web App Bot**

1.  Sign into the [Azure portal](http://portal.azure.com/) and open the
    > blade for the bot.

2.  Under the **BOT MANAGEMENT** section, Click **Build**.

3.  Click **Open online code editor**. This will open the bot\'s code in
    > a new browser window.

> ![Open online code editor](media/image37.png){width="6.93125in"
> height="6.56875in"}
>
> Depending on the language of the bot, the file structure under
> the **WWWRoot**directory will be different. For example, if you have a
> C\# bot, your **WWWRoot** may look something like this:
>
> ![C\# file structure](media/image38.png){width="4.534722222222222in"
> height="6.310416666666667in"}
>
> If you have a Node.js bot, your **WWWRoot** may look something like
> this:
>
> ![Node.js file
> structure](media/image39.png){width="4.534722222222222in"
> height="4.138194444444444in"}

4.  Make code changes. For example, for C\# bots, you can start with
    > the **Dialogs/EchoDialog.cs** file. For Node.js bots, you can
    > start with the **App.js** file.

> Note
>
> While you can make code changes to current source files in the
> project, it is not possible to create new source files using the
> online code editor. To add new source files to the bot, you need
> to [download the
> source](https://docs.microsoft.com/en-us/bot-framework/bot-service-build-download-source-code) project,
> add your files and publish the changes back to Azure.

5.  Save your changes. For C\# bots that are on a **Consumption
    > plan** and all Node.js bots, the bot is automatically updated once
    > the source code is saved by clicking the **Save**button.

> ![Node.js file
> structure](media/image40.png){width="1.086111111111111in"
> height="0.6895833333333333in"}
>
> For C\# bots on an **App service** plan, open the **Console** blade
> and send the **build.cmd**command.
>
> ![Build project in console
> blade](media/image41.png){width="8.327777777777778in"
> height="4.154861111111111in"}
>
> Note
>
> If this command fails to build, try restarting your bot\'s app service
> and try building again. To restart your app service, from your bot\'s
> blade, click **All App service settings** then click
> the **Restart** button. ![Restart a web
> app](media/image42.png){width="8.327777777777778in"
> height="0.4486111111111111in"}

6.  Switch back to Azure portal and click **Test in Web Chat** to test
    > out your changes. If you already have the Web Chat open for this
    > bot, click **Start over** to see the new changes.

### **Functions Bot**

1.  Sign into the [Azure portal](http://portal.azure.com/) and open the
    > blade for the bot.

2.  Under the **BOT MANAGEMENT** section, Click **Build**.

3.  Click **Open this bot in Azure Functions**. This will open the bot
    > with the [Azure
    > Functions](http://go.microsoft.com/fwlink/?linkID=747839) UI.

4.  Make code changes. For example, update the function\'s messages
    > code. The screen shot below shows the Messages code for a Node.js
    > Functions Bot.

> ![Functions Bot Messages code
> editor](media/image43.png){width="8.224305555555556in"
> height="8.534722222222221in"}

5.  Save your code changes.

6.  Switch back to Azure portal and click **Test in Web Chat** to test
    > out your changes. If you already have the Web Chat open for this
    > bot, click **Start over** to see the new changes.

Download Bot Service source code
================================

Bot Service allows you to download the entire source project for your
bot. This allows you to work on your bot locally using an IDE of your
choice. Once you are done making changes, you can publish your changes
back to Azure.

This topic will show you how to download your bot\'s source code and
publishing the changes back to Azure.

**Download bot source code**
----------------------------

To develop your bot locally, do the following:

1.  In the Azure portal and open the blade for the bot.

2.  Under the **BOT MANAGEMENT** section, Click **Build**.

3.  Click **Download zip file**.

> ![Download source code](media/image44.png){width="6.93125in"
> height="6.56875in"}

4.  Extract the .zip file to a local directory.

5.  Navigate to the extracted folder and open the source files in your
    > favorite IDE.

6.  Make changes to your sources. Either edit existing source files or
    > add new ones to your project.

When you are ready, you can publish the sources back to Azure.

**Publish Node bot source code to Azure**
-----------------------------------------

To publish the sources back to Azure, run the following NPM command:

consoleCopy

npm run azure-publish

**Publish C\# bot source code to Azure**
----------------------------------------

Publishing C\# code to Azure using Visual Studio is a two step process:
First, you will need to configure publishing settings. Then, you can
publish your changes.

To configure publishing from Visual Studio, do the following:

1.  In Visual Studio, click **Solution Explorer**.

2.  Right-click your project name and click **Publish\...**.
    > The **Publish** window opens.

3.  Click **Create new profile**, click **Import profile**, and
    > click **OK**.

4.  Navigate to your project folder then navigate to
    > the **PostDeployScripts** folder, and select the file that ends
    > in **.PublishSettings**. Click **Open**.

Your project is now configured to publish changes to Azure.

Once your project is configured, you can publish your bot source code
back to Azure by doing the following:

1.  In Visual Studio, click **Solution Explorer**.

2.  Right-click your project name and click **Publish\...**.

3.  Click the **Publish** button to publish your changes to Azure.

Set up continuous deployment
============================

Continuous deployment allows you to develop your bot locally. Continuous
deployment is useful if your bot is checked into a source control
like **GitHub** or **Visual Studio Team Services**. As you check your
changes back into your source repository, your changes will
automatically be deployed to Azure.

Note

Once continuous deployment is set up, the [online code
editor](https://docs.microsoft.com/en-us/bot-framework/bot-service-build-online-code-editor) becomes *READ
ONLY*.

This topic will show you how to set up continuous deployment
for **GitHub** and **Visual Studio Team Services**.

**Continuous deployment using GitHub**
--------------------------------------

To set up continuous deployment using GitHub, do the following:

1.  [Fork](https://help.github.com/articles/fork-a-repo/) the GitHub
    > repository that contains the code you want to deploy to Azure.

2.  From the Azure portal, go to your bot\'s **Build** blade and
    > click **Configure continuous deployment**.

3.  Click **Setup**.

> ![Setup continuous
> deployment](media/image45.png){width="4.517361111111111in"
> height="0.36180555555555555in"}

4.  Click **Choose source** and choose **GitHub**.

> ![Choose GitHub](media/image46.png){width="6.396527777777778in"
> height="4.379166666666666in"}

5.  Click **Authorization** then click the **Authorize** button and
    > follow the prompts to give Azure authorization to access your
    > GitHub account.

Your continuous deployment with GitHub setup is complete. Whenever you
commit, your changes will automatically be deployed to Azure.

**Continuous deployment using Visual Studio**
---------------------------------------------

1.  From your bot\'s **Build** blade, click **Configure continuous
    > deployment**.

2.  Click **Setup**.

> ![Setup continuous
> deployment](media/image45.png){width="4.517361111111111in"
> height="0.36180555555555555in"}

3.  Click **Choose source** and choose **Visual Studio Team Services**.

> ![Choose Visual Studio Team
> Services](media/image47.png){width="6.396527777777778in"
> height="4.379166666666666in"}

4.  Click **Choose your account** and choose an account.

5.  Click **Choose a project** and choose a project.

6.  click **Choose Branch** and choose a branch to branch.

7.  Click **OK** to complete the setup process.

> ![Visual Studio
> configuration](media/image48.png){width="3.2583333333333333in"
> height="8.689583333333333in"}

Your continuous deployment with Visual Studio Team Services setup is
complete. Whenever you commit, your changes will automatically be
deployed to Azure.

**Disable continuous deployment**
---------------------------------

While your bot is configured for continuous deployment, you may not use
the online code editor to make changes to your bot. If you want to use
the online code editor, you can temporarily disable continuous
deployment.

To disable (or re-enable) continuous deployment, do the following:

1.  From your bot\'s **Build** blade, click **Configure continuous
    > deployment**.

2.  Click **Disconnect** to disable continuous deployment. To re-enable
    > continuous deployment, repeat these steps.

Test in Web Chat
================

Bot Service includes the [Web Chat
control](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-webchat) to
help you conveniently test your bot.

**Test a bot in the Azure Portal with Web Chat**
------------------------------------------------

Sign into the [Azure portal](https://portal.azure.com/) and open the
blade for the bot. In the Bot Management section, click **Test in Web
Chat**. Bot Service will load the Web Chat control and connect to your
bot.

![Test in Web Chat UI](media/image49.png){width="8.327777777777778in"
height="7.43125in"}

You can enter text to chat with your bot. If your bot supports speech,
you can click the microphone button to talk to your bot. If your bot
supports attachments, you can upload an attachment, such as an image.
Learn how to add features to your bot with the [Bot Builder
SDK](https://docs.microsoft.com/en-us/bot-framework/bot-builder-overview-getstarted).

Note

If the Web Chat control is not fully loaded after a few minutes, try
refreshing the page.

Bot analytics
=============

Analytics is an extension of [Application
Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-analytics).
Application Insights provides **service-level** and instrumentation data
like traffic, latency, and integrations. Analytics
provides **conversation-level**reporting on user, message, and channel
data.

**View analytics for a bot**
----------------------------

To access Analytics, open the bot in the developer portal and
click **Analytics**.

Too much data? [Enable and configure
sampling](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-sampling) to
reduce telemetry traffic and storage while maintaining statistically
correct analysis.

### **Specify channel**

Choose which channels appear in the graphs below. Note that if a bot is
not enabled on a channel, there will be no data from that channel.

![Select channel](media/image50.png){width="9.345138888888888in"
height="2.0347222222222223in"}

-   Check the check box to include a channel in the chart.

-   Clear the check box to remove a channel from the chart.

### **Specify time period**

Analysis is available for the past 90 days only. Data collection began
when Application Insights was enabled.

![Select time period](media/image51.png){width="6.258333333333334in"
height="0.8277777777777777in"}

Click the drop-down menu and then click the amount of time the graphs
should display. Note that changing the overall time frame will cause the
time increment (X-axis) on the graphs to change accordingly.

### **Grand totals**

The total number of active users and messages sent and received during
the specified time frame. Dashes \-- indicate no activity.

### **Retention**

Retention tracks how many users who sent one message came back later and
sent another one. The chart is a rolling 10-day window; the results are
not affected by changing the time frame.

![Retention chart](media/image52.png){width="10.051388888888889in"
height="4.43125in"}

Note that the most recent possible date is two days ago; a user sent
messages the day before yesterday and then *returned* yesterday.

### **User**

The Users graph tracks how many users accessed the bot using each
channel during the specified time frame.

![Users graph](media/image53.png){width="10.01736111111111in"
height="4.138194444444444in"}

-   The percentage chart shows what percentage of users used each
    > channel.

-   The line graph indicates how many users were accessing the bot at a
    > certain time.

-   The legend for the line graph indicates which color represents which
    > channel and the includes the total number of users during the
    > specified time period.

### **Messages**

The Message graph tracks how many messages were sent and received using
which channel during the specified time frame.

![Messages graph](media/image54.png){width="10.01736111111111in"
height="4.06875in"}

-   The percentage chart shows what percentage of messages were
    > communicated over each channel.

-   The line graph indicates how many messages were sent and received
    > over the specified time frame.

-   The legend for the line graph indicates which line color represents
    > each channel and the total number of messages sent and received on
    > that channel during the specified time period.

**Enable analytics**
--------------------

Analytics are not available until Application Insights has been enabled
and configured. Application Insights will begin collecting data as soon
as it is enabled. For example, if Application Insights was enabled a
week ago for a six-month-old bot, it will have collected one week of
data.

Note

Analytics requires both an Azure subscription and Application
Insights [resource](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource).
To access Application Insights, open the bot in the [Bot Framework
Portal](https://dev.botframework.com/) and click **Settings**.

1.  Create an Application
    > Insights [resource](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource).

2.  Open the bot in the dashboard. Click **Settings** and scroll down to
    > the **Analytics** section.

3.  Enter the information to connect the bot to Application Insights.
    > All fields are required.

![Connect Insights](media/image55.png){width="6.482638888888889in"
height="3.2416666666666667in"}

### **AppInsights Instrumentation Key**

To find this value, open Application Insights and navigate
to **Configure** \> **Properties**.

### **AppInsights API key**

Provide an Azure App Insights API key. Learn how to [generate a new API
key](https://dev.applicationinsights.io/documentation/Authorization/API-key-and-App-ID).
Only **Read**permission is required.

### **AppInsights Application ID**

To find this value, open Application Insights and navigate
to **Configure** \> **API Access**.

For more information on how to locate these values, see [Application
Insights
keys](https://docs.microsoft.com/en-us/bot-framework/bot-service-resources-app-insights-keys).

Connect a bot to channels
=========================

A channel is the connection between the Bot Framework and communication
apps. You configure a bot to connect to the channels you want it to be
available on. For example, a bot connected to the Skype channel can be
added to a contact list and people can interact with it in Skype.

The channels include many popular services, such
as [Cortana](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-cortana), [Facebook
Messenger](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-facebook), [Kik](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-kik),
and [Slack](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-slack),
as well as several others. [Skype](https://dev.skype.com/bots) and Web
Chat are pre-configured for you.

Connecting to channels is quick and easy in the [Azure
Portal](https://portal.azure.com/).

**Get started**
---------------

For most channels, you must provide channel configuration information to
run your bot on the channel. Most channels require that your bot have an
account on the channel, and others, like Facebook Messenger, require
your bot to have an application registered with the channel also.

To configure your bot to connect to a channel, complete the following
steps:

1.  Sign in to the [Azure Portal](https://portal.azure.com/).

2.  Select the bot that you want to configure.

3.  In the Bot Service blade, click **Channels** under **Bot
    > Management**.

4.  Click the icon of the channel you want to add to your bot.

![Connect to channels](media/image56.png){width="8.327777777777778in"
height="6.396527777777778in"}

After you\'ve configured the channel, users on that channel can start
using your bot.

**Publish a bot**
-----------------

The publishing process is different for each channel.

### **Cortana**

Bots are published to Cortana from
the [dashboard](https://aka.ms/cortana-publish) and are used to power
Cortana skills. Publishing a bot submits it for review. Cortana skills
can be deployed for your own use, deployed to a small group, or
published to the world.

### **Skype**

Bots are published to Skype from the [configuration
page](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-skypeforbusiness).
Publishing a bot submits it for review. Before review, the bot is
limited to 100 contacts. Approved bots do not have limited contacts and
you may opt to have the bot included in the Skype bot directory.

### **Skype for Business**

Skype for Business bots are registered with a [Skype for Business Online
tenant](https://msdn.microsoft.com/en-us/skype/Skype-For-Business-Bot-Framework/docs/overview) by
a Tenant Administrator.

Tip

To view the status of a review, open the bot in the [Bot Framework
Portal](https://dev.botframework.com/) and click **Channels**. If the
bot is not approved, the result will link to the reason why. After
making the required changes, resubmit the bot for review.

Connect a bot to Cortana
========================

Cortana is a speech-enabled channel that can send and receive voice
messages in addition to textual conversation. A bot intended to connect
to Cortana should be designed for speech as well as text. A
Cortana *skill* is a bot that can be invoked using a Cortana client.
Publishing a bot adds the bot to the list of available skills.

To add the Cortana channel, open the bot in the [Azure
Portal](https://portal.azure.com/), click the **Channels** blade, and
then click **Cortana**.

![Add Cortana channel](media/image57.png){width="8.034722222222221in"
height="5.293055555555555in"}

**General bot information**
---------------------------

All fields marked with an asterisk (\*) are required. Bots must be
published on the Bot Framework before they can be connected to Cortana.

![Provide general
information](media/image58.png){width="7.1722222222222225in"
height="5.965277777777778in"}

### **Skill Icon**

Select a custom icon to represent this bot. This icon is displayed in
the Cortana canvas when this skill is invoked and anywhere skills are
discoverable, such as the Microsoft store. The image must be a PNG, 60 x
60 pixels, and no larger than 30kb.

### **Display Name**

The name of this skill as displayed to the user at the top of Cortana\'s
visual UI.

### **Invocation Name**

The name that Cortana will recognize and use to invoke this skill when
spoken aloud by the user. See the [Invocation Name
Guidelines](https://aka.ms/cortana-invocation-guidelines) for more
information on how to choose this phrase.

### **Skill description**

Describe the skill. This is used where bots are discoverable, like the
Microsoft store.

### **Short description**

This summary will be used to describe the skill in Cortana's Notebook.

Note

For basic skills, this is all that is required. Click **Connect to
Cortana** to complete the connection. For more advanced skills, add a
connected account or configure access to user profile and contextual
information.

**Manage user identity**
------------------------

The default value is *Disabled*. If *Enabled*, the user will be required
to log in before using this skill. Cortana can manage this skill\'s user
identity and tokens across devices if an OAuth2 identity provider is
added as a [connected
service](https://aka.ms/CortanaSkillsBotConnectedAccount).

Note

Only **Auth Code Grant** authentication is supported. **Implicit
Grant** is currently not supported.

![Define user profile
request](media/image59.png){width="8.845138888888888in"
height="13.310416666666667in"}

  Field                                             Description
  ------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------
  Icon                                              The icon to display when the sign-in form is displayed.
  Account Name                                      The name to be shown when the sign-in form is displayed.
  Client ID for third-party services                The client id that Cortana needs as part of the OAuth flow.
  Client secret/password for third party services   The client secret Cortana needs as part of the OAuth flow.
  List of scopes                                    A list of scopes Cortana needs as part of the skill execution flow.
  Authorization URL                                 The URI Cortana will call to authorize the user.
  Token URL                                         The URI Cortana will call to fetch tokens.
  Client authentication scheme                      The mechanism by which Cortana will pass a bearer token.
  Token option                                      How Cortana should obtain tokens. If unsure, select POST.
  Intranet toggle                                   Select if this skill's connected service requires *intranet* access to authenticate users. If unsure, leave this blank.)

**Request user profile data**
-----------------------------

Cortana provides access to several different types of user profile
information, which is useful in customizing the bot for different users.

![Define user profile
request](media/image60.png){width="7.396527777777778in"
height="3.7069444444444444in"}

1.  Click **Add a user profile request**.

2.  Click **Select Data** and then select the user profile information
    > from the drop-down list.

3.  Add a **Friendly name** to identify this information in
    > the UserInfo [entity](https://aka.ms/lgvcto).

4.  Click **Remove** to remove this request for data or click **Add a
    > user profile request** again to define another request.

Click **Save**. The bot will be deployed automatically as a Cortana
skill.

**Enable speech recognition priming**
-------------------------------------

If your bot uses a Language Understanding (LUIS) app, register the LUIS
application ID.

Click the **Settings** tab and then under **Configuration**, enter the
LUIS application ID in the **Speech recognition priming with LUIS** text
box. This helps your bot recognize spoken utterances that are defined in
your LUIS model. ![Enable speech recognition
priming](media/image61.png){width="7.5in" height="2.7069444444444444in"}

Connect a bot to Skype for Business
===================================

Skype for Business Online keeps you connected with co-workers and
business partners through instant messaging, phone, and video calls.
Extend this functionality by building bots that users can discover and
interact with through the Skype for Business interface.

Note

The Skype for Business Bot Framework channel is currently supported for
Skype for Business Online. Skype for Business Server 2015 is not
supported.

**Enable the channel**
----------------------

Open the bot in the [Azure Portal](https://portal.azure.com/), click
the **Channels** blade, and then click **Skype for Business**. The bot
is now enabled.

Connecting the bot with Skype for Business Online is performed by
a **Tenant Administrator** of that Skype for Business tenant.

Connect a bot to Direct Line
============================

You can enable your own client application to communicate with your bot
by using the Direct Line channel.

**Add the Direct Line channel**
-------------------------------

To add the Direct Line channel, open the bot in the [Azure
Portal](https://portal.azure.com/), click the **Channels** blade, and
then click **Direct Line**.

![Add Direct Line channel](media/image62.png){width="7.93125in"
height="6.482638888888889in"}

**Add new site**
----------------

Next, add a new site that represents the client application that you
want to connect to your bot. Click **Add new site**, enter a name for
your site, and click **Done**.

![Add Direct Line site](media/image63.png){width="8.327777777777778in"
height="3.551388888888889in"}

**Manage secret keys**
----------------------

When your site is created, the Bot Framework generates secret keys that
your client application can use
to [authenticate](https://docs.microsoft.com/en-us/bot-framework/rest-api/bot-framework-rest-direct-line-3-0-authentication) the
Direct Line API requests that it issues to communicate with your bot. To
view a key in plain text, click **Show** for the corresponding key.

![Show Direct Line key](media/image64.png){width="8.327777777777778in"
height="6.5in"}

Copy and securely store the key that is shown. Then use the key
to [authenticate](https://docs.microsoft.com/en-us/bot-framework/rest-api/bot-framework-rest-direct-line-3-0-authentication) the
Direct Line API requests that your client issues to communicate with
your bot, or alternatively, use the Direct Line API to [exchange the key
for a
token](https://docs.microsoft.com/en-us/bot-framework/rest-api/bot-framework-rest-direct-line-3-0-authentication#generate-token) that
your client can use to authenticate its subsequent requests within the
scope of a single conversation.

![Copy Direct Line key](media/image65.png){width="8.327777777777778in"
height="6.5in"}

**Configure settings**
----------------------

Finally, configure settings for the site.

-   Select the Direct Line protocol version that your client application
    > will use to communicate with your bot. \> \[!TIP\] \> If you are
    > creating a new connection between your client application and bot,
    > use Direct Line API 3.0.

When finished, click **Done** to save the site configuration. You can
repeat this process, beginning with [Add new
site](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-directline#add-new-site),
for each client application that you want to connect to your bot.

 Develop bots for Microsoft Teams
=================================

Build and connect intelligent bots to interact with Microsoft Teams
users naturally through chat. Or provide a simple commands-based bot, to
be used as your \"command-line\" interface for your broader Teams app
experience. You can make a notification-only bot, which can push
information relevant to your users directly to them in a channel or
direct message. You can even bring your existing Bot Framework--based
bot and add Teams-specific support to make your experience shine.

![Example of a bot assisting a user](media/image66.png){width="20.0in"
height="11.258333333333333in"}

Tip

If you are just looking for a way to simply extend your team by
integrating with custom tools and services in a secure manner, check out
our [custom
bots](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/custom-bot) feature.
Be aware, though, that custom bots simply leverage your existing web
services---they can\'t access non-messaging APIs, perform asynchronous
posting, or add button actions to cards.

**What you need to know: Bots**
-------------------------------

Other than its hexagonal avatar icon, a bot appears just like any other
team member you interact with, in a channel or in one-on-one
conversations. It is always online and does not have a mood message.

Bots in Teams can surface in a one-on-one context (\"personal scope\"),
as a member of a team (\"team scope\"), or both. For the latter, they
take part in a conversation only when you \@mention them. For the
former, you can address them via the conversation interface or access
them in the apps personal experience from the app bar flyout.

With Microsoft Teams apps, you can make the bot the star of your
experience, or just a helper. Bots are distributed as part of your
broader app package, which can include other capabilities such as tabs
or messaging extensions.

If your bot is the star, be sure to take advantage of
the [tabs](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/tabs/tabs-overview) capability
as well. Use this rich web view to surface accompanying experiences and
information that helps your users best interact with your service.

Microsoft Teams supports much of the [Microsoft Bot
Framework](https://dev.botframework.com/) functionality. (If you already
have a bot that\'s based on the Bot Framework, you can easily adapt it
to work in Microsoft Teams.) We recommend you use either C\# or
TypeScript to take advantage of our SDKs.

We want to make development of Microsoft Teams apps as easy as possible,
so we build and maintain extensions to the Bot Builder SDK. These
packages extend the basic Bot Builder classes and methods with the
following:

-   Using specialized card types like the Office 365 Connector card

-   Consuming and setting Teams-specific channel data on activities

-   Processing messaging extension requests

-   Handling rate limiting

The SDK extensions install dependencies, including the Bot Builder SDK.

-   **.NET** To use the Microsoft Teams extensions for the Bot Builder
    > SDK for .NET, install
    > the [Microsoft.Bot.Connector.Teams](https://www.nuget.org/packages/Microsoft.Bot.Connector.Teams) NuGet
    > package in your Visual Studio project.

-   **Node.js** To use the Microsoft Teams extensions for the Bot
    > Builder SDK for Node.js, add
    > the [botbuilder-teams](https://www.npmjs.com/package/botbuilder-teams) npm
    > package.

-   **Source code** You can find the full source code for the extensions
    > in
    > the [BotBuilder-MicrosoftTeams](https://github.com/OfficeDev/BotBuilder-MicrosoftTeams) repo
    > on Github.

Important

You can develop Teams apps in any other web-programming technology and
call the [Bot Framework REST
APIs](https://docs.microsoft.com/en-us/bot-framework/rest-api/bot-framework-rest-overview) directly,
but you must perform all token handling yourself.

Follow these steps to build a great Teams bot:

-   [Design a great
    > bot](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/design#designing-a-great-bot):
    > Microsoft Teams is the place for group and team collaboration.
    > Consider what functionality your bot can bring to this
    > collaboration environment, via 1:1 conversations or as part of a
    > channel conversation. A great bot on Teams will also find ways to
    > leverage the unique tabs feature, via a [configurable
    > tab](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/tabs/tabs-overview) or
    > a [static
    > tab](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/tabs/tabs-static).

-   [Create and register your bot in the Bot
    > Framework](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/bots/bots-create):
    > Take advantage of the great tools, documentation, and community
    > provided by the Bot Framework team.

-   [Develop your
    > bot](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/bots/bots-conversations):
    > Add basic conversation flow and leverage channel-specific
    > functionality. If you develop in .NET or Node.js, use
    > our [extensions for the Bot Builder
    > SDK](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/code#microsoft-teams-extensions-for-the-bot-builder-sdk) to
    > simplify your work.

-   [Test your
    > bot](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/bots/bots-test):
    > Add your bot for 1:1 or team conversations to see it in action.

-   [Publish your
    > bot](https://docs.microsoft.com/en-us/microsoftteams/platform/publishing/apps-publish):
    > Create your Teams package, add other capabilities, and submit it
    > to the Office Store.

**What you need to know: Custom bots**
--------------------------------------

Custom bots allow you to create a simple bot for basic interaction, like
kicking off a workflow or other simple commands you may need. These
custom bots live only in the team in which you create them and are
intended for simple processes specific to your company\'s workflow.
See [Custom
bots](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/custom-bot) for
more information.

Connect a bot to Web Chat
=========================

When you [create a
bot](https://docs.microsoft.com/en-us/bot-framework/bot-service-quickstart) with
Bot Service, the Web Chat channel is automatically configured for you.
The Web Chat channel includes the web chat control, which provides the
ability for users to interact with your bot directly in a web page.

![Web chat sample](media/image67.png){width="8.327777777777778in"
height="7.06875in"}

The Web Chat channel in the Bot Framework Portal contains everything you
need to embed the web chat control in a web page. All you have to do to
use the web chat control is get your bot\'s secret key and embed the
control in a web page.

Tip

To see how various Bot Framework features look and work on this
channel, [use the Channel
Inspector](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-inspector).

**Get your bot secret key**
---------------------------

1.  Open your bot in the [Azure Portal](http://portal.azure.com/) and
    > click **Channels** blade.

2.  Click **Edit** for the **Web Chat** channel.\
    > ![Web chat channel](media/image68.png){width="7.482638888888889in"
    > height="3.689583333333333in"}

3.  Under **Secret keys**, click **Show** for the first key.\
    > ![Secret key](media/image69.png){width="5.965277777777778in"
    > height="7.293055555555555in"}

4.  Copy the **Secret key** and the **Embed code**.

5.  Click **Done**.

**Embed the web chat control in your website**
----------------------------------------------

You can embed the web chat control in your website by using one of two
options.

### **Option 1 - Keep your secret hidden, exchange your secret for a token, and generate the embed**

Use this option if you can execute a server-to-server request to
exchange your web chat secret for a temporary token, and if you want to
make it difficult for other developers to embed your bot in their
websites. Although using this option will not absolutely prevent other
developers from embedding your bot in their websites, it does make it
difficult for them to do so.

To exchange your secret for a token and generate the embed:

1.  Issue a **GET** request
    > to https://webchat.botframework.com/api/tokens and pass your web
    > chat secret via the Authorization header. The Authorization header
    > uses the BotConnector scheme and includes your secret, as shown in
    > the example request below.

2.  The response to your **GET** request will contain the token
    > (surrounded with quotation marks) that can be used to start a
    > conversation by rendering the web chat control within
    > an **iframe**. A token is valid for one conversation only; to
    > start another conversation, you must generate a new token.

3.  Within the iframe **Embed code** that you copied from the Web Chat
    > channel within the Bot Framework Portal (as described in [Step
    > 1](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-webchat#step-1) above),
    > change the s= parameter to t=and replace \"YOUR\_SECRET\_HERE\"
    > with your token.

Note

Tokens will automatically be renewed before they expire.

##### **Example request**

requestCopy

GET https://webchat.botframework.com/api/tokens

Authorization: BotConnector YOUR\_SECRET\_HERE

##### **Example response**

responseCopy

\"IIbSpLnn8sA.dBB.MQBhAFMAZwBXAHoANgBQAGcAZABKAEcAMwB2ADQASABjAFMAegBuAHYANwA.bbguxyOv0gE.cccJjH-TFDs.ruXQyivVZIcgvosGaFs\_4jRj1AyPnDt1wk1HMBb5Fuw\"

##### **Example iframe (using token)**

HTMLCopy

\<iframe
src=\"https://webchat.botframework.com/embed/YOUR\_BOT\_ID?t=YOUR\_TOKEN\_HERE\"\>\</iframe\>

### **Option 2 - Embed the web chat control in your website using the secret**

Use this option if you want to allow other developers to easily embed
your bot into their websites.

Warning

If you use this option, other developers can embed your bot into their
websites by simply copying your embed code.

To embed your bot in your website by specifying the secret within
the iframe tag:

1.  Copy the iframe **Embed code** from the Web Chat channel within the
    > Bot Framework Portal (as described in [Step
    > 1](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-webchat#step-1) above).

2.  Within that **Embed code**, replace \"YOUR\_SECRET\_HERE\" with
    > the **Secret key** value that you copied from the same page.

##### **Example iframe (using secret)**

HTMLCopy

\<iframe
src=\"https://webchat.botframework.com/embed/YOUR\_BOT\_ID?s=YOUR\_SECRET\_HERE\"\>\</iframe\>

**Style the web chat control**
------------------------------

You may change the size of the web chat control by using
the style attribute of the iframe to specify height and width.

HTMLCopy

\<iframe style=\"height:480px; width:402px\" src=\"\... SEE ABOVE
\...\"\>\</iframe\>

![Chat control Client](media/image70.png){width="4.6722222222222225in"
height="5.379166666666666in"}

You can enable a voice interface in the Web Chat control. Users interact
with the voice interface by using the microphone in the Web Chat
control.

![Web chat speech sample](media/image71.png){width="5.189583333333333in"
height="3.379166666666667in"}

If the user types instead of speaking a response, Web Chat turns off the
speech functionality and the bot gives only a textual response instead
of speaking out loud. To re-enable the spoken response, the user can use
the microphone to respond to the bot the next time. If the microphone is
accepting input, it appears dark or filled-in. If it\'s grayed out, the
user clicks on it to enable it.

**Prerequisites**
-----------------

Before you run the sample, you need to have a Direct Line secret or
token for the bot that you want to run using the Web Chat control.

-   See [Connect a bot to Direct
    > Line](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-directline) for
    > information on getting a Direct Line secret associated with your
    > bot.

-   See [Generate a Direct Line
    > token](https://docs.microsoft.com/en-us/bot-framework/rest-api/bot-framework-rest-direct-line-3-0-authentication) for
    > information on exchanging the secret for a token.

**Customizing Web Chat for speech**
-----------------------------------

To enable the speech functionality in Web Chat, you need to customize
the JavaScript code that invokes the Web Chat control. You can try out
voice-enabled Web Chat locally using the following steps.

1.  Download the [sample
    > index.html](https://aka.ms/web-chat-speech-sample).

2.  Edit the code in index.html according to the type of speech support
    > you want to add. The types of speech implementations are described
    > in [Enable speech
    > services](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-webchat-speech#enable-speech-services).

3.  Start a web server. One way to do so is to use npm http-server at a
    > Node.js command prompt.

    -   To install http-server globally so it can be run from the
        > command line, run this command:

> Copy
>
> npm install http-server- -g

-   To start a web server using port 8000, from the directory that
    > contains index.html, run this command:

> Copy
>
> http-server -p 8000

1.  Aim your browser at http://localhost:8000/samples?parameters. For
    > example, http://localhost:8000/samples?s=YOURDIRECTLINESECRET invokes
    > the bot using a Direct Line secret. The parameters that can be set
    > in the query string are described in the following table:

  Parameter   Description
  ----------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  s           Direct Line secret. See [Connect a bot to Direct Line](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-directline) for information on getting a Direct Line secret.
  t           Direct Line token. See [Generate a Direct Line token](https://docs.microsoft.com/en-us/bot-framework/rest-api/bot-framework-rest-direct-line-3-0-authentication) for info on how to generate this token.
  domain      Optional. The URL of an alternate Direct Line endpoint.
  webSocket   Optional. Set to \'true\' to use WebSocket to receive messages. Default is false.
  userid      Optional. The ID of the bot user.
  username    Optional. The user name of the bot\'s user.
  botid       Optional. ID of the bot.
  botname     Optional. Name of the bot.

**Enable speech services**
--------------------------

The customization allows you to add speech functionality in any of the
following ways:

-   **Browser-provided speech** - Use speech functionality built into
    > the web browser. At this time, this functionality is only
    > available on the Chrome browser.

-   **Use Bing Speech service** - You can use the Bing Speech service to
    > provide speech recognition and synthesis. This way of access
    > speech functionality is supported by a variety of browsers. In
    > this case, the processing is done on a server instead of on the
    > browser.

-   **Create a custom speech service** - You can create your own custom
    > speech recognition and voice synthesis components.

### **Browser-provided speech**

The following code instantiates speech recognizer and speech synthesis
components that come with the browser. This method of adding speech is
not supported by all browsers.

Note

Google Chrome supports the browser speech recognizer. However, Chrome
may block the microphone in the following cases:

-   If the URL of the page that contains Web Chat begins
    > with http:// instead of https://.

-   If the URL is a local file using the file:// protocol instead
    > of http://localhost:8000.

JavaScriptCopy

const speechOptions = {

speechRecognizer: new BotChat.Speech.BrowserSpeechRecognizer(),

speechSynthesizer: new BotChat.Speech.BrowserSpeechSynthesizer()

};

### **Bing Speech service**

The following code instantiates speech recognizer and speech synthesis
components that use the Bing Speech service. The recognition and
generation of speech is performed on the server. This mechanism is
supported in multiple browsers.

Tip

You can use speech recognition priming to improve your bot\'s speech
recognition accuracy if you use the Bing Speech service. For more
information, check out the [Speech Support in Bot
Framework](https://blog.botframework.com/2017/06/26/Speech-To-Text) blog
post.

JavaScriptCopy

const speechOptions = {

speechRecognizer: new CognitiveServices.SpeechRecognizer({
subscriptionKey: \'YOUR\_COGNITIVE\_SPEECH\_API\_KEY\' }),

speechSynthesizer: new CognitiveServices.SpeechSynthesizer({

gender: CognitiveServices.SynthesisGender.Female,

subscriptionKey: \'YOUR\_COGNITIVE\_SPEECH\_API\_KEY\',

voiceName: \'Microsoft Server Speech Text to Speech Voice (en-US,
JessaRUS)\'

})

};

#### **Use the Bing Speech service with a token**

You also have the option to enable Cognitive Services speech recognition
using a token. The token is generated in a secure back end using your
API key.

The following example code shows how the token fetch is done from a
secure back end to avoid exposing the API key.

JavaScriptCopy

function getToken() {

// This call would be to your backend, or to retrieve a token that was
served as part of the original page.

return fetch(

\'https://api.cognitive.microsoft.com/sts/v1.0/issueToken\',

{

headers: {

\'Ocp-Apim-Subscription-Key\': \'YOUR\_COGNITIVE\_SPEECH\_API\_KEY\'

},

method: \'POST\'

}

).then(res =\> res.text());

}

const speechOptions = {

speechRecognizer: new CognitiveServices.SpeechRecognizer({

fetchCallback: (authFetchEventId) =\> getToken(),

fetchOnExpiryCallback: (authFetchEventId) =\> getToken()

}),

speechSynthesizer: new BotChat.Speech.BrowserSpeechSynthesizer()

};

### **Custom Speech service**

You can also provide your own custom speech recognition that implements
ISpeechRecognizer or speech synthesis that implements ISpeechSynthesis.

JavaScriptCopy

const speechOptions = {

speechRecognizer: new YourOwnSpeechRecognizer(),

speechSynthesizer: new YourOwnSpeechSynthesizer()

};

### **Pass the speech options to Web Chat**

The following code passes the speech options to the Web Chat control:

JavaScriptCopy

BotChat.App({

bot: bot,

locale: params\[\'locale\'\],

resize: \'detect\',

// sendTyping: true, // defaults to false. set to true to send
\'typing\' activities to bot (and other users) when user is typing

speechOptions: speechOptions,

user: user,

directLine: {

domain: params\[\'domain\'\],

secret: params\[\'s\'\],

token: params\[\'t\'\],

webSocket: params\[\'webSocket\'\] && params\[\'webSocket\'\] ===
\'true\' // defaults to true

}

}, document.getElementById(\'BotChatGoesHere\'));

**Next steps**
--------------

Now that you can enable voice interaction with Web Chat, learn how your
bot constructs spoken messages and adjusts the state of the microphone:

-   [Add speech to messages
    > (C\#)](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-text-to-speech)

-   [Add speech to messages
    > (Node.js)](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-text-to-speech)

Connect a bot to Office 365 email
=================================

Bots can communicate with users via Office 365 email in addition to
other [channels](https://docs.microsoft.com/en-us/bot-framework/bot-service-manage-channels).
When a bot is configured to access an email account, it receives a
message when a new email arrives. The bot can then respond as indicated
by its business logic. For example, the bot could send an email reply
acknowledging an email was received with the message, \"Hi! Thanks for
your order! We will begin processing it immediately.\"

Warning

It is a violation of the Bot Framework [Code of
Conduct](https://www.botframework.com/Content/Microsoft-Bot-Framework-Preview-Online-Services-Agreement.htm) to
create \"spambots\", including bots that send unwanted or unsolicited
bulk email.

**Configure email credentials**
-------------------------------

You can connect a bot to the Email channel by entering Office 365
credentials in the Email channel configuration.

To add the Email channel, open the bot in the [Azure
Portal](https://portal.azure.com/), click the **Channels** blade, and
then click **Email**. Enter your valid email credentials and
click **Save**.

![Enter email
credentials](media/image72.png){width="5.154861111111111in"
height="2.7243055555555555in"}

The Email channel currently works with Office 365 only. Other email
services are not currently supported.

**Customize emails**
--------------------

The Email channel supports sending custom properties to create more
advanced, customized emails using the channelData property.

  Property     Description
  ------------ --------------------------------------------------------------
  HtmlBody     The HTML to use for the body of the message.
  Subject      The subject to use for the message.
  Importance   The importance flag to use for the message.(Low/Normal/High)

The following example message shows a JSON file that includes
the channelData properties.

JSONCopy

{

\"type\": \"message\",

\"locale\": \"en-Us\",

\"channelID\":\"email\",

\"from\": { \"id\":\"mybot\@mydomain.com\", \"name\":\"My bot\"},

\"recipient\": { \"id\":\"joe\@otherdomain.com\", \"name\":\"Joe Doe\"},

\"conversation\": { \"id\":\"123123123123\", \"topic\":\"awesome chat\"
},

\"channelData\":

{

\"htmlBody\" : \"\<html\>\<body style = /\"font-family: Calibri;
font-size: 11pt;/\" \>This is more than awesome\</body\>\</html\>\",

\"subject\":\"Super awesome message subject\",

\"importance\":\"high\"

}

}

For more information about using channelData, see
the [Node.js](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-ChannelData) sample
or [.NET](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-channeldata) documentation.

Connect a bot to GroupMe
========================

You can configure a bot to communicate with people using the GroupMe
group messaging app.

Tip

To see how various Bot Framework features look and work on this
channel, [use the Channel
Inspector](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-inspector).

**Sign up for a GroupMe account**
---------------------------------

If you don\'t have a GroupMe account, [sign up for a new
account](https://web.groupme.com/signup).

**Create a GroupMe application**
--------------------------------

[Create a GroupMe
application](https://dev.groupme.com/applications/new) for your bot.

Use this callback URL: https://groupme.botframework.com/Home/Login

![Create app](media/image73.png){width="9.01736111111111in"
height="7.3277777777777775in"}

**Gather credentials**
----------------------

1.  In the **Redirect URL** field, copy the value after **client\_id=**.

2.  Copy the **Access Token** value.

![Copy client ID and access
token](media/image74.png){width="9.172222222222222in"
height="4.413888888888889in"}

**Submit credentials**
----------------------

1.  On dev.botframework.com, paste the **client\_id** value you just
    > copied into the **Client ID**field.

2.  Paste the **Access Token** value into the **Access Token** field.

3.  Click **Save**.

![Enter credentials](media/image75.png){width="6.465277777777778in"
height="2.7756944444444445in"}

Connect a bot to Facebook Messenger
===================================

To learn more about developing for Facebook Messenger, see
the [Messenger platform
documentation](https://developers.facebook.com/docs/messenger-platform).
You may wish to review Facebook\'s [pre-launch
guidelines](https://developers.facebook.com/docs/messenger-platform/product-overview/launch#app_public), [quick
start](https://developers.facebook.com/docs/messenger-platform/guides/quick-start),
and [setup
guide](https://developers.facebook.com/docs/messenger-platform/guides/setup).

To configure a bot to communicate using Facebook Messenger, enable
Facebook Messenger on a Facebook page and then connect the bot to the
app.

Tip

To see how various Bot Framework features look and work on this
channel, [use the Channel
Inspector](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-inspector).

Note

The Facebook UI may appear slightly different depending on which version
you are using.

**Copy the Page ID**
--------------------

The bot is accessed through a Facebook Page. [Create a new Facebook
Page](https://www.facebook.com/bookmarks/pages) or go to an existing
Page.

-   Open the Facebook Page\'s **About** page and then copy and save
    > the **Page ID**.

**Create a Facebook app**
-------------------------

[Create a new Facebook
App](https://developers.facebook.com/quickstarts/?platform=web) on the
Page and generate an App ID and App Secret for it.

![Create an App ID](media/image76.png){width="6.06875in"
height="2.5347222222222223in"}

-   Copy and save the **App ID** and the **App Secret**.

![Save App ID and secret](media/image77.png){width="8.172222222222222in"
height="2.7583333333333333in"}

Set the \"Allow API Access to App Settings\" slider to \"Yes\".

![App settings](media/image78.png){width="7.93125in"
height="1.586111111111111in"}

**Enable messenger**
--------------------

Enable Facebook Messenger in the new Facebook App.

-   On the **Product Setup** page of the app, click **Get Started** and
    > then click **Get Started** again.

![Enable messenger](media/image79.png){width="7.913888888888889in"
height="4.741666666666666in"}

**Generate a Page Access Token**
--------------------------------

In the **Token Generation** panel of the Messenger section, select the
target Page. A Page Access Token will be generated.

-   Copy and save the **Page Access Token**.

![Generate token](media/image80.png){width="9.172222222222222in"
height="4.8277777777777775in"}

**Enable webhooks**
-------------------

Click **Set up Webhooks** to forward messaging events from Facebook
Messenger to the bot.

![Enable webhook](media/image81.png){width="9.258333333333333in"
height="1.7243055555555555in"}

**Provide webhook callback URL and verify token**
-------------------------------------------------

Return to the [Bot Framework Portal](https://dev.botframework.com/).
Open the bot, click the **Channels** tab, and then click **Facebook
Messenger**.

-   Copy the **Callback URL** and **Verify Token** values from the
    > portal.

![Copy values](media/image82.png){width="5.06875in" height="2.43125in"}

1.  Return to Facebook Messenger and paste the **Callback
    > URL** and **Verify Token** values.

2.  Under **Subscription Fields**,
    > select *message\_deliveries*, *messages*, *messaging\_options*,
    > and *messaging\_postbacks*.

3.  Click **Verify and Save**.

![Configure webhook](media/image83.png){width="6.56875in"
height="3.0347222222222223in"}

**Provide Facebook credentials**
--------------------------------

On the Bot Framework Portal, paste the **Page ID**, **App ID**, **App
Secret**, and **Page Access Token**values copied from Facebook Messenger
previously.

![Enter credentials](media/image84.png){width="5.051388888888889in"
height="4.2756944444444445in"}

**Submit for review**
---------------------

Facebook requires a Privacy Policy URL and Terms of Service URL on its
basic app settings page. The [Code of
Conduct](https://aka.ms/bf-conduct) page contains third party resource
links to help create a privacy policy. The [Terms of
Use](https://aka.ms/bf-terms) page contains sample terms to help create
an appropriate Terms of Service document.

After the bot is finished, Facebook has its own [review
process](https://developers.facebook.com/docs/messenger-platform/app-review) for
apps that are published to Messenger. The bot will be tested to ensure
it is compliant with Facebook\'s [Platform
Policies](https://developers.facebook.com/docs/messenger-platform/policy-overview).

**Make the App public and publish the Page**
--------------------------------------------

Note

Until an app is published, it is in [Development
Mode](https://developers.facebook.com/docs/apps/managing-development-cycle).
Plugin and API functionality will only work for admins, developers, and
testers.

After the review is successful, in the App Dashboard under App Review,
set the app to Public. Ensure that the Facebook Page associated with
this bot is published. Status appears in Pages settings.

Connect a bot to Kik
====================

You can configure your bot to communicate with people using the Kik
messaging app.

Tip

To see how various Bot Framework features look and work on this
channel, [use the Channel
Inspector](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-inspector).

**Install Kik on your phone**
-----------------------------

If you don\'t have Kik installed on your phone, you can install it via
your phone\'s app store or at [the Kik website](https://www.kik.com/)

**Log into the dev portal with your mobile phone**
--------------------------------------------------

[Log into the Kik portal](https://dev.kik.com/) on your mobile phone.

**Follow the bot setup process**
--------------------------------

Give the bot a name.

![Set up bot](media/image85.png){width="8.327777777777778in"
height="9.948611111111111in"}

**Gather credentials**
----------------------

On the Configuration tab, copy the **Name** and **API key**.

![Copy bot information](media/image86.png){width="8.327777777777778in"
height="4.379166666666666in"}

**Submit credentials**
----------------------

![Paste credentials](media/image87.png){width="8.327777777777778in"
height="1.7583333333333333in"}

Click **Submit Kik Credentials**.

**Enable the bot**
------------------

Check **Enable this bot on Kik**. Then click **I\'m done configuring
Kik**.

When you have completed these steps, your bot will be successfully
configured to communicate with users in Kik.

Connect a bot to Slack
======================

You can configure your bot to communicate with people using the Slack
messaging app.

**Create a Slack Application for your bot**
-------------------------------------------

Log into Slack and [create a Slack
application](https://api.slack.com/applications/new).

![Set up bot](media/image88.png){width="6.2243055555555555in"
height="0.5861111111111111in"}

**Create an app and assign a Development Slack team**
-----------------------------------------------------

Enter an App Name and select a Development Slack Team. If you are not
already a member of a Development Slack Team, [create or join
one](https://slack.com/).

![Create app](media/image89.png){width="6.0in"
height="4.8277777777777775in"}

Click **Create App**. Slack will create your app and generate a Client
ID and Client Secret.

**Add a new Redirect URL**
--------------------------

Next you will add a new Redirect URL.

1.  Select the **OAuth & Permissions** tab.

2.  Click **Add a new Redirect URL**.

3.  Enter [https://slack.botframework.com](https://slack.botframework.com/).

4.  Click **Add**.

5.  Click **Save URLs**.

![Add Redirect URL](media/image90.png){width="8.206944444444444in"
height="5.120833333333334in"}

**Create a Slack Bot User**
---------------------------

Adding a Bot User allows you to assign a username for your bot and
choose whether it is always shown as online.

1.  Select the **Bot Users** tab.

2.  Click **Add a Bot User**.

![Create bot](media/image91.png){width="8.206944444444444in"
height="3.7756944444444445in"}

Click **Add Bot User** to validate your settings, click **Always Show My
Bot as Online** to **On**, and then click **Save Changes**.

![Create bot](media/image92.png){width="8.206944444444444in"
height="4.1722222222222225in"}

**Subscribe to Bot Events**
---------------------------

Follow these steps to subscribe to six particular bot events. By
subscribing to bot events, your app will be notified of user activities
at the URL you specify.

Tip

Your bot handle is a property of your bot. To find a bot\'s handle,
visit <https://dev.botframework.com/bots>, choose a bot, and
click **SETTINGS**.

1.  Select the **Event Subscriptions** tab.

2.  Click **Enable Events** to **On**.

3.  In **Request URL**, enter this URL, but replace {YourBotHandle} with
    > your bot
    > handle.https://slack.botframework.com/api/Events/{YourBotHandle}

4.  In **Subscribe to Bot Events**, click **Add Bot User Event**.

5.  In the list of events, click Add **Bot User Event** and select these
    > six event types:

    -   member\_joined\_channel

    -   member\_left\_channel

    -   message.channels

    -   message.groups

    -   message.im

    -   message.mpim

<!-- -->

1.  Click **Save Changes**.

![Subscribe to Events](media/image93.png){width="8.120833333333334in"
height="3.2243055555555555in"}

**Add and Configure Interactive Messages (optional)**
-----------------------------------------------------

If your bot will use Slack-specific functionality such as buttons,
follow these steps:

1.  Select the **Interactive Components** tab and click **Enable
    > Interactive Components**.

2.  Enter https://slack.botframework.com/api/Actions as the **Request
    > URL**.

3.  Click the **Enable Interactive Messages** button, and then click
    > the **Save changes** button.

![Enable messages](media/image94.png){width="8.206944444444444in"
height="4.154861111111111in"}

**Gather credentials**
----------------------

Select the **Basic Information** tab and scroll to the **App
Credentials** section. The Client ID, Client Secret, and Verification
Token required for configuration of your Slack bot are displayed.

![Gather credentials](media/image95.png){width="8.206944444444444in"
height="4.017361111111111in"}

**Submit credentials**
----------------------

In a separate browser window, return to the Bot Framework site
at https://dev.botframework.com/.

1.  Select **My bots** and choose the Bot that you want to connect to
    > Slack.

2.  In the **Add a channel** section, click the Slack icon.

3.  In the **Enter your Slack credentials** section, paste the App
    > Credentials from the Slack website into the appropriate fields.

4.  The **Landing Page URL** is optional. You may omit or change it.

5.  Click **Save**.

![Submit credentials](media/image96.png){width="6.982638888888889in"
height="3.448611111111111in"}

Follow the instructions to authorize your Slack app\'s access to your
Development Slack Team.

**Enable the bot**
------------------

On the Configure Slack page, confirm the slider by the Save button is
set to **Enabled**. Your bot is configured to communicate with users in
Slack.

**Create an Add to Slack button**
---------------------------------

Slack provides HTML you can use to help Slack users find your bot in
the *Add the Slack button*section of [this
page](https://api.slack.com/docs/slack-button). To use this HTML with
your bot, replace the href value (begins with https://) with the URL
found your bot\'s Slack channel settings. Follow these steps to get the
replacement URL.

1.  On <https://dev.botframework.com/bots>, click your bot.

2.  Click **CHANNELS**, right-click the entry named **Slack**, and
    > click **Copy link**. This URL is now in your clipboard.

3.  Paste this URL from your clipboard into the HTML provided for the
    > Slack button. This URL replaces the href value provided by Slack
    > for this bot.

Authorized users can click the **Add to Slack** button provided by this
modified HTML to reach your bot on Slack.

Connect a bot to Telegram
=========================

You can configure your bot to communicate with people using the Telegram
messaging app.

Tip

To see how various Bot Framework features look and work on this
channel, [use the Channel
Inspector](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-inspector).

**Visit the Bot Father to create a new Telegram bot**
-----------------------------------------------------

[Create a new Telegram bot](https://telegram.me/botfather) using the Bot
Father.

![Visit Bot Father](media/image97.png){width="11.775694444444444in"
height="10.0in"}

**Create a new Telegram bot**
-----------------------------

To create a new Telegram bot, send command /newbot.

![Create new bot](media/image98.png){width="11.775694444444444in"
height="10.0in"}

### **Specify a friendly name**

Give the Telegram bot a friendly name.

![Give bot a friendly
name](media/image99.png){width="11.775694444444444in" height="10.0in"}

### **Specify a username**

Give the Telegram bot a unique username.

![Give bot a unique
name](media/image100.png){width="11.775694444444444in" height="10.0in"}

### **Copy the access token**

Copy the Telegram bot\'s access token.

![Copy access token](media/image101.png){width="7.776019247594051in"
height="6.603448162729658in"}

**Enter the Telegram bot\'s access token**
------------------------------------------

Paste the token you copied previously into the **Access Token** field
and click **Submit**.

**Enable the bot**
------------------

Check **Enable this bot on Telegram**. Then click **I\'m done
configuring Telegram**.

When you have completed these steps, your bot will be successfully
configured to communicate with users in Telegram.

Connect a bot to Twilio
=======================

You can configure your bot to communicate with people using the Twilio
cloud communication platform.

**Log in to or create a Twilio account for sending and receiving SMS messages**
-------------------------------------------------------------------------------

If you don\'t have a Twilio account, [create a new
account](https://www.twilio.com/try-twilio)

**Create a TwiML Application**
------------------------------

[Create a TwiML
application](https://www.twilio.com/user/account/messaging/dev-tools/twiml-apps/add)

![Create app](media/image102.png){width="17.15486111111111in"
height="10.275694444444444in"}

Under Messaging, the Request URL should
be [**https://sms.botframework.com/api/sms**](https://sms.botframework.com/api/sms).

**Select or add a phone number**
--------------------------------

[Select or add a phone
number](https://www.twilio.com/user/account/phone-numbers/incoming).
Click the number to add it to the TwiML application you created.

![Set phone number](media/image103.png){width="10.58611111111111in"
height="2.7243055555555555in"}

**Specify application to use for Messaging**
--------------------------------------------

In the **Messaging** section, set the **TwiML App** to the name of the
TwiML App you just created. Copy the **Phone Number** value for later
use.

![Specify app](media/image104.png){width="10.741666666666667in"
height="9.293055555555556in"}

**Gather credentials**
----------------------

[Gather credentials](https://www.twilio.com/user/account/settings) and
then click the \"eye\" icon to see the Auth Token.

![Gather app credentials](media/image105.png){width="9.91388888888889in"
height="7.017361111111111in"}

**Submit credentials**
----------------------

Enter the phone number, accountSID, and Auth Token you copied earlier
and click **Submit Twilio Credentials**.

**Enable the bot**
------------------

Check **Enable this bot on SMS**. Then click **I\'m done configuring
SMS**.

When you have completed these steps, your bot will be successfully
configured to communicate with users using Twilio.

Preview bot features with the Channel Inspector
===============================================

The Bot Framework enables you to create bots with a variety of features
such as text, buttons, images, rich cards displayed in carousel or list
format, and more. However, each channel ultimately controls how features
are rendered by its messaging clients.

Even when a feature is supported by multiple channels, each channel may
render the feature in a slightly different way. In cases where a message
contains feature(s) that a channel does not natively support, the
channel may attempt to down-render message contents as text or as a
static image, which can significantly impact the message\'s appearance
on the client. In some cases, a channel may not support a particular
feature at all. For example, GroupMe clients cannot display a typing
indicator.

**The Channel Inspector**
-------------------------

The [Channel
Inspector](https://docs.botframework.com/en-us/bot-service-channel-inspector/channels/Skype/) is
created to give you a preview on how various Bot Framework features look
and work on different channels. By understanding how features are
rendered by various channels, you\'ll be able to design your bot to
deliver an exceptional user experience on the channels where it
communicates. The Channel Inspector also provides a great way to learn
about and visually explore Bot Framework features.1

Note

Rich cards are a developing standard for bot information exchange to
ensure consistent display across multiple channels. See
the [.NET](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments) or [Node.js](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards) documentation
for more information about rich cards.

**Text formatting**
-------------------

Text formatting can enhance your text messages visually.
Besides **plain** text, your bot can send text messages
using **markdown** or **xml** formatting to channels that support them.
The following tables list some of the most commonly used text formatting
in **markdown** and **xml**. Each channel may support fewer or more text
formatting then what is listed here. You can check the [Channel
Inspector](https://docs.botframework.com/en-us/bot-service-channel-inspector/channels/Skype/) to
see if a feature you want to use is supported on a channel that you
target.

### **Markdown text format**

These styles may be supported when textFormat is set to **markdown**:

+-----------------------+-----------------------+-----------------------+
| Style                 | Markdown              | Example               |
+=======================+=======================+=======================+
| bold                  | \*\*text\*\*          | **text**              |
+-----------------------+-----------------------+-----------------------+
| italic                | \*text\*              | *text*                |
+-----------------------+-----------------------+-----------------------+
| header (1-5)          | \# H1                 | \# H1                 |
+-----------------------+-----------------------+-----------------------+
| strikethrough         | \~\~text\~\~          |                       |
+-----------------------+-----------------------+-----------------------+
| horizontal rule       | \-\-\--               | \-\-\--               |
+-----------------------+-----------------------+-----------------------+
| unordered list        | \* text               | -   text              |
+-----------------------+-----------------------+-----------------------+
| ordered list          | 1\. text              | 1\. text              |
+-----------------------+-----------------------+-----------------------+
| preformatted text     | \`text\`              | text                  |
+-----------------------+-----------------------+-----------------------+
| blockquote            | \> text               | text                  |
+-----------------------+-----------------------+-----------------------+
| hyperlink             | \[bing\]([http://www. | [bing](http://www.bin |
|                       | bing.com](http://www. | g.com/)               |
|                       | bing.com/))           |                       |
+-----------------------+-----------------------+-----------------------+
| image link            | !\[duck\](<http://aka | ![duck](media/image10 |
|                       | .ms/Fo983c>)          | 6.jpeg){width="2.3277 |
|                       |                       | 77777777778in"        |
|                       |                       | height="1.56875in"}   |
+-----------------------+-----------------------+-----------------------+

Note

HTML tags in **Markdown** are not supported in Microsoft Bot Framework
Web Chat channels. If you need to use HTML tags in your **Markdown**,
you can render them in a [Direct
Line](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-directline) channel
that supports them. Alternatively, you can use the HTML tags below by
setting the textFormat to **xml** and connect your bot to Skype channel.

### **XML text format**

These styles may be supported when textFormat is set to **xml**:

+-----------------------+-----------------------+-----------------------+
| Style                 | XML                   | Example               |
+=======================+=======================+=======================+
| bold                  | \<b\>text\</b\>       | **text**              |
+-----------------------+-----------------------+-----------------------+
| italic                | \<i\>text\</i\>       | *text*                |
+-----------------------+-----------------------+-----------------------+
| underline             | \<u\>text\</u\>       | [text]{.underline}    |
+-----------------------+-----------------------+-----------------------+
| strikethrough         | \<s\>text\</s\>       | ~~text~~              |
+-----------------------+-----------------------+-----------------------+
| hyperlink             | \<a                   | [bing](http://www.bin |
|                       | href=\"http://www.bin | g.com/)               |
|                       | g.com\"\>bing\</a\>   |                       |
+-----------------------+-----------------------+-----------------------+
| paragraph             | \<p\>text\</p\>       | text                  |
+-----------------------+-----------------------+-----------------------+
| line break            | \<br/\>               | line 1 \              |
|                       |                       | line 2                |
+-----------------------+-----------------------+-----------------------+
| horizontal rule       | \<hr/\>               |                       |
+-----------------------+-----------------------+-----------------------+
| header (1-4)          | \<h1\>text\</h1\>     | Heading 1 {#heading-1 |
|                       |                       | }                     |
|                       |                       | =========             |
+-----------------------+-----------------------+-----------------------+
| code                  | \<code\>code          | code block            |
|                       | block\</code\>        |                       |
+-----------------------+-----------------------+-----------------------+
| image                 | \<img                 | ![Duck](media/image10 |
|                       | src=\"<http://aka.ms/ | 6.jpeg){width="2.3277 |
|                       | Fo983c>\"             | 77777777778in"        |
|                       | alt=\"Duck\"\>        | height="1.56875in"}   |
+-----------------------+-----------------------+-----------------------+

Note

The textFormat **xml** is supported only by the Skype channel.

**Preview features across various channels**
--------------------------------------------

To see how a channel renders a particular feature, go to the [Channel
Inspector](https://docs.botframework.com/en-us/bot-service-channel-inspector/channels/Skype/),
select the channel from **Channel** list and the feature from
the **Feature** list. For example, to see how Skype renders a Hero Card,
set **Channel** to *Skype* and **Feature** to *HeroCard*.

![Channel Inspector showing Skype channel and Hero
Card](media/image107.png){width="8.189583333333333in"
height="5.965277777777778in"}

The Channel Inspector shows a preview of the selected feature as it will
be rendered by the specified channel. The **Notes** section conveys
important information about message limitations and/or display changes.
For example, some types of rich cards support only one image and some
features may be down-rendered on certain channels.

Note

The Channel Inspector currently supports these channels:

-   Cortana

-   Email

-   Facebook

-   GroupMe

-   Kik

-   Skype

-   Skype for Business

-   Slack

-   SMS

-   Microsoft Teams

-   Telegram

-   WeChat

-   Web Chat

Additional channels may be added in the future.

**Features that can be previewed**
----------------------------------

The Channel Inspector currently allows you to preview the following
features.

  Feature             Description
  ------------------- --------------------------------------------------------------------------------------------------------------------------------------------------
  Adaptive Cards      A card that can contain any combination of text, speech, images, buttons, and input fields.
  Buttons             Buttons that the user can click. Buttons appear on the conversation canvas with the message they belong to.
  Carousel            A compact, scrollable horizontal list of cards. For a vertical layout, use List.
  ChannelData         A way to pass metadata to access channel-specific functionality beyond cards, text, and attachments.
  Codesample          A multi-line, pre-formatted block of text designed to display computer code.
  DirectMessage       A message sent to a single member of a group conversation.
  Document            Send and receive non-media attachments.
  Emoji               Display supported emoji.
  GroupChat           Bot sends messages to participate in group conversations.
  HeroCard            A formatted attachment typically containing a single large image, a tap action, and buttons (optional), along with descriptive text content.
  Images              Display of image attachments.
  List Layout         A vertical list of cards. For a horizontal, scrollable layout, use Carousel.
  Location            Share the user\'s physical location with the bot.
  Markdown            Renders text formatted with Markdown.
  Members             Shares the list of members in the conversation with the bot during a group chat.
  Receipt Card        Display a receipt to the user.
  Signin Card         Request the user to enter authentication credentials.
  Suggested Actions   Actions presented as buttons that the user can tap to provide input.
  Thumbnail Card      A formatted attachment containing a single small image (thumbnail), a tap action, and buttons (optional), along with descriptive text content.
  Typing              Displays a typing indicator. This is helpful to inform the user that the bot is still functioning, but performing some action in the background.
  Video               Displays video attachments and play controls.

Configure bot settings
======================

The bot settings, such as Display name, Icon, and Application Insights,
can be viewed and modified on its **Settings** blade.

![The bot settings
blade](media/image108.png){width="8.327777777777778in"
height="7.258333333333334in"}

Below is the list of fields on the **Settings** blade:

  Field                                      Description
  ------------------------------------------ -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Icon                                       A custom icon to visually identify your bot in channels and as the icon for Skype, Web Chat, and other services. This icon must be in PNG format, and no larger than 30K in size. This value can be changed at any time.
  Display name                               The name of your bot in channels and directories. This value can be changed at any time. 35 character limit.
  Bot handle                                 Unique idenifier for your bot. This value cannot be changed after creating your bot with the Bot Service.
  Messaging endpoint                         The endpoint to communicate with your bot.
  Microsoft App ID                           Unique identifier for your bot. This value cannot be changed. You can generate a new password by clicking on the **Manage** link.
  Application Insights Instrumentation key   Unique key for bot telemetry. Copy your Azure Application Insights Key to this field if you want to receive bot telemetry for this bot. This value is optional. Bots created in the Azure Portal will have this key generated for them. For more details on this field, see [[Application Insights keys]{.underline}](https://docs.microsoft.com/en-us/bot-framework/bot-service-resources-app-insights-keys).
  Application Insights API key               Unique key for bot analytics. Copy your Azure Application Insights API Key to this field if you want to view analytics about your bot in the Dashboard. This value is optional. For more details on this field, see [[Application Insights keys]{.underline}](https://docs.microsoft.com/en-us/bot-framework/bot-service-resources-app-insights-keys).
  Application Insights Application ID        Unique key for bot analytics. Copy your Azure Insights Application ID Key to this field if you want to view analytics about your bot in the Dashboard. This value is optional. Bots created in the Azure Portal will have this key generated for them. For more details on this field, see [[Application Insights keys]{.underline}](https://docs.microsoft.com/en-us/bot-framework/bot-service-resources-app-insights-keys).

Note

After you have changed settings for your bot, click the **Save** button
at the top of the blade to save your new bot settings.

Configure speech priming
========================

Speech priming improves the recognition of spoken words and phrases that
are commonly used in your bot. For speech-enabled bots that use the Web
Chat and Cortana channels, speech priming uses examples specified in
Language Understanding (LUIS) apps to improve speech recognition
accuracy for important words.

Your bot may already be integrated with a LUIS app, or you can choose to
create a LUIS app to associate with your bot for speech priming. The
LUIS app contains examples of what you expect users to say to your bot.
Important words that you want the bot to recognize should be labeled as
entities. For example, in a chess bot you want to make sure that when
the user says \"Move knight\", it isn't interpreted as \"Move night\".
The LUIS app should include examples in which \"knight\" is labeled as
an entity.

Note

To use speech priming with the Web Chat channel, you must use the Bing
Speech service. See [Enable speech in the Web Chat
channel](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-webchat-speech) for
an explanation of how to use the Bing Speech service.

Important

Speech priming only applies to bots configured for the Cortana channel
or the Web Chat channel.

**Change the list of LUIS apps your bot uses**
----------------------------------------------

To change the list of LUIS apps used by Bing Speech with your bot, do
the following:

1.  Click **Speech priming** on the bot service blade. The list of LUIS
    > apps available to you will appear.

2.  Select the LUIS apps you want Bing Speech to use.

> a\. To select a LUIS app in the list, hover over the LUIS model until a
> checkbox appears, then check the checkbox.
>
> b\. To select a LUIS app that is not on the list, scroll to the bottom
> and enter the LUIS Application ID GUID into the text box.

3.  Click **Save** to save the list of LUIS apps associated with Bing
    > Speech for your bot.

![The speech priming
panel](media/image109.png){width="7.810416666666667in"
height="4.482638888888889in"}

**Additional Resources**
------------------------

-   To learn more enabling speech in Web Chat see [Enable speech in the
    > Web Chat
    > channel](https://docs.microsoft.com/en-us/bot-framework/bot-service-channel-connect-webchat-speech).

-   To learn more about speech priming, see [Speech Support in Bot
    > Framework -- Web Chat to Directline, to
    > Cortana](https://blog.botframework.com/2017/06/26/Speech-To-Text/).

-   To learn more about LUIS apps, see [Language Understanding
    > Intelligent Service](https://www.luis.ai/).

Migrate your bot to Azure
=========================

All **Azure Bot Service (Preview)** bots created in the [Bot Framework
Portal](http://dev.botframework.com/) must migrate to the new Bot
Service in Azure by 3/31/2018.

Note

Migration is currently enabled for registration bot types only.
Migration for SDK bots and Functions bots will be coming soon.

To migrate your bot, do the following:

1.  Sign into the [Bot Framework
    > Portal](http://dev.botframework.com/) and click **My bots**.

2.  Click **Migrate** button for the bot you want to migrate.

> Note
>
> Before migrating a Functions bot using Node.js, it is recommended that
> you use the *Azure Functions Pack* to package the Node.js modules
> together. Doing so will improve performance during migration and
> execution of the Functions bot after it is migrated. For more
> information about, see [Azure Functions
> Pack](https://github.com/Azure/azure-functions-pack).

3.  Accept the **Terms** and click **Migrate** to start the migration
    > process or click **Cancel** to cancel this action.

Important

While the migration task is in progress, do not navigate away from the
page or refresh the page. Doing so will cause the migration task to stop
pre-maturely and you will have to perform the action again. To ensure
the migration completes successfully, wait for the confirmation message.

After the migration process complete successfully, the **Migration
status** will indicate that the bot is migrated and a **Roll back
migration** button is available if you need to undo the migration.

Clicking the name of a migrated bot will open the bot in the [Azure
portal](http://portal.azure.com/).

**Migration under the hood**
----------------------------

Depending on the type of bot you are migrating, the list below can help
you better understand what is happening under the hood.

-   **Web App Bot** or **Functions Bot**: For these types of bots, the
    > source code project is copied from the old bot to the new bot.
    > Other resources such as your bot\'s storage, Application Insights,
    > LUIS, etc. are left as is. In those cases, the new bot contains a
    > copy of the IDs/keys/passwords to those existing resources.

-   **Bot Channels Registration**: For this type of bots, the migration
    > process simply create a new **Bot Channels Registration** and copy
    > the endpoint from the old bot over.

-   Regardless of the types of bot you are migrating, the migration
    > process does not modify the existing bot\'s state in anyway. This
    > allows you to safely roll back if you need to do so.

-   If you have [continuous
    > deployment](https://docs.microsoft.com/en-us/bot-framework/bot-service-build-continuous-deployment) set
    > up, you will need to set it up again so that your source control
    > connects to the new bot instead.

**Roll back migration**
-----------------------

In the event something went wrong with the bot during migration or after
it is migrated, you can **Roll back migration**. To roll back a
migration, do the following:

1.  Sign into the [Bot Framework
    > Portal](http://dev.botframework.com/) and click **My bots**.

2.  Click **Roll back migration** button for the bot you want to roll
    > back. A prompt will appear.

3.  Click **Yes, roll back** to proceed or **Cancel** to cancel the roll
    > back action.

Note

Roll back functionality for registration bots is coming soon.

Bot Builder SDK for .NET
========================

The Bot Builder SDK for .NET is a powerful framework for constructing
bots that can handle both free-form interactions and more guided
conversations where the user selects from possible values. It is easy to
use and leverages C\# to provide a familiar way for .NET developers to
write bots.

Using the SDK, you can build bots that take advantage of the following
SDK features:

-   Powerful dialog system with dialogs that are isolated and composable

-   Built-in prompts for simple things such as Yes/No, strings, numbers,
    > and enumerations

-   Built-in dialogs that utilize powerful AI frameworks such
    > as [LUIS](http://luis.ai/)

-   FormFlow for automatically generating a bot (from a C\# class) that
    > guides the user through the conversation, providing help,
    > navigation, clarification, and confirmation as needed

Important

On July 31, 2017 breaking changes will be implemented in the Bot
Framework security protocol. To prevent these changes from adversely
impacting your bot, you must ensure that your application is using Bot
Builder SDK v3.5 or greater. If you\'ve built a bot using an SDK that
you obtained prior to January 5, 2017 (the release date for Bot Builder
SDK v3.5), be sure to upgrade to Bot Builder SDK v3.5 or later before
July 31, 2017.

**Get the SDK**
---------------

The SDK is available as a NuGet package and as open source
on [GitHub](https://github.com/Microsoft/BotBuilder).

Important

The Bot Builder SDK for .NET requires .NET Framework 4.6 or newer. If
you are adding the SDK to an existing project targeting a lower version
of the .NET Framework, you will need to update your project to target
.NET Framework 4.6 first.

To install the SDK within a Visual Studio project, complete the
following steps:

1.  In **Solution Explorer**, right-click the project name and
    > select **Manage NuGet Packages\...**.

2.  On the **Browse** tab, type \"Microsoft.Bot.Builder\" into the
    > search box.

3.  Select **Microsoft.Bot.Builder** in the list of results,
    > click **Install**, and accept the changes.

**Get code samples**
--------------------

This SDK includes [sample source
code](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-samples) that
uses the features of the Bot Builder SDK for .NET.

Bot Builder SDK for Node.js
===========================

Bot Builder SDK for Node.js is a powerful, easy-to-use framework that
provides a familiar way for Node.js developers to write bots. You can
use it to build a wide variety of conversational user interfaces, from
simple prompts to free-form conversations.

The conversational logic for your bot is hosted as a web service. The
Bot Builder SDK uses [restify](http://restify.com/), a popular framework
for building web services, to create the bot\'s web server. The SDK is
also compatible with [Express](http://expressjs.com/) and the use of
other web app frameworks is possible with some adaption.

Using the SDK, you can take advantage of the following SDK features:

-   Powerful system for building dialogs to encapsulate conversational
    > logic.

-   Built-in prompts for simple things such as Yes/No, strings, numbers,
    > and enumerations, as well as support for messages containing
    > images and attachments, and rich cards containing buttons.

-   Built-in support for powerful AI frameworks such
    > as [LUIS](http://luis.ai/).

-   Built-in recognizers and event handlers that guide the user through
    > the conversation, providing help, navigation, clarification, and
    > confirmation as needed.

**Get started**
---------------

If you are new to writing bots, [create your first bot with
Node.js](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-quickstart) with
step-by-step instructions to help you set up your project, install the
SDK, and run your first bot.

If you are new to the Bot Builder SDK for Node.js, you can start with
key concepts that help you understand the major components of the Bot
Builder SDK, see [Key
concepts](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-concepts).

To ensure your bot addresses the top user scenarios, review the [design
principles](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-principles) and [explore
patterns](https://docs.microsoft.com/en-us/bot-framework/bot-service-design-pattern-task-automation) for
guidance.

**Get samples**
---------------

The [Bot Builder SDK for Node.js
samples](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-samples) demonstrate
task-focused bots that show how to take advantage of features in the Bot
Builder SDK for Node.js. You can use the samples to help you quickly get
started with building great bots with rich capabilities.

Bot Framework REST APIs
=======================

The Bot Framework REST APIs enable you to build bots that exchange
messages with channels configured in the [Bot Framework
Portal](https://dev.botframework.com/), store and retrieve state data,
and connect your own client applications to your bots. All Bot Framework
services use industry-standard REST and JSON over HTTPS.

**Build a bot**
---------------

You can create a bot with any programming language by using the Bot
Connector service to exchange messages with channels configured in the
Bot Framework Portal.

Tip

The Bot Framework provides client libraries that can be used to build
bots in either C\# or Node.js. To build a bot using C\#, use the [Bot
Builder SDK for
C\#](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-overview).
To build a bot using Node.js, use the [Bot Builder SDK for
Node.js](https://docs.microsoft.com/en-us/bot-framework/nodejs/index).

To learn more about building bots using the Bot Connector service,
see [Key
concepts](https://docs.microsoft.com/en-us/bot-framework/rest-api/bot-framework-rest-connector-concepts).

**Build a client**
------------------

You can enable your own client application to communicate with your bot
by using the Direct Line API. The Direct Line API implements an
authentication mechanism that uses standard secret/token patterns and
provides a stable schema, even if your bot changes its protocol version.
To learn more about using the Direct Line API to enable communication
between a client and your bot, see [Key
concepts](https://docs.microsoft.com/en-us/bot-framework/rest-api/bot-framework-rest-direct-line-3-0-concepts).

Debug a Bot Service bot
=======================

Bot Service bots are built as Azure App Service web apps, or as code
running in a Consumption plan upon the Azure Functions serverless
architecture. This article describes how to debug your bot after you
have set up a publishing process. By downloading a zip file that
contains your bot source, you can develop and debug using an integrated
development environment (IDE) such as Visual Studio or Visual Studio
Code. From your computer, you can update your bot on Bot Service by
publishing from Visual Studio, or by publishing with every check-in to
your source control service through continuous deployment.

**Publish any bot source using continuous deployment**
------------------------------------------------------

You can publish bot source to Azure using continuous deployment. To set
up continuous deployment, [follow these
steps](https://docs.microsoft.com/en-us/bot-framework/bot-service-continuous-deployment) before
proceeding.

**Debug a Node.js bot**
-----------------------

Follow steps in this section to debug a bot written in Node.js.

### **Prerequisites**

Before you can debug your Node.js bot, you must complete these tasks.

-   Download the source code for your bot (from Azure), as described
    > in [Set up continuous
    > deployment](https://docs.microsoft.com/en-us/bot-framework/bot-service-continuous-deployment).

-   Download and install the [Bot Framework
    > Emulator](https://docs.microsoft.com/en-us/bot-framework/bot-service-debug-emulator).

-   Download and install a code editor such as [Visual Studio
    > Code](https://code.visualstudio.com/).

### **Debug a Node.js bot using the Bot Framework Emulator**

The simplest way to debug your bot locally is to start the bot in Node
and then connect to it from Bot Framework Emulator. First, you must set
the NODE\_ENV environment variable. This screenshot shows how to set
the NODE\_ENV environment variable and start the bot.

![run bot](media/image110.png){width="18.43125in"
height="12.224305555555556in"}

At this point, the bot is running locally. Copy the bot\'s endpoint from
the terminal window (in this
example, http://localhost:3978/api/messages), start the Bot Framework
Emulator, and paste the endpoint into the address bar of the emulator.
Since you do not need security for local debugging, you can leave
the **Microsoft App ID** and **Microsoft App Password** fields blank.
Click **Connect** to establish a connection to your bot using the
specified endpoint.

![configure emulator](media/image111.png){width="15.0in"
height="8.43125in"}

After you have connected the emulator to your bot, send a message to
your bot by typing some text into the textbox that is located at the
bottom of the emulator window (i.e., where **Type your
message\...** appears in the lower-left corner). By using
the **Log** and **Inspector** panels on the right side of the emulator
window, you can view the requests and responses as messages are
exchanged between the emulator and the bot.

![test via emulator](media/image112.png){width="15.0in"
height="8.43125in"}

Additionally, you can view log details from the Node runtime in the
terminal window.

![terminal window](media/image113.png){width="18.43125in"
height="12.224305555555556in"}

### **Debug a Node.js bot using breakpoints in Visual Studio Code**

If you need more than logs and request / response traces to debug your
bot, you can use a local IDE such as Visual Studio Code to debug your
code using breakpoints. Using VS Code to debug your bot can be
beneficial because you can make changes locally within the editor while
you are debugging, and when you push changes to the remote repository,
those changes will automatically be applied to your bot in the cloud
(since you have enabled continuous deployment).

First, launch VS Code and open the local folder where the source code
for your bot is located.

![open VS Code](media/image114.png){width="15.0in" height="8.43125in"}

Switch to the debugging view, and click **run**. If you are prompted to
select a runtime engine to run your code, select Node.js.

![VS Code debugging view](media/image115.png){width="30.0in"
height="16.861805555555556in"}

Next, depending on whether you have synced the repository or modified
files, you may be prompted to configure the **launch.json** file. If you
are prompted, add the env configuration setting to
the **launch.json** file (to tell the template that you are going to
work with the emulator).

JSONCopy

\"env\": {

\"NODE\\\_ENV\": \"development\"

}

![VS Code debugging view](media/image116.png){width="15.0in"
height="8.293055555555556in"}

Save your changes to the **launch.json** file and click **run** again.
Your bot should now be running in the VS Code environment with Node. You
can open the debug console to see logging output and set breakpoints as
needed.

![VS Code set breakpoints](media/image117.png){width="15.0in"
height="8.293055555555556in"}

At this point, the bot is running locally. Copy the bot\'s endpoint from
the debug console in VS Code, start the Bot Framework Emulator, and
paste the endpoint into the address bar of the emulator. Since you do
not need security for local debugging, you can leave the **Microsoft App
ID** and **Microsoft App Password** fields blank. Click **Connect** to
establish a connection to your bot using the specified endpoint.

After you have connected the emulator to your bot, send a message to
your bot by typing some text into the textbox that is located at the
bottom of the emulator window (i.e., where **Type your
message\...** appears in the lower-left corner). As messages are
exchanged between the emulator and the bot, you should hit the
breakpoints that you set in VS Code.

![Debug in VS Code](media/image118.png){width="15.0in"
height="8.293055555555556in"}

**Debug an Azure App Service web app C\# bot**
----------------------------------------------

You can debug a C\# bot Bot Service web app locally in Visual Studio.

### **Prerequisites**

Before you can debug your web app C\# bot, you must complete these
tasks.

-   Download and install the [Bot Framework Channel
    > Emulator](https://docs.microsoft.com/en-us/bot-framework/bot-service-debug-emulator).

-   Download and install [Visual Studio
    > 2017](https://www.visualstudio.com/downloads/) (Community Edition
    > or above).

### **Get and debug your source code**

Follow these steps to download your C\# bot source.

1.  In the Azure Portal, click your Bot Service, click
    > the **BUILD** tab, and click **Download zip file**.

2.  Extract the contents of the downloaded zip file to a local folder.

3.  In Explorer, double-click the .sln file.

4.  Click **Debug**, and click **Start Debugging**. Your
    > bot\'s default.htm page appears. Note the address in the location
    > bar.

5.  In the Bot Framework Channel Emulator, click the blue location bar,
    > and enter an address similar
    > to http://localhost:3984/api/messages. Your port number might be
    > different.

You are now debugging locally. You can simulate user activity in the
emulator, and set breakpoints on your code in Visual Studio. You can
then [re-publish your bot to
Azure](https://docs.microsoft.com/en-us/bot-framework/bot-service-continuous-deployment).

**Debug a Consumption plan C\# script bot**
-------------------------------------------

The Consumption plan serverless C\# environment in Bot Service has more
in common with Node.js than a typical C\# application because it
requires a runtime host, much like the Node engine. In Azure, the
runtime is part of the hosting environment in the cloud, but you must
replicate that environment locally on your desktop.

### **Prerequisites**

Before you can debug your Consumption plan C\# bot, you must complete
these tasks.

-   Download the source code for your bot (from Azure), as described
    > in [Set up continuous
    > deployment](https://docs.microsoft.com/en-us/bot-framework/bot-service-continuous-deployment).

-   Download and install the [Bot Framework
    > Emulator](https://docs.microsoft.com/en-us/bot-framework/bot-service-debug-emulator).

-   Install the [Azure Functions
    > CLI](https://www.npmjs.com/package/azure-functions-cli).

-   Install the DotNet CLI.

If you want to be able to debug your code by using breakpoints in Visual
Studio 2017, you must also complete these tasks.

-   Download and install [Visual Studio
    > 2017](https://www.visualstudio.com/downloads/) (Community Edition
    > or above).

-   Download and install the [Command Task Runner Visual Studio
    > Extension](https://visualstudiogallery.msdn.microsoft.com/e6bf6a3d-7411-4494-8a1e-28c1a8c4ce99).

Note

Visual Studio Code is not currently supported.

### **Debug a Consumption plan C\# script bot using the Bot Framework Emulator**

The simplest way to debug your bot locally is to start the bot and then
connect to it from Bot Framework Emulator. First, open a command prompt
and navigate to the folder where the **project.json** file is located in
your repository. Then, run the command dotnet restore to restore the
various packages that are referenced in your bot.

Note

Visual Studio 2017 changes how Visual Studio handles dependencies. While
Visual Studio 2015 uses **project.json** to handle dependencies, Visual
Studio 2017 uses a **.csproj** model when loading in Visual Studio. If
you are using Visual Studio 2017, [download
this **[.csproj]{.underline}**file](https://aka.ms/bf-debug-project) to
the **/messages** folder in your repository before you run the dotnet
restorecommand.

![Command prompt](media/image119.png){width="8.276173447069116in"
height="5.08965113735783in"}

Next, run debughost.cmd to load and start your bot.

![Command prompt run
debughost.cmd](media/image120.png){width="9.083689851268591in"
height="5.586254374453193in"}

At this point, the bot is running locally. From the console window, copy
the endpoint that debughost is listening on (in this
example, http://localhost:3978). Then, start the Bot Framework Emulator
and paste the endpoint into the address bar of the emulator. For this
example, you must also append /api/messages to the endpoint. Since you
do not need security for local debugging, you can leave the **Microsoft
App ID** and **Microsoft App Password** fields blank.
Click **Connect** to establish a connection to your bot using the
specified endpoint.

![Configure emulator](media/image111.png){width="10.568965441819772in"
height="5.940639763779528in"}

After you have connected the emulator to your bot, send a message to
your bot by typing some text into the textbox that is located at the
bottom of the emulator window (i.e., where **Type your
message\...** appears in the lower-left corner). By using
the **Log** and **Inspector** panels on the right side of the emulator
window, you can view the requests and responses as messages are
exchanged between the emulator and the bot.

![test via emulator](media/image112.png){width="8.586207349081365in"
height="4.826163604549431in"}

Additionally, you can view log details the console window.

![Console window](media/image121.png){width="6.276173447069116in"
height="3.859698162729659in"}

### **Debug a Consumption plan C\# bot using breakpoints in Visual Studio**

To debug your bot using breakpoints in Visual Studio 2017, stop
the **DebugHost.cmd** script, and load the solution for your project
(included as part of the repository) in Visual Studio. Then,
click **Task Runner Explorer** at the bottom of the Visual Studio
window.

![Visual Studio Task Runner
Explorer](media/image122.png){width="9.793222878390202in"
height="7.168392388451443in"}

You will see the bot loading in the debug host environment in the **Task
Runner Explorer**window. Your bot is now running locally. Copy the
bot\'s endpoint from the **Task Runner Explorer** window, start the Bot
Framework Emulator, and paste the endpoint into the address bar of the
emulator. For this example, you must also append /api/messages to the
endpoint. Since you do not need security for local debugging, you can
leave the **Microsoft App Id** and **Microsoft App Password** fields
blank. Click **Connect** to establish a connection to your bot using the
specified endpoint.

After you have connected the emulator to your bot, send a message to
your bot by typing some text into the textbox that is located at the
bottom of the emulator window (i.e., where **Type your
message\...** appears in the lower-left corner). As messages are
exchanged between the emulator and the bot, you will see the responses
as well as logged output within **Task Runner Explorer** in Visual
Studio.

![Debug in Visual
Studio](media/image123.png){width="9.092307524059493in"
height="6.655340113735783in"}

You can also set breakpoints for your bot. The breakpoints are hit only
after clicking **Start** in the Visual Studio environment, which will
attach to the Azure Function host (func command from Azure Functions
CLI). Chat with your bot again using the emulator and you should hit the
breakpoints that you set in Visual Studio.

Tip

If you cannot successfully set a breakpoint, a syntax error likely
exists in your code. To troubleshoot, look for compile errors in
the **Task Runner Explorer** window after you try to send messages to
your bot.

![Debug in Visual
Studio](media/image124.png){width="8.621215004374454in"
height="6.31051290463692in"}

Debug bots with the Bot Framework Emulator
==========================================

The Bot Framework Emulator is a desktop application that allows bot
developers to test and debug their bots, either locally or remotely.
Using the emulator, you can chat with your bot and inspect the messages
that your bot sends and receives. The emulator displays messages as they
would appear in a web chat UI and logs JSON requests and responses as
you exchange messages with your bot.+

Tip

Before you deploy your bot to the cloud, run it locally and test it
using the emulator. You can test your bot using the emulator even if you
have not
yet [registered](https://docs.microsoft.com/en-us/bot-framework/bot-service-quickstart-registration) it
with the Bot Framework or configured it to run on any channels.

**Prerequisites**
-----------------

### **Download the Bot Framework Emulator**

Download packages for Mac, Windows, and Linux are available via
the [GitHub releases
page](https://github.com/Microsoft/BotFramework-Emulator/releases).

### **Install and configure ngrok**

If you are using Windows and you are running the Bot Framework Emulator
behind a firewall or other network boundary and want to connect to a bot
that is hosted remotely, you must install and
configure **ngrok** tunneling software. The Bot Framework Emulator
integrates tightly with [ngrok](https://ngrok.com/) tunnelling software
(developed by [inconshreveable](https://inconshreveable.com/)), and can
launch it automatically when it is needed.

To install **ngrok** on Windows and configure the emulator to use it,
complete these steps:

1.  Download the [ngrok](https://ngrok.com/) executable to your local
    > machine.

2.  Open the emulator\'s App Settings dialog, enter the path to ngrok,
    > select whether or not to bypass ngrok for local addresses, and
    > click **Save**.

![Setting the path to
ngrok](media/image125.png){width="10.98263888888889in"
height="6.7243055555555555in"}

When the emulator connects to a bot that is hosted remotely, it displays
messages in its log that indicate that ngrok has automatically been
launched. If you\'ve followed these steps but the emulator\'s log
indicates that it is not able to launch ngrok, ensure that you have
installed ngrok version 2.1.18 or later. (Earlier versions have been
known to be incompatible.) To check ngrok\'s version, run this command
from the command line:

ngrok -v

**Connect to a bot that is running on localhost**
-------------------------------------------------

Launch the Bot Framework Emulator and enter your bot\'s endpoint into
the emulator\'s address bar.

Tip

If your bot was built using the Bot Builder SDK, the default endpoint
for local debugging is http://localhost:3978/api/messages. This is where
the bot will be listening for messages when hosted locally.

Next, if your bot is running with Microsoft Account (MSA) credentials,
enter those values into the **Microsoft App ID** and **Microsoft App
Password** fields. For localhost debugging, you will not typically need
to populate these fields, although doing so is supported if your bot
requires it.

Finally, click **Connect** to connect the emulator to your bot. After
the emulator has connected to your bot, you can send and receive
messages using the embedded chat control.

**Connect to a bot that is hosted remotely**
--------------------------------------------

Launch the Bot Framework Emulator and enter your bot\'s endpoint into
the emulator\'s address bar.

Next, populate the **Microsoft App ID** and **Microsoft App
Password** fields with your bot\'s credentials.

Note

To find your bot\'s **AppID** and **AppPassword**, see [MicrosoftAppID
and
MicrosoftAppPassword](https://docs.microsoft.com/en-us/bot-framework/bot-service-manage-overview#microsoftappid-and-microsoftapppassword).

Ensure
that [ngrok](https://docs.microsoft.com/en-us/bot-framework/bot-service-debug-emulator#ngrok) is
installed and that the emulator\'s App Settings specify the path to
the **ngrok**executable. **ngrok** enables the emulator to communicate
with your remotely-hosted bot.

Finally, click **Connect** to connect the emulator to your bot. After
the emulator has connected to your bot, you can send and receive
messages using the embedded chat control.

**Enable speech recognition**
-----------------------------

The Bot Framework Emulator supports speech recognition via
the [Cognitive Services Speech
API](https://docs.microsoft.com/en-us/azure/cognitive-services/Speech/home).
This allows you to exercise your speech-enabled bot, or Cortana skill,
via speech in the emulator during development. The Bot Framework
Emulator provides speech recognition free of charge for up to three
hours per bot per day.

**Send system activities**
--------------------------

You can use the Bot Framework Emulator to emulate specific activities
within the context of a conversation, by selecting from the available
options under **Conversation** \> **Send System Activity** in the
emulator\'s settings menu:

-   conversationUpdate (user added)

-   conversationUpdate (user removed)

-   contactRelationUpdate (bot added)

-   contactRelationUpdate (bot removed)

-   typing

-   ping

-   deleteUserData

**Emulate payment processing**
------------------------------

You can use the Bot Framework Emulator to emulate payment processing. In
emulation mode, no real payment will be processed. Instead, the process
payment logic simply returns a successful payment record. For payment
processing, the emulator remembers your payment methods, shipping
addresses, and it support form field validation.

Test a Cortana skill
====================

If you\'ve built a Cortana skill using the Bot Builder SDK, you can test
it by invoking it from Cortana. The following instructions walk you
through the steps required to try out your Cortana skill.

**Register your bot**
---------------------

If you [created your
bot](https://docs.microsoft.com/en-us/bot-framework/bot-service-quickstart) using
Bot Service in Azure, then your bot is already registered and you can
skip this step.

If you have deployed your bot elsewhere or if you want to test your bot
locally, then you
must [register](https://docs.microsoft.com/en-us/bot-framework/bot-service-quickstart-registration) your
bot so that you can connect it to Cortana. During the registration
process, you will need to provide your bot\'s **Messaging endpoint**. If
you choose to test your bot locally, you will need to run a tunneling
software such as [ngrok](http://ngrok.com/) to get an endpoint for your
local bot.

**Get messaging endpoint using ngrok**
--------------------------------------

If you are running the bot locally, you can get an endpoint to use for
testing by running tunneling software, such
as [ngrok](https://ngrok.com/). To use ngrok to get an endpoint, from a
console window type:

cmdCopy

ngrok.exe http 3979 -host-header=\"localhost:3979\"

This configures and displays an ngrok forwarding link that forward
requests to your bot, which is running on port 3978. The URL to the
forwarding link should look something like
this: https://0d6c4024.ngrok.io. Append /api/messages to the link, to
form a messaging endpoint URL in this
format: https://0d6c4024.ngrok.io/api/messages.

Enter this endpoint URL in the **Configuration** section of your
bot\'s [Settings](https://docs.microsoft.com/en-us/bot-framework/bot-service-manage-settings) blade.

**Enable speech recognition priming**
-------------------------------------

If your bot uses a Language Understanding (LUIS) app, make sure you
associate the LUIS application ID with your registered bot service. This
helps your bot recognize spoken utterances that are defined in your LUIS
model. For more information, see [Speech
priming](https://docs.microsoft.com/en-us/bot-framework/bot-service-manage-speech-priming).

**Add the Cortana channel**
---------------------------

Open the blade for your bot and click **Channels**. From the list of
channels, click the **Cortana** icon.

![Add the Cortana channel
](media/image126.png){width="8.327777777777778in"
height="5.465277777777778in"}

Note

[Secure your
bot](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-security) by
configuring the **AppID** and **AppPassword** in
your **Web.config** file. To find your
bot\'s **AppID** and **AppPassword**, see [MicrosoftAppID and
MicrosoftAppPassword](https://docs.microsoft.com/en-us/bot-framework/bot-service-manage-overview#microsoftappid-and-microsoftapppassword).

### **Configure Cortana**

When connecting your bot with the Cortana channel, some basic
information about your bot will be pre-filled into the registration
form. Review this information carefully. This form consists of the
following fields.

  Field                   Description
  ----------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Skill icon**          An icon that is displayed in the Cortana canvas when your skill is invoked. This is also used where skills are discoverable (like the Microsoft store). (32KB max, PNG only).
  **Display name**        The name of your Cortana skill is displayed to the user at the top of the visual UI. (30 character limit)
  **Invocation name**     This is the name users say when invoking a skill. It should be no more than three words and easy to pronounce. See the [Invocation Name Guidelines](https://aka.ms/cortana-invocation-guidelines) for more information on how to choose this name.
  **Description**         A description of your Cortana skill. This is used where skills are discoverable (like the Microsoft store).
  **Short description**   A short description of your skill's functionality, used to describe the skill in Cortana's notebook.

### **Request user profile data (Optional)**

Cortana provides access to several different types of user profile
information, that you can use to customize the bot for the user.

Note

You can skip this step if you don\'t need to use user profile data in
your bot.

To add user profile information, click the **Add a user profile
request** link, then select the user profile information you want from
the drop-down list. Add a friendly name to use to access this
information from your bot\'s code. See [Cortana-specific
entities](https://aka.ms/lgvcto) for more information on using these
fields.

![Fill out user profile
data](media/image127.png){width="9.138194444444444in"
height="4.810416666666667in"}

### **Manage user identity through connected services (Optional)**

If your skill requires authentication, you can connect an account so
that Cortana will require users to log in into your skill before they
can use it. Currently, only **Auth Code Grant** authentication is
supported, and **Implicit Grant** is not supported. See [Secure your
skill with authentication](https://aka.ms/vsdqcj) for more information.

Note

You can skip this step if your bot doesn\'t require authentication.

### **Connect to Cortana**

When you are done filling out the registration form for your Cortana
skill, click **Save** to complete the connection. This brings you back
to your bot\'s **Channels** blade and you should see that it is now
connected to Cortana.

At this point your bot has already been automatically deployed as a
Cortana skill to your account.

**Test using Web Chat control**
-------------------------------

To test your bot using the integrated web chat control in Bot Service,
click **Test in Web Chat** and type a message to verify that your bot is
working.

**Test using emulator**
-----------------------

To test your bot using
the [emulator](https://docs.microsoft.com/en-us/bot-framework/bot-service-debug-emulator),
do the following:

1.  Run the bot.

2.  Open the emulator and fill in the necessary information. To find
    > your bot\'s **AppID** and **AppPassword**, see [MicrosoftAppID and
    > MicrosoftAppPassword](https://docs.microsoft.com/en-us/bot-framework/bot-service-manage-overview#microsoftappid-and-microsoftapppassword).

3.  Click **Connect** to connect the emulator to your bot.

4.  Type a message to verify that your bot is working.

**Test using Cortana**
----------------------

You can invoke your Cortana skill by speaking an invocation phrase to
Cortana.

1.  Open Cortana.

2.  Open the Notebook within Cortana and click **About me** to see which
    > account you\'re using for Cortana. Make sure you are signed in
    > with the same Microsoft account that you used to register your
    > bot.![Sign in to Cortana\'s
    > notebook](media/image128.png){width="8.327777777777778in"
    > height="8.172222222222222in"}

3.  Click on the microphone button in the Cortana app or in the \"Ask me
    > anything\" search box in Windows, and say your bot\'s [invocation
    > phrase](https://aka.ms/cortana-invocation-guidelines). The
    > invocation phrase includes an *invocation name*, which uniquely
    > identifies the skill to invoke. For example, if a skill\'s
    > invocation name is \"Northwind Photo\", a proper invocation phrase
    > could include \"Ask Northwind Photo to\...\" or \"Tell Northwind
    > Photo that\...\".

> You specify your bot\'s *Invocation Name* when you configure it for
> Cortana. ![Enter the invocation name when you configure the Cortana
> channel](media/image129.png){width="7.1722222222222225in"
> height="5.965277777777778in"}

4.  If Cortana recognizes your invocation phrase, your bot launches in
    > Cortana\'s canvas.

**Troubleshoot**
----------------

If your Cortana skill fails to launch, check the following:

-   Make sure you are signed in to Cortana using the same Microsoft
    > account that you used to register your bot in the Bot Framework
    > Portal.

-   Check if the bot is working by clicking **Test in Web chat** to open
    > the **Chat** window and typing a message to it.

-   Check if your invocation name meets
    > the [guidelines](https://aka.ms/cortana-invocation-guidelines). If
    > your invocation name is longer than three words, hard to
    > pronounce, or sounds like other words, Cortana might have
    > difficulty recognizing it.

-   If your skill uses a LUIS model, make sure you [enable speech
    > recognition
    > priming](https://docs.microsoft.com/en-us/bot-framework/bot-service-manage-speech-priming).

See the [Enable Debugging of Cortana
skills](https://aka.ms/cortana-enable-debug) for additional
troubleshooting tips and information on how to enable debugging of your
skill in the Cortana dashboard.
