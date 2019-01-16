# QC QuickCheck

*Quick Check of Cisco CE endpoints info*

---

**ToDo's:**

- [ ] Consider writing your README first.  Doing so helps you clarify your intent, focuses your project, and it is much more fun to write documentation at the beginning of a project than at the end of one, see:
    - [Readme Driven Development](http://tom.preston-werner.com/2010/08/23/readme-driven-development.html)
    - [GitHub Guides: Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
- [ ] Ensure you put the [license and copyright header](./HEADER) at the top of all your source code files.
- [ ] Be mindful of the third-party materials you use and ensure you follow Cisco's policies for creating and sharing Cisco Sample Code.

---

## Motivation

There are many fine tools for managing Cisco Video Endpoints that do so much more than **QuickCheck**.  But, on occasion, you get a call saying "All the video units are down." Are they?  Are they ALL down or just some of them?  With QuickCheck, you could query the QC bot in a webex teams space "QC getStatus" and the bot would query the status of every video unit you manage and respond with a quick, concise report. Maybe follow that with "QC getDiags" to see a report of Diagnostic Alerts generated by each of your managed endpoints.  Quick and Simple with valuable results.

## Show Me!

Are all my endpoints running the same code?  Use QuickCheck!

You1:23 PM
QC getVersion

QC1:23 PM
Cisco Berry Farms at Kellers DX70 on webex sandbox at home office is:
	 ce9.7.0 54ac0f80a97 2018-12-19
MX800 Test at Kellers MX800 on webex sandbox at home office is:
	 ce9.7.0 54ac0f80a97 2018-12-19

## Features

  Here are the actions supported by QuickCheck:  
  **help**       - This help menu  
  **list**       - Print endpoints from [endpoints.json](./include/endpoints.json) list.  
  **getStatus**  - Provides Standby Status.  
  **getDiags**   - List any diagnostic alerts.  
  **getVersion** - List current software version.  
  **sipStatus**  - List SIP registration Status.  
  **getLoss**    - List Packet Loss values.  
  **getLast**    - List Last Call Details.  

## Technologies & Frameworks Used

This is Cisco Sample Code!  What Cisco and third-party technologies are you working with?  Are you using a coding framework or software stack?  A simple list will set the context for your project.

**Cisco Products & Services:**

- Product
- Service

**Third-Party Products & Services:**

- Product
- Service

**Tools & Frameworks:**

- Framework 1
- Automation Tool 2

## Usage

If people like your project, they will want to use it.  Show them how.

## Installation

Provide a step-by-step series of examples and explanations for how to install your project and its dependencies.
Pre-Requisites for QuickCheck
  - Create a webex teams bot - I created QC@webex.bot
      How to create a webex teams bot (using python):
  https://developer.webex.com/blog/spark-bot-demo
  - Invite your bot to a webex teams space
  - Create a webex teams webhook that will listen for messages to your bot and forward them to your bot handling app. (this app)
    HowTo:
  - Get an account on ngrok which gives you a tunnel from ngrok to your laptop and a public address at ngrok for your webhook to send http messages to.  *** ngrok is sometimes considered a security risk by corporate security services, so check with IT before loading ngrok client on your laptop.
    - Launch ngrok client on laptop
- Edit endpoints.json file to include endpoints you want to manage.
- Run main.py from terminal on laptop
    main.py will
      - launch local HTTP server on port 10010
        (You can change port number in main.py/global variables)
      - check your local ngrok client and get public uri
      - edit your webex teams webhook with current ngrok target


## Authors & Maintainers

People responsible for the creation and maintenance of this project:

- Keller McBride <kelmcbri@cisco.com>
- Trey George <ergeorge@cisco.com>

## Credits

Give proper credit.  Inspired by another project or article?  Was your work made easier by a tutorial?  Include links to the people, projects, and resources that were influential in the creation of this project.

## License

This project is licensed to you under the terms of the [Cisco Sample
Code License](./LICENSE).
