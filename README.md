# QuickCheck
![Alt text](/images/qclogo512x512_icon.png?raw=true )

**A Webex Teams Bot to perform Quick Check of Cisco CE endpoints**

---

## Motivation

There are many fine tools for managing Cisco Video Endpoints that do so much more than **QuickCheck**.  But, on occasion, you get a call saying "All the video units are down." Are they?  Are they ALL down or just some of them?  With QuickCheck, you can query the QC bot in a webex teams space with "QC sipStatus" and the bot would query the status of every video unit you manage and respond with a quick, concise report right back to you in the same Webex Teams space. Maybe follow that with "QC getDiags" to see a report of current Diagnostic Alerts generated by each of your managed endpoints.  Quick and Simple with valuable results.

## Show Me!
![Alt text](/images/QC_Help.png?raw=true )

## Features

### **Welcome to QuickCheck** ###

Here are the actions supported by QuickCheck:
-  **help** - This help menu
-  **list** - print endpoints from [endpoints.json](./endpoints.json) file.
-  **callStatus** - Shows **current** call status.
-  **getDiags** - List any diagnostic alerts.
-  **getVersion** - List current software version.
-  **sipStatus** - List SIP registration Status.
-  **getLoss** - List current Packet Loss values.
-  **getLast** - List Last Call Details.
-  **getPeople** - List number of people in room.
-  **getNumber** - Get Endpoint Numbers.

## Technologies & Frameworks Used

This is Cisco Sample Code written in Python3. We use the Atom application on Apple Macbook Pro computer to write and maintain the code.  

The three of us are in a group called "tag-team" on github and use github as the central repository for this code.  (Atom has simple git and github actions built in which make it easier to code together)

Our github repository is publicly available at https://github.com/CiscoSE/QuickCheck.git



**Cisco Products & Services:**

- This Cisco Webex Teams bot uses Webex Teams API to send/receive JSON formatted webhooks.  The bot also sends/receives XML formatted xAPI commands to/from Cisco CE code based Video Endpoints.

## Installation

**Please Note:** This code is written for **Python 3**... if you have a Mac, it comes with **Python 2**... you will need to upgrade to Python 3 or do a whole lot of changes to many of the methods for it to work.

### Pre-Requisites for QuickCheck ###
  - Create a webex teams bot - We created QC@webex.bot starting from the "How to create a webex teams bot (using python)":
  https://developer.webex.com/blog/spark-bot-demo
  - Invite your bot to a webex teams space or 1-1 direct space.

  - Create a webex teams webhook that will listen for messages to your bot and forward them to a public address for your bot handling app.(this app)
    HowTo:
  - Get an account on ngrok which gives you a tunnel from ngrok to your laptop and a public address at ngrok for your webhook to send http messages to.  *** ngrok is sometimes considered a security risk by corporate security services, so check with IT before loading ngrok client on your laptop.

    - Launch ngrok client on laptop
- **Edit [endpoints.txt](./endpoints.txt)** file to include endpoints you want to manage and **save the file as [endpoints.json](./endpoints.json)**.
- **Edit [config.txt](./config.txt)** with your names and bearer tokens and **save the file as [config.json](config.json)**
- Run [main.py](./main.py) from terminal on laptop and main.py will
      - launch local HTTP server on port 10010
        (You can change port number in config.json)
      - check your local ngrok client and get public uri
      - edit your webex teams webhook with current ngrok target
     - HTTP server will then wait for incoming webhooks and send them to the intent method for action.

## Useful links
- **Edit Webex Teams Webhook:**  https://developer.webex.com/my-apps/
- **How to Create a Webex Teams Bot**  https://developer.webex.com/blog/spark-bot-demo
- **ngrok dashboard**  https://dashboard.ngrok.com/status
- **Our QuickCheck github repository** https://github.com/CiscoSE/QuickCheck.git
- **Sfartz Postman Collection** https://github.com/CiscoDevNet/postman-xapi


## Authors & Maintainers

People responsible for the creation and maintenance of this project:

- Keller McBride <kelmcbri@cisco.com>
- Trey George <ergeorge@cisco.com>
- Joe Bourne <jbourne@cisco.com>


## Credits

The HTTP server code and the send get/post to webex teams methods were inspired by the code in the "How to create a webex teams bot" tutorial at:  https://developer.webex.com/blog/spark-bot-demo
The original python 2 code for this tutorial can be found at "tahanson's" repository at https://github.com/webex/SparkBotDemo/blob/master/bot_demo.py


We pulled from ObjectIsAdvantag / Steve Sfartz Postman Collection Github Repository at https://github.com/CiscoDevNet/postman-xapi to create actions/intents, i.e. commands against Telepresence Endpoints you can execute with QuickCheck bot.


## License

This project is licensed to you under the terms of the [Cisco Sample
Code License](./LICENSE).

## Contributions
Please see [Contributing](./CONTRIBUTiNG.md) to help contribute to this code.

## Code of Conduct
Contributors to this code agree with our Code of Conduct: [CODE_OF_CONDUCT](./CODE_OF_CONDUCT.md)
