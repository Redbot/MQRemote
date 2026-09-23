---
tags:
  - plugin
resource_link: "https://www.redguides.com/community/resources/mqremote.3345/"
support_link: "https://www.redguides.com/community/threads/mqremote.97294/"
repository: "https://github.com/peonMQ/MQRemote"
config: "MQRemote.ini"
authors: "PeonMQ"
tagline: "MQRemote is a modernized remote communication plugin for MacroQuest, inspired by EQBC and MQ2DanNet."
acknowledgements: "Inspiration from EQBC and MQ2DanNet"
---

# MQRemote

<!--desc-start-->
MQRemote is a modernized remote communication plugin for MacroQuest, inspired by EQBC and MQ2DanNet. It provides reliable, multi-channel text communication between clients with a cleaner internal design, and tighter integration with contemporary MacroQuest workflows using its built-in actors system.
<!--desc-end-->

## Getting Started
Load the plugin like any other MacroQuest plugin:

```txt
/plugin MQRemote
```

The plugin initializes automatically on load. Default channels (Globla, Server, Group, Raid, Zone) are created dynamically as they become available in-game. No additional setup is required for basic functionality.

### Commands
MQRemote supports multiple logical communication channels. All commands use the /rc prefix.

<a href="cmd-rc/">
{% 
  include-markdown "projects/mqremote/cmd-rc.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "projects/mqremote/cmd-rc.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('projects/mqremote/cmd-rc.md') }}

<a href="cmd-rcjoin/">
{% 
  include-markdown "projects/mqremote/cmd-rcjoin.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "projects/mqremote/cmd-rcjoin.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('projects/mqremote/cmd-rcjoin.md') }}

<a href="cmd-rcleave/">
{% 
  include-markdown "projects/mqremote/cmd-rcleave.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "projects/mqremote/cmd-rcleave.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('projects/mqremote/cmd-rcleave.md') }}

### Configuration File
A configuration file,`MQRemote.ini`, is used for storing logging settings and custom channels that should be automatically joined has the following setup:

```ini
[MQRemote]
LoggingFlags=15

[Winnythepoo]
honeyjar=1
bees=0

[Pigglet]
forrest=1
```

### Examples
Sending commands to other toons: 
```
/rc server ToonName /sit
/rc server ToonName /stand
/rc server ToonName /macro ninjalooter
/rc server ToonName /endmacro
```

Make a channel called "clerics". On each character you want in the channel, type:
```
/rcjoin clerics noauto
```

To make all characters in the channel "clerics" say "I am a cleric",
```
/rc clerics /say I am a cleric
```

Sending commands to all other connects clients: 
```
/rc global /target id ${Me.ID}
```

To have the recieving client parse MQ data use `noparse`
```
/noparse /rc +self global /echo I am ${Me.PctExp} into ${Me.Level}
```

## Easier migration from EQBC or DanNet
Setup aliases for the different channels to be similar to your previous preferred choice of plugin.

Example
```
# Tells matching eqbc or dannet api
/alias /rct /rc server

# All matching eqbc or dannet api
/alias /rca /rc server

# All including self matching eqbc or dannet api
/alias /rcaa /rc +self server

# Zone matching eqbc or dannet api
/alias /rcz /rc zone

# Zone including self matching eqbc or dannet api
/alias /rcza /rc +self zone

# Group matching eqbc or dannet api
/alias /rcg /rc group

# Group including self matching eqbc or dannet api
/alias /rcga /rc +self group

# Raid matching dannet api
/alias /rcr /rc raid

# Raid including self matching dannet api
/alias /rcra /rc +self raid
```

## Authors
* PeonMQ - *Initial work*

See also the list of [contributors](https://github.com/peonmq/mqremote/contributors.md) who participated in this project.

## Acknowledgments
* Inspiration from EQBC and MQ2DanNet
