Bot Builder SDK for .NET samples

These samples demonstrate task-focused bots that show how to take
advantage of features in the Bot Builder SDK for .NET. You can use the
samples to help you quickly get started with building great bots with
rich capabilities.

**Get the samples**
-------------------

To get the samples, clone
the [BotBuilder-Samples](https://github.com/Microsoft/BotBuilder-Samples) GitHub
repository using Git.

cmdCopy

git clone https://github.com/Microsoft/BotBuilder-Samples.git

cd BotBuilder-Samples

The sample bots built with the Bot Builder SDK for .NET are organized in
the **CSharp** directory.

You can also view the samples on GitHub and deploy them to Azure
directly.

**Core**
--------

These samples show the basic techniques for building rich and capable
bots.

  Sample                                                                                                                            Description
  --------------------------------------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------
  [Send Attachment](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-SendAttachment)                         A sample bot that sends simple media attachments (images) to the user.
  [Receive Attachment](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-ReceiveAttachment)                   A sample bot that receives attachments sent by the user and downloads them.
  [Create New Conversation](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-CreateNewConversation)          A sample bot that starts a new conversation using a previously stored user address.
  [Get Members of a Conversation](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-GetConversationMembers)   A sample bot that retrieves the conversation\'s members list and detects when it changes.
  [Direct Line](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-DirectLine)                                 A sample bot and a custom client that communicate with each other using the Direct Line API.
  [Direct Line (WebSockets)](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-DirectLineWebSockets)          A sample bot and a custom client that communicate with each other using the Direct Line API + WebSockets.
  [Multi Dialogs](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-MultiDialogs)                             A sample bot that shows various kinds of dialogs.
  [State API](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-State)                                        A stateless sample bot that tracks the context of a conversation.
  [Custom State API](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-CustomState)                           A stateless sample bot that tracks the context of a conversation using a custom storage provider.
  [ChannelData](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-ChannelData)                                A sample bot that sends native metadata to Facebook using ChannelData.
  [AppInsights](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/core-AppInsights)                                A sample bot that logs telemetry to an Application Insights instance.

**Search**
----------

This sample shows how to leverage Azure Search in data-driven bots.

  Sample                                                                                           Description
  ------------------------------------------------------------------------------------------------ -----------------------------------------------------------------------
  [Azure Search](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/demo-Search)   Two sample bots that help the user navigate large amounts of content.

**Cards**
---------

These samples show how to send rich cards in the Bot Framework.

  Sample                                                                                                        Description
  ------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------
  [Rich Cards](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/cards-RichCards)              A sample bot that sends several different types of rich cards.
  [Carousel of Cards](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/cards-CarouselCards)   A sample bot that sends multiple rich cards within a single message using the Carousel layout.

**Intelligence**
----------------

These samples show how to add artificial intelligence capabilities to a
bot using Bing and Microsoft Cognitive Services APIs.

  Sample                                                                                                                Description
  --------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------
  [LUIS](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/intelligence-LUIS)                          A sample bot that uses LuisDialog to integrate with a LUIS.ai application.
  [Image Caption](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/intelligence-ImageCaption)         A sample bot that gets an image caption using the Microsoft Cognitive Services Vision API.
  [Speech To Text](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/intelligence-SpeechToText)        A sample bot that gets text from audio using the Bing Speech API.
  [Similar Products](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/intelligence-SimilarProducts)   A sample bot that finds visually similar products using the Bing Image Search API.
  [Zummer](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/intelligence-Zummer)                      A sample bot that finds wikipedia articles using the Bing Search API.

**Reference implementation**
----------------------------

This sample is designed to showcase an end-to-end scenario. It\'s a
great source of code fragments if you\'re looking to implement more
complex features in your bot.

  Sample                                                                                                      Description
  ----------------------------------------------------------------------------------------------------------- ------------------------------------------------------------
  [Contoso Flowers](https://github.com/Microsoft/BotBuilder-Samples/tree/master/CSharp/demo-ContosoFlowers)   A sample bot that uses many features of the Bot Framework.

Bot Builder SDK for Node.js samples
===================================

These samples demonstrate task-focused bots that show how to take
advantage of features in the Bot Builder SDK for Node.js. You can use
the samples to help you quickly get started with building great bots
with rich capabilities.

**Get the samples**
-------------------

To get the samples, clone
the [BotBuilder-Samples](https://github.com/Microsoft/BotBuilder-Samples) GitHub
repository using Git.

cmdCopy

git clone https://github.com/Microsoft/BotBuilder-Samples.git

cd BotBuilder-Samples

The sample bots built with the Bot Builder SDK for Node.js are organized
in the **Node** directory.

You can also view the samples on GitHub and deploy them to Azure
directly.

**Core**
--------

These samples show the basic techniques for building rich and capable
bots.

  Sample                                                                                                                          Description
  ------------------------------------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------
  [Send Attachment](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-SendAttachment)                         A sample bot that sends simple media attachments (images) to the user.
  [Receive Attachment](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-ReceiveAttachment)                   A sample bot that receives attachments sent by the user and downloads them.
  [Create New Conversation](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-CreateNewConversation)          A sample bot that starts a new conversation using a previously stored user address.
  [Get Members of a Conversation](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-GetConversationMembers)   A sample bot that retrieves the conversation\'s members list and detects when it changes.
  [Direct Line](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-DirectLine)                                 A sample bot and a custom client that communicate with each other using the Direct Line API.
  [Direct Line (WebSockets)](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-DirectLineWebSockets)          A sample bot and a custom client that communicate with each other using the Direct Line API + WebSockets.
  [Multi Dialogs](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-MultiDialogs)                             A sample bot that shows various kinds of dialogs.
  [State API](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-State)                                        A stateless sample bot that tracks the context of a conversation.
  [Custom State API](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-CustomState)                           A stateless sample bot that tracks the context of a conversation using a custom storage provider.
  [ChannelData](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-ChannelData)                                A sample bot that sends native metadata to Facebook using ChannelData.
  [AppInsights](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/core-AppInsights)                                A sample bot that logs telemetry to an Application Insights instance.

**Search**
----------

This sample shows how to leverage Azure Search in data-driven bots.

  Sample                                                                                         Description
  ---------------------------------------------------------------------------------------------- -----------------------------------------------------------------------
  [Azure Search](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/demo-Search)   Two sample bots that help the user navigate large amounts of content.

**Cards**
---------

These samples show how to send rich cards in the Bot Framework.

  Sample                                                                                                      Description
  ----------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------
  [Rich Cards](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/cards-RichCards)              A sample bot that sends several different types of rich cards.
  [Carousel of Cards](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/cards-CarouselCards)   A sample bot that sends multiple rich cards within a single message using the Carousel layout.

**Intelligence**
----------------

These samples show how to add artificial intelligence capabilities to a
bot using Bing and Microsoft Cognitive Services APIs.

  Sample                                                                                                              Description
  ------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------
  [LUIS](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/intelligence-LUIS)                          A sample bot that uses LuisDialog to integrate with a LUIS.ai application.
  [Image Caption](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/intelligence-ImageCaption)         A sample bot that gets an image caption using the Microsoft Cognitive Services Vision API.
  [Speech To Text](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/intelligence-SpeechToText)        A sample bot that gets text from audio using the Bing Speech API.
  [Similar Products](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/intelligence-SimilarProducts)   A sample bot that finds visually similar products using the Bing Image Search API.
  [Zummer](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/intelligence-Zummer)                      A sample bot that finds wikipedia articles using the Bing Search API.

**Reference implementation**
----------------------------

This sample is designed to showcase an end-to-end scenario. It\'s a
great source of code fragments if you\'re looking to implement more
complex features in your bot.

  Sample                                                                                                    Description
  --------------------------------------------------------------------------------------------------------- ------------------------------------------------------------
  [Contoso Flowers](https://github.com/Microsoft/BotBuilder-Samples/tree/master/Node/demo-ContosoFlowers)   A sample bot that uses many features of the Bot Framework.
