---
tags:
  - command
---

# /rcjoin

## Syntax

<!--cmd-syntax-start-->
```eqcommand
/rcjoin <channel> [auto|noauto]
```
<!--cmd-syntax-end-->

## Description

<!--cmd-desc-start-->
You can also create and use custom channels dynamically. Channels may be marked as auto (default) or noauto to persist in settings if the channel should be automatically joined by the character.
<!--cmd-desc-end-->

## Examples

Make a channel called "clerics". On each character you want in the channel, type:
```
/rcjoin clerics noauto
```

To make all characters in the channel "clerics" say "I am a cleric",
```
/rc clerics /say I am a cleric
```

## See also

- [/rc](cmd-rc.md)
- [/rcleave](cmd-rcleave.md)
