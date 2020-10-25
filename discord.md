---
permalink: /discord
---
# [The /r/ProgrammingLanguages Discord](https://discord.gg/4Kjt3ZE)
## Rules
These rules are guidelines for the moderation team just as much as they are for the members of this community. They are an elaboration of the rules for [/r/ProgrammingLanguages](https://reddit.com/r/ProgrammingLanguages).

### 1. Discussion should stay on topic
We are a community dedicated to the discussion of programming language design, so discussion should remain related to this topic. Use the appropriate Discord channel, and do not use the off-topic channels for unwanted promotional or NSFW material. Nobody's going to mind if you go slightly off-topic in a channel, but don't derail ongoing conversations, and at least move to the relevant channel if you find that the conversation has gone off-topic. 

### 2. Be civil and respectful
While we encourage discussion, and yes, even disagreements, we require them to remain civil, respectful, and constructive. We don’t want you here if your behavior disrupts the community. Examples of disruptive behaviors include, but are not limited to: insults, threats, intimidation, discrimination, personal attacks, harassment, rudeness, doxing, excessive negativity, spamming, trolling, excessive melodrama, and sexualized attention. **Use common sense**. If someone tells you to stop, there's a good chance you're being disruptive. Don't be a problem if you don't want to be handled like one.

Additionally, the /r/ProgrammingLanguages server is not the place to debate politics, religion, or philosophy, and such debates often lead to bad blood all around. A number of our members are interested in goodwill discussion, however, so we do recommend joining our friends at [The Philosophy Chat](https://discord.gg/MBqq2uh) if you're seeking productive discussion on the topic.

## The Members List
You might have noticed that the members list isn't divided into sections. All of us here are interested in programming language design and implementation, and we don't want to force artificial distinctions between members of our community. However, there are a couple convenience roles to facilitate easier communication:
* 💚 People with **green** names are **moderators**. Ask one of us (or ping `@Mods`) if you want something done about the discord server itself, like a new channel, or a new emote, or the rare instances when there's a troublemaker in the chat.
* 🧡 People with **orange** names are **language developers**, whose languages have a separate channel in our "Projects" section. **This does not mean that only the orange names are actively developing a language!** However, when you click on the profile of someone with an orange name, they will have a purple `@lang: LanguageName` role - that's the name of their language, which you should be able to find a separate channel for under the "Projects" heading in the channel list. Feel free to ask them about their language there!

## Channel Overview
### Meta
The Meta category is dedicated to discussing the actual platforms that our community uses:
* `#announcements` is used for important announcements regarding the Discord server or our community as a whole.
* `#arrivals` is a list of "welcome" messages for newly-joining users. You can see and greet the new members here.
* `#meta` is for discussion pertaining to the Discord server itself. If you want the mods to make any changes to the Discord, discuss them there.
* `#subreddit` is for talking about [/r/ProgrammingLanguages](https://reddit.com/r/ProgrammingLanguages). Slavfox posts notifications about the monthly discussion threads there.
* `#website` is for discussing [the website](https://proglangdesign.net/). A GitHub webhook is set up there, so you'll see when changes are made to it.
* `#wiki` is for discussion regarding this this (work-in-progress) wiki.

### General Chat
* `#off-topic` is for anything unrelated to programming (except for topics forbidden by the rules, such as politics, religion, or philosophy). You can think of it as a relaxed hang-out channel.
* `#programming` is for discussing programming and programming projects *not* related to programming languages themselves. Have a cool non-PL project that you're working on? Discuss it here!
* `#jobs` is for folks looking for employment or employees, mainly in programming language development.
* `#hey-look` is the channel for showing your achievements. New academic paper? Your language can now say "Hello World"? A new blog post or live-stream announcement? Anything you want to share!

### PLT&D
This is the main section of our Discord, for discussing programming language theory and design. You'll find channels devoted to every step of developing a programming language here, and a `#general` plt&d chat. Feel free to ask there if you don't think any of the other channels will fit your topic better.

`#beginners` is intended to be the place to go for folks new to PLT&D. The moderators are going to be extra strict on moderation there - it's supposed to be a welcoming place where someone without proglangs knowledge can ask how to get started and get help with their proglang journey, and being unwelcoming there is... unwelcome.

### Voice Channels
Go here to have an audio chat with other people! If you can't talk, or want to share a link relevant to what you're discussing, #voice-text is there as a supplemental text chat for the voice channels.

It's also possible to share your screen in those channels, if you'd like to stream your development.

### Project Channels
Members of our community may get a channel for their project in the `Projects` category.

#### How can I get a channel for my project?
You can get a channel for a project if:
* It is under active development
* It is related to programming languages (although not necessarily a programming language itself)
* You are a member of the project's team

Before you get a channel, I would recommend that:
* You have some sort of documentation to help explain your project to other users.
* You are an active member of the community and expect to regularly discuss your language with other users.

When you are ready to get your channel, just go ahead and ping the `@Mods` in `#meta`.
We will create your channel and give you a role for your project,
and the `@Language Developers` role if your project is a programming language.

#### What can I do with my channel?
You are given full moderator permissions over your channel, including the ability to:
* Change the channel's topic
* Pin or delete messages
* Create webhooks
* Give other users these permissions

You may also ask the `@Mods` to give other project members your project's role.

It is your channel and you can do what you like with it as long as you abide by the server rules.

If your project has its own Discord server, you may link to it,
but you should not create a channel if you only intend to use it to direct people to your server.

#### Git webhooks
You have permission in your channel to configure a webhook to recieve GitHub and GitLab notifications in your channel.
[Here's a gist that describes how to do it.](https://gist.github.com/jagrosh/5b1761213e33fc5b54ec7f6379034a22)

The purpose of the webhook is get server members involved in the discussion of your project.
To reduce noise, you *must not* enable star, fork, or commit notifications,
because those sorts of messages produce lots of noise while rarely leading to discussion.

I would recommend no more than these hooks:
* Published releases
* Published packages
* Issues and issue comments
* Pull requests, pull request comments, and pull request reviews
* Changes to the project's collaborators

#### Including your project on the website
If your project is reasonably mature and has a good landing page (e.g. a website or detailed README), I encourage you to go ahead and [showcase your work](https://github.com/proglangdesign/proglangdesign.github.io/#adding-your-project) on [the website's projects list](https://proglangdesign.net/#projects)!

You may simply open up a pull request to do this. The Discord moderators do not need to be involved.

#### Project emoji
If you include your project's square icon in PNG or SVG format with a colored or transparent background,
we will add it as an emoji.

#### Project bots
If you make a Discord bot, like an interpreter for your language, we will add it to your channel,
although you will have to find somewhere to host it yourself.
I highly encourage you to do this because language bots are awesome and we need more of them.

Currently our server has bots for `#aardvark`, `#calc=`, and `#volpe`.

#### Inactive project channels
1. After three months of inactivity, channels are automatically moved to the "Inactive Projects" category.
2. After three months in the inactive projects category, moderators will attempt to contact the owner of the channel.
3. If the channel's owner does not request for the channel's life to be extended (e.g. for when the developer needs to be on hiatus for more than 6 months), the channel's contents will be downloaded as a text file (not including e.g. file attachments), and that file will then be uploaded to `#archive`.

You may remove your project from the "Inactive Projects" category at any time by sending a message to the channel.
If you are planning on going on a (temporary) hiatus, you may voluntarily put your channel into the "Inactive Projects" category using the `!archive` command.
If you are planning on quitting your project permanently, please notify a moderator so that we may archive your channel.
Finally, as you have full permissions over your channel, you may delete your channel (without backup!) at any time.

Thanks to Timon Passlick for [the bot which automates the inactive projects list](https://github.com/proglangdesign/channel-sorter).
