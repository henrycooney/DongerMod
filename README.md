# DongerMod

A discord bot that can manage your subscriber games.

### Info

The bot is currently on invite only.

## How does it work?

The for each discord server, the bot will host it's own queue, which everyone with the right permissions on the server can join.

There are 3 different roles that the bot recognizes:
- Admin
- Mod
- Subscriber

Subscribers and Mods can join the queue by typing a command in a specific channel. The host can then decide to invite a desired amount of people by entering a command with the ammount and an eventual password that will be automatically sent to the selected group of subscribers. The bot will check every discord member in the queue (beginning from position 1) if the member has his discord status set to "online" (green dot) and invite those people until it reached the before specified amount of people that should be invited. Those invited people are automatically removed from the queue and can then join again by typing the join command in the specific channel.


## Setup
Once you have added the DongerMod bot to your discord server, you can set it up by following this step by step instructions:


__1. Role Setup__
  
  You have to create 3 roles on your server and assign them to the according people, so the bot can recognize which member has which       access level. None of those roles needs any special permissions or colors. It serves only a "tag". Only the role name is important.
  
  - The first role is the subscriber role. This role must have one of the following names: `Sub`, `Subs`, `Subscriber`, `Subscribers`,       `Twitch Subscriber`
    If your subscribers already have a role with one of those names assigned, you probably don't need to do anything at this point.
  
  - The second role is the moderator role. This role must have one of the following names: `Mod, Mods, Moderator, Subgame Moderator, Bot       Moderator`
    If your moderators already have a role with one of those names assigned, you probably don't need to do anything at this point.
 
  - The second role is the moderator role. This role must have one of the following names: `Subgame Admin, Admin, Bot Admin`
    This role is mainly meant for the subgame host/streamer himself, as it permitts him to invite people from the queue.
    
    
__2. Channel Setup__

  To do the following steps, you must have a admin role assigned to you.
 
  - Type `!setsubgamechannel` in every channel on the server in which you want that the subscribers will be able to use join and list       commands.
  
  - Type `!setnotificationchannel` in every channel on the server in which you want to be able to send a subgame notification later.         This is optional!
  
  - Type `!setmodchannel` in every channel on the server in which you want your mods to be able to use moderator commands like removing     subscribers from the list etc. This will also be the channel where the subgame host/streamer is able to type his invite command.


__3. Messages Setup__
 
  Execute the following commands in one of your specified mod channels. All of those commands are optional. If you want to remove the     automatic sending of one of those message, just execute the according command without specifying a message: 
  
  - Type `!setsubgamechannelscheduledmsg \<your message\>` to set the message that will be posted to the subgame channel(s) once the         time to join for the invited subscribers has passed.

  - Type `!setnotifchannelschedmsg \<your message\>` to set the message that will be posted to the notification channel(s) once the time     to join for the invited subscribers has passed.

  - Type `!setsubwipedmsg \<your message\>` to set the message that will be posted to the subgame channel(s) as soon as the queue wipe       command is called.
  
  - Type `!setnotifwipedmsg \<your message\>` to set the message that will be posted to the notification channel(s) as soon as the queue     wipe command is called.
  
  - Type `!setinvitemsg \<your message\>` to set the message that will be sent to every invited subscriber. You can add two different       values to this message. Add `{jointime}` somewhere in your message and it will be replaced by the time in seconds until the public       messages (in the subscriber and notification channels) are being sent. Add `{password}` somewhere in the message and is will be         replaced by the password that was entered when the invite command was used.
  
  - Type  `!sgsetjointime \<number\>` to set the time in seconds until the bot sends the public messages. If you set the time to 0           seconds, the bot will send them imediately. If you don't want to send any public messages, you have to remove all of the above           messages. (They are removed by default)
  
  - The subgame host/streamer must have the admin role and has to type the command `!sethost` to set himself as the subgame                 host/streamer.
