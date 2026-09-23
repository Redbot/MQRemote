---
tags:
  - command
---

# /rc

## Syntax

<!--cmd-syntax-start-->
```eqcommand
/rc [+self] <channel> <message>
/rc <channel> <character> <message>
```
<!--cmd-syntax-end-->

## Description

<!--cmd-desc-start-->
MQRemote supports multiple logical communication channels. All commands use the /rc prefix. All channels follow the pattern of `/rc [+self] <channel> <message>` where `+self` is optional, or `/rc <channel> <character> <message>` to send a tell to just that character in a channel (most used will probably be server channel).
<!--cmd-desc-end-->

## Built-in Channels
All channels follow the pattern of `/rc [+self] <channel> <message>` where `+self` is optional.
or `/rc <channel> <character> <message>` to send a tell to just that character in a channel (most used will probably be server channel).

### Global Channel
The global channel is always available
```
/rc global <message>        - Send a command to the global channel excluding self
/rc +self global <message>  - Send a command to the global channel message including self
/rc global name <message>   - Send a command to the global channel to the specific named character
```

### Server Channel
The server channel is available from character select screen and onwards. Use this to limit recievers to be only the other characters logged into the same server.
```
/rc server <message>        - Send a command to the server channel excluding self
/rc +self server <message>  - Send a command to the server channel message including self
/rc server name <message>   - Send a command to the server channel to the specific named character

```

### Zone Channel
The zone channel is available once the character is registered as being ingame. Use this to limit recievers to be only the other characters who are in the same zone.
```
/rc zone <message>        - Send a command to the zone channel excluding self
/rc +self zone <message>  - Send a command to the zone channel message including self
/rc zone name <message>   - Send a command to the zone channel to the specific named character
```

### Group Channel
The group channel is available whenever the character is in a group. Sends a command only to the characters in the same group.
```
/rc group <message>        - Send a command to the group channel excluding self
/rc +self group <message>  - Send a command to the group channel message including self
/rc group name <message>   - Send a command to the group channel to the specific named character
```

### Raid Channel
The group channel is available whenever the character is in a raid. Sends a command only to the characters in the same raid.
```
/rc raid <message>        - Send a command to the raid channel excluding self
/rc +self raid <message>  - Send a command to the raid channel message including self
/rc raid name <message>   - Send a command to the raid channel to the specific named character
```

## Custom Channels
You can also create and use custom channels dynamically. Channels may be marked as auto (default) or noauto to persist in settings if the channel should be automatically joined by the character.
```
# create
/rcjoin <channel> [auto|noauto]

#leave
/rcleave <channel> [auto|noauto]

#use
/rc [+self] <channel> <message>
/rc <channel> <name> <message>
```

## See also

- [/rcjoin](cmd-rcjoin.md)
- [/rcleave](cmd-rcleave.md)
